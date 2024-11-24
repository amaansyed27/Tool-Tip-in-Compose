# ToolTip in Android Studio with Kotlin Compose

This repository contains a custom implementation of a **ToolTip** for Android applications developed using **Kotlin** and **Jetpack Compose**. The project is compatible with **Android Studio Ladybug Stable** version.

## Features

- Fully customizable ToolTip design.
- Easy-to-use implementation with Compose's modern UI toolkit.
- Supports dynamic positioning and animations.
- Lightweight and performance-efficient.

## Requirements

- **Android Studio Version**: Ladybug Stable  
- **Kotlin**: Latest stable version supported by Ladybug.  
- **Jetpack Compose**: Integrated into the project for building UI.

## Configuration

### `build.gradle.kts` (Module: app)

```kotlin
plugins {
    alias(libs.plugins.android.application)
    alias(libs.plugins.kotlin.android)
    alias(libs.plugins.kotlin.compose)
}

android {
    namespace = "com.example.tooltip"
    compileSdk = 35

    defaultConfig {
        applicationId = "com.example.tooltip"
        minSdk = 24
        targetSdk = 34
        versionCode = 1
        versionName = "1.0"

        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
        }
    }
    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_11
        targetCompatibility = JavaVersion.VERSION_11
    }
    kotlinOptions {
        jvmTarget = "11"
    }
    buildFeatures {
        compose = true
    }
}

dependencies {
    implementation(libs.androidx.core.ktx)
    implementation(libs.androidx.lifecycle.runtime.ktx)
    implementation(libs.androidx.activity.compose)
    implementation(platform(libs.androidx.compose.bom))
    implementation(libs.androidx.ui)
    implementation(libs.androidx.ui.graphics)
    implementation(libs.androidx.ui.tooling.preview)
    implementation(libs.androidx.material3)
    testImplementation(libs.junit)
    androidTestImplementation(libs.androidx.junit)
    androidTestImplementation(libs.androidx.espresso.core)
    androidTestImplementation(platform(libs.androidx.compose.bom))
    androidTestImplementation(libs.androidx.ui.test.junit4)
    debugImplementation(libs.androidx.ui.tooling)
    debugImplementation(libs.androidx.ui.test.manifest)
}
