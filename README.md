# Smart E-Grievance

An Android application for managing citizen complaints and grievances efficiently. Users can register, login, submit complaints about various civic issues, and track their complaint status in real-time.

## Features

- **User Authentication**: Secure user registration and login
- **Complaint Submission**: Report various types of grievances including:
  - Water issues
  - Electricity problems
  - Garbage management
  - Parking violations
  - Sound pollution
  - Gas leaks
  - Water leaks
  - Other civic issues
- **Complaint Tracking**: View status and details of submitted complaints
- **GPS Integration**: Location-based complaint submission
- **Admin Dashboard**: Different views for administrators to manage complaints
- **User-friendly UI**: Clean and intuitive Material Design interface

## Tech Stack

- **Language**: Java
- **Framework**: Android (API 31, MinSDK 23)
- **Architecture**: AndroidX
- **Database**: SQLite (local storage)
- **Networking**: Volley HTTP client
- **JSON**: GSON for serialization
- **UI Components**: Material Design, AppCompat

## Prerequisites

- Android Studio (latest)
- JDK 11 or higher
- Android SDK API 31 and above
- Gradle 7.6.1 (included via wrapper)

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/nimishaWargantiwar/Smart-E-Grievance.git
   cd Smart-E-Grievance
   ```

2. **Configure Android SDK**:
   Update `local.properties` with your Android SDK path:
   ```
   sdk.dir=/Users/YOUR_USERNAME/Library/Android/sdk
   ```

3. **Build the project**:
   ```bash
   ./gradlew build
   ```

## Running the App

### On Android Emulator

1. **Start the emulator**:
   ```bash
   emulator -avd Pixel_5_API_28
   ```

2. **Install and run the app**:
   ```bash
   ./gradlew installDebug
   ./gradlew assembleDebug
   adb shell am start -n info.androidhive.loginandregistration/.activity.LoginActivity
   ```

### On Physical Device

1. Connect your Android device via USB
2. Enable USB Debugging on your device
3. Run:
   ```bash
   ./gradlew installDebug
   ```

## Backend Configuration

The app communicates with a backend server for user authentication and complaint management.

### Default Backend URL

```
http://192.168.160.116:8080/Complaint/Business
```

### To Change Backend URL

Edit `app/src/main/java/info/androidhive/loginandregistration/app/AppConfig.java`:

```java
public static String URL = "http://YOUR_BACKEND_URL:PORT/ENDPOINT";
```

Also update hardcoded URLs in:
- `MainActivity.java` - Line 71
- `ViewProblem.java` - Line 116
- `AsyncServerTask.java` - Line 52

## Test Credentials

The app has built-in admin accounts for testing:

**Username (Email)**: `Admin`, `Electricity`, `Garbage`, `Parking`, `Water`, `Sound`, `Other`, `gasleak`, `Waterleak`  
**Password**: `1234`

## Recent Updates (April 2026)

### Migration to Modern Android Stack

✅ **Gradle & Build Tools**
- Upgraded Gradle from 7.2 → 7.6.1
- Updated Android Gradle Plugin 3.6.2 → 4.2.2
- Added modern JVM configuration for Java 19+ support

✅ **AndroidX Migration**
- Migrated from deprecated Android Support Libraries to AndroidX
- Updated all imports and dependencies
- Enabled Jetifier for compatibility

✅ **Fixed Imports**
- `android.support.v4.app.ActivityCompat` → `androidx.core.app.ActivityCompat`
- `android.support.v4.content.ContextCompat` → `androidx.core.content.ContextCompat`
- `android.support.v4.content.LocalBroadcastManager` → `androidx.localbroadcastmanager.content.LocalBroadcastManager`
- `android.support.v7.app.AlertDialog` → `androidx.appcompat.app.AlertDialog`

✅ **Manifest Improvements**
- Added `android:exported` attributes to all activities (required for Android 12+)
- Updated targetSdkVersion to 31
- Enabled cleartext HTTP traffic for legacy backend compatibility
- Removed duplicate permission declarations

✅ **Dependencies Updated**
- AndroidX AppCompat 1.3.1
- Material Design 1.4.0
- AndroidX ConstraintLayout 2.1.0
- Legacy support libraries for backward compatibility

## Project Structure

```
Smart-E-Grievance/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/info/androidhive/loginandregistration/
│   │       │   ├── activity/          # UI Activities
│   │       │   ├── app/               # App configuration
│   │       │   └── helper/            # Utilities & DB
│   │       ├── res/                   # Resources (layouts, strings, etc)
│   │       └── AndroidManifest.xml
│   ├── build.gradle
│   └── proguard-rules.txt
├── build.gradle
├── gradle.properties
├── settings.gradle
├── gradlew / gradlew.bat
└── local.properties
```

## Key Activities

- **LoginActivity**: User authentication
- **RegisterActivity**: New user registration
- **MainActivity**: Main dashboard and complaint submission
- **viewComplaint**: View pending complaints
- **viewImpComplaint**: View important/tracked complaints
- **Home**: Information and admin features
- **ViewProblem**: Detailed problem view

## Permissions

The app requires the following permissions:

```xml
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.READ_PHONE_STATE"/>
```

## Troubleshooting

### HTTP Connection Errors
- Ensure backend server is running and accessible
- Check firewall settings allow connection to backend port
- For emulator, use `10.0.2.2` instead of `localhost` to access host machine

### Build Errors
- Ensure Java 11+ is installed: `java -version`
- Clear Gradle cache: `./gradlew clean`
- Update Android SDK: Use Android Studio SDK Manager

### App Crashes on Launch
- Check Android version compatibility (min API 23, target API 31)
- Verify all required permissions are granted on device
- Check logcat for detailed error: `adb logcat | grep loginandregistration`

## Future Improvements

- Implement HTTPS for secure communication
- Add push notifications for complaint updates
- Implement offline mode with data sync
- Add image upload for complaints
- Real-time complaint tracking with maps
- User profile management
- Feedback and rating system

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Create a Pull Request

## License

This project is available under the MIT License.

## Author

- **Nimisha** - Repository Owner: [nimishaWargantiwar](https://github.com/nimishaWargantiwar)

## Support

For issues, questions, or suggestions, please open an issue on the [GitHub repository](https://github.com/nimishaWargantiwar/Smart-E-Grievance/issues).

---

**Last Updated**: April 29, 2026
