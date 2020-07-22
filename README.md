# inVCIPadaptor
VIDEO KYC VCIP Web View Adapter for Android

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
    implementation 'co.invoid.android:videokycandroid:1.0.3rc'
}
```

This library also uses some common android libraries. So if you are not already using them then make sure you add these libraries to your module level `build.gradle`
- `androidx.appcompat:appcompat:1.1.0`

## Initialize SDK

```
VideoKycHelper.start(YourActivity.this, "Unique url of user");
```
## Callback from SDK
```
@Override
protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
    super.onActivityResult(requestCode, resultCode, data);

    if(requestCode == VideoKycHelper.REQUEST_CODE) {
            
        if(resultCode == VideoKycHelper.RESULT_OK) {
            Log.i(TAG, "Succcess");
            
        } else if(resultCode == VideoKycHelper.RESULT_ERROR) {
            String errorMessage = data.getStringExtra(VideoKycHelper.ERROR_MSG);
            Log.i(TAG, "Error: message: "+errorMessage);
            
        } else if(resultCode == VideoKycHelper.RESULT_CANCELLED) {
            Log.i(TAG, "Cancelled by user");
        }
    }
}
```
