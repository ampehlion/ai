# Voice Agent (Android app)

A native Android app: tap Start once, it listens, sends what you say to Groq
(`llama-3.3-70b-versatile`), speaks the reply out loud, then automatically
listens again — until you tap Stop.

## How to build and run it

1. Install **Android Studio** (free): https://developer.android.com/studio
2. Open Android Studio → **Open** → select this `VoiceAgentApp` folder.
3. Wait for "Gradle sync" to finish (bottom status bar). This needs an internet
   connection the first time — it downloads the build tools automatically.
4. Connect your Android phone by USB with **USB debugging** enabled
   (Settings → About phone → tap "Build number" 7 times → Developer options →
   USB debugging), or use Android Studio's built-in emulator instead.
5. Click the green ▶ **Run** button at the top. Choose your phone/emulator.
6. The app installs and opens. Tap **Start**, allow microphone access when
   asked, and start talking.

## Notes

- Your Groq API key is already in the code, in
  `app/src/main/java/com/example/voiceagent/MainActivity.kt` near the top
  (`GROQ_API_KEY`). Since it was shared in plain text earlier, please rotate
  it at console.groq.com and paste the new one in that same spot.
- For faster/shorter replies, change `GROQ_MODEL` to `"llama-3.1-8b-instant"`.
- Like any Android app, the microphone only stays active while the screen is
  on and the app is in the foreground — Android suspends mic access for
  background/locked-screen apps unless you build a foreground service with a
  persistent notification, which is a bigger addition if you ever want it.
- To share this app with others without them installing Android Studio,
  use **Build → Generate Signed App Bundle / APK** in Android Studio once
  you're happy with it, then send them the resulting `.apk` file directly.
