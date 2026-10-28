# WOD Daily — Netlify website + Android APK

This project is an Expo / React Native app. It has been prepared with a web export script, Netlify build settings, and an EAS APK profile.

## Deploy the website to Netlify

1. Extract this ZIP.
2. Upload the project to a GitHub repository (the repository root should contain `package.json`, `app.json`, and `netlify.toml`).
3. In Netlify choose **Add new site → Import an existing project** and connect the repository.
4. Netlify should read `netlify.toml`. Build command: `npm ci && npm run build:web`; publish directory: `dist`.
5. Deploy. Test the generated site on desktop and a real iPhone before sharing it.

## Build Android APK

1. Install Node.js 22 LTS and Git on your computer.
2. In the project folder run `npm ci`.
3. Install EAS CLI: `npm install -g eas-cli`.
4. Sign in: `eas login`.
5. Configure the project once: `eas build:configure` and follow prompts. Keep the generated Expo project ID in `app.json` if asked.
6. Build an APK: `eas build --platform android --profile preview`.
7. Open the build URL EAS gives you and download the APK to the Android phone.

## iPhone home screen

After the site is deployed, open its HTTPS URL in Safari → Share → Add to Home Screen. The web export and manifest settings are a starting point; verify installation behavior on the deployed site. If the manifest is not linked in the generated HTML, add the manifest link through the supported Expo web HTML template for the SDK version in use.

## Important

- Netlify hosts the web build; it does not produce Android APK files.
- The app currently saves history/custom workouts/records locally on each device using AsyncStorage. This is not cloud sync.
- The app uses Expo notifications; scheduled notifications are generally native-app functionality and may not work on the web.
- The Android/iOS application identifiers were changed from the example `com.example.woddaily` to `com.woddaily.app`. Choose a unique identifier before distributing builds.
- The package lockfile should be refreshed with `npm install` and committed before deploying.
