# WOD Daily — iOS & Android Expo app

A mobile-first CrossFit / functional fitness app starter using React Native + Expo.

## Included
- iOS and Android portrait-first UI with dark/neon styling
- Beginner, Intermediate, Professional levels
- Daily workout selection that changes by local day (deterministic rotation)
- Workout library with multiple workouts per level
- Timer with start/pause/reset, elapsed time, vibration at completion, and rest interval timer
- Direct numeric inputs for reps, custom workout duration, session duration, and rest duration (seconds; no preset-only lists)
- Movement completion checklist
- Exercise demonstration links that open YouTube tutorial searches
- Custom workout builder: name, format, duration, movements and rep counts
- Workout history and manually entered personal records
- AsyncStorage persistence on the device
- Optional daily 8:00 AM local notification reminder

## Run it
1. Install Node.js LTS and npm.
2. In this folder run `npm install`.
3. Run `npx expo start`.
4. Scan the QR code with Expo Go, or run `npm run ios` / `npm run android` with the appropriate simulator/tooling.

For reliable local notifications and native builds, use an Expo development build. iOS simulator builds require macOS/Xcode; Android builds can be done with Android Studio or EAS Build.

## Production steps still needed
- Replace `com.example.woddaily` with your unique iOS bundle identifier and Android application ID.
- Cloud sync/authentication is not enabled yet. Device persistence is implemented with AsyncStorage. To sync across devices, create a Supabase/Firebase project, add authentication and a database, and configure environment variables and access policies. Do not ship secret keys in the app.
- The exercise demo action opens YouTube search results rather than bundling copyrighted videos. Add licensed/owned video URLs for a polished in-app demo experience.
- Notifications require user permission and an installed app/development build. Current reminder schedules for 8:00 AM local time.
- The included workout catalog is a starter rotation, not a professional coaching prescription. Have a qualified coach review training plans and scaling guidance before public release.
- Add automated tests, app icons/splash assets, privacy policy, accessibility review, and store metadata before release.

## Notes
Workout history, custom workouts and PRs persist on the current device. Timer state itself is transient. The daily selection rotates by date; it does not fetch new workouts from a server. A true cloud-generated plan and cross-device sync require backend configuration.
