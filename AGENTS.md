# MAX Complications (Wear OS watch face)

Product name: "MAX Complications". Package / applicationId: `com.guidohuisman.maxcomplications`.

## Concept
Maximum information density on a round Wear OS watch.
- Built with the **Watch Face Format (WFF)**, which has been mandatory for watch faces on Wear OS since January 2026. Do not use the deprecated Jetpack/AndroidX watch face libraries or a Canvas renderer.
- WFF allows at most **8 ComplicationSlots** per face. Use all 8 in a **2 columns x 4 rows grid** (or 4 x 2 if it fits the round screen better; say which you chose and why in the README).
- PLUS show every built-in WFF data source that does NOT use a complication slot. Check the current WFF reference (https://developer.android.com/reference/wear-os/wff) for the exact list and the minimum WFF version per item. Expected candidates: time (hours/minutes/seconds), date, weekday, month, step count, step goal %, heart rate, battery %, moon phase, timezone / UTC offset, AM/PM, day of year/week number if available. List in the README which ones you used and which WFF version each needs.
- Must stay legible on a round ~1.2-1.4 inch screen (about 384-456 px). Clean, readable layout, not a cluttered mess.
- Low-power ambient mode (dim, minimal, no seconds, no bright fills).
- Color customization via WFF `UserConfigurations` (a few color themes; maybe accent color).
- No other features.

## First run
1. A WFF watch face project (resource-only APK, `hasCode=false`, `com.google.wear.watchface.format.version` metadata, watch face XML in `res/raw`) that builds with the Gradle CLI.
2. README (what it is, build requirements, how to build, how to install on the watch).
3. `build-debug.cmd` in the project root: double-click builds the debug APK and tells where it is.
4. If JDK + Android SDK exist on this PC, prove it builds (`gradlew.bat assembleDebug`) and fix errors. If they don't, say so in README/STATUS.md and stop after writing the code.
## House rules (all projects)
- Meneer (Guido) is not a developer. Anything he must run = a double-clickable `.cmd` in the project root with plain-English steps in the README. Never ask him to type PowerShell or terminal commands.
- Kotlin, Gradle CLI (use the Gradle wrapper `gradlew.bat`), no emulators, no Android Studio requirement.
- No hardcoded absolute paths in code or scripts; resolve everything from the script's own folder (`%~dp0`). Use `local.properties` / env vars (`ANDROID_HOME`, `JAVA_HOME`) for the SDK and JDK, and keep `local.properties` out of git.
- Never put keystores, passwords, API keys or ad IDs in this folder, in git, or in chat. Debug builds only for now. Never publish, submit or roll out anything.
- Backups only in a hidden `.backups\` folder; never loose `.bak` files. Outdated files go to hidden `.archive\`; nothing gets deleted.
- Code, file names and in-app text in English.
- Be frugal: smallest change that works, no extra features, no heavy installs. If the JDK (17+) or Android SDK is missing on this PC, do NOT install them; write exactly what is missing in the README under "Build requirements" and in STATUS.md, and continue writing code that will build once they exist.
- This folder is its own git repo (branch `main`). Commit after each working step with clear messages. A private GitHub remote under GaryHman may be added later; do not create one yourself and do not push.
- Keep a short STATUS.md: what works, what is untested, what is blocked.