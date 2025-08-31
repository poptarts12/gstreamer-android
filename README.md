### GStreamer – Path Setup

This project uses **gstreamer-1.0-android-universal-1.20.7**.  
👉 The library was successfully integrated and builds correctly, but **real connectivity has not yet been tested**.

---

#### Set these two paths (required)

**Repo root → `gradle.properties`**
```properties
gstreamerRoot=/ABSOLUTE/PATH/to/gstreamer-1.0-android-universal-1.20.7
```

**Repo root → `local.properties` (not committed)**
```properties
gstreamer.dir=/ABSOLUTE/PATH/to/gstreamer-1.0-android-universal-1.20.7
```

**Modules reference the path (Kotlin DSL):**
```kotlin
val gstRoot = (findProperty("gstreamer.dir") ?: findProperty("gstreamerRoot")) as String
```

For all other configuration details (AAR dependency, repositories, JNI/CMake, packaging), follow the sample project:  
https://github.com/AndyHa23/gstreamer-android-samples

---

### Environment Used

- **Android SDK Build-Tools:** 36.0.0  
- **NDK (side-by-side):** 21.4.7075529  
  *(19.2.5345600 also installed)*

---

### Repository State (what was committed)

The initial commit was made **before `.gitignore` was applied**, so the repository **currently includes generated and IDE-specific files** (e.g. `**/build/`, `.gradle/`, `.idea/`, `*.iml`, and possibly `local.properties`).  
These files are **not meant to be versioned** and may inflate the repo or include machine-specific paths. They will be cleaned up in a later commit; this does **not** prevent local builds.
