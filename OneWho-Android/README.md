# OneWho AI Android prototype
Native Java Android client (rather than React Native) with Android speech recognition and existing FastAPI backend. Android 8+. Foreground only, with consent. Speech recognition may use Google's network service. No APK is bundled: Android SDK and Gradle were unavailable in the authoring environment; compilation and device tests remain pending.
## Build without a laptop
Create a GitHub repository, upload all project files (including hidden .github/workflows/apk.yml), open Actions > Build Android APK > Run workflow. After a successful run download OneWho-AI-debug artifact, unzip, install app-debug.apk. Debug signing is for testing only.
## Backend
Deploy backend/Dockerfile to an HTTPS host supporting WebSockets. Set SUPABASE_URL, SUPABASE_ANON_KEY, LLM_API_KEY, LLM_MODEL and optionally LLM_BASE_URL. Create a Supabase user and obtain its access token through Supabase Auth. Enter the HTTPS backend URL and access token in the app. Backend is not hosted for you. Existing backend resume endpoint is not authenticated; restrict use to a private test deployment until hardened. Do not upload sensitive resumes on a public test server. Tokens are not persisted. API charges may apply.
## Local build
Open project in Android Studio with SDK 35 and JDK 17, sync Gradle, Build > Build APK(s). Or use installed Gradle 8.9: gradle assembleDebug.
