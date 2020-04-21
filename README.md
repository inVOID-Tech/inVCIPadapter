# inVCIPadaptor
VCIP Web View Adaptor for Android

## Minimum Requirements
- `minSdkVersion 21` 
- `AndroidX`

## Getting Started

Add following lines in your root ```build.gradle```
```
allprojects {
    repositories {
        ...
        maven { url "https://dl.bintray.com/invoidandroid12/android/" }
    }
}
```

Add following lines in your module level ```build.gradle```
```
dependencies {
    ....
    implementation 'co.invoid.android:videokycandroid:1.0.0rc'
}
```

This library also uses some common android libraries. So if you are not already using them then make sure you add these libraries to your module level `build.gradle`
- `androidx.appcompat:appcompat:1.1.0`

## Initialize SDK

```
VideoKycHelper.start(YourActivity.this);
```
