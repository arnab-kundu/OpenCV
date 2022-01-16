# OpenCV
## Setup OpenCV in Android
Follow the below steps to setup an OpenCV project in Android
### Download OpenCV SDK
1. Open the official website of **[OpenCV](https://opencv.org/)** i.e. https://opencv.org/
2. Goto **Library** -> **Releases**
3. Under OpenCV-4.5.5 -> **[Android](https://sourceforge.net/projects/opencvlibrary/files/4.5.5/opencv-4.5.5-android-sdk.zip/download)**
4. A zip file will be downloaded with the name like `opencv-4.5.5-android-sdk.zip` in your **Downloads** folder

### Setup OpenCV SDK
1. **Extract** the `opencv-4.5.5-android-sdk.zip` file
2. Now locate the **OpenCV SDK** in this path `C:\Users\<your_user_name>\Downloads\opencv-4.5.5-android-sdk\OpenCV-android-sdk\sdk`
3. **Copy** the **SDK** folder
4. **Paste** into the **AndroidStudioProjects** folder in this path `C:\Users\<your_user_name>\AndroidStudioProjects`

### Setup Android Studio Project
1. **Create a new project** in Android Studio with `<your_opencv_android_project_name>`
2. Select language as **Kotlin**
2. Open `settings.gradle` file in `<your_opencv_android_project_name>` and paste this lines of code and sync project
```
def opencvsdk='../'
//def opencvsdk='/<path to OpenCV-android-sdk>'
//println opencvsdk
include ':opencv'
project(':opencv').projectDir = new File(opencvsdk + '/sdk')
```
3. Open **MainActivity.kt** and write this lines of code in `onCreate()` to verify **OpenCV SDK** working
```
 if (!OpenCVLoader.initDebug()) {
    Log.e(TAG, "Internal OpenCV library not found. Using OpenCV Manager for initialization")
    OpenCVLoader.initAsync(OpenCVLoader.OPENCV_VERSION_3_0_0, this, mLoaderCallback)
} else {
    Log.d(TAG, "OpenCV library found inside package. Using it!")
}
```
4. Run the project now in an emulator or in a Physical device and check the logs.
### Prerequisite
1. Need to have latest stable **Android Studio version** installed.

```
Android Studio Arctic Fox | 2020.3.1 Patch 3
Build #AI-203.7717.56.2031.7784292, built on October 1, 2021

```
## Become a master 
This is a step by step guide line to become a master for OpenCV in Android.

1. You will have a sample android project in [OpenCV SDK(4.5.5)](https://sourceforge.net/projects/opencvlibrary/files/4.5.5/opencv-4.5.5-android-sdk.zip/download)  
2. Check out this path `C:\Users\<your_user_name>\Downloads\opencv-4.5.5-android-sdk\OpenCV-android-sdk\samples` for the sample android project
3. To run **OpenCV sample project** use **Android Studio 4.2**
4. Follow one by one this modules in the SampleProject in this flowing order   
    a. tutorial-1-camerapreview     
    b. tutorial-2-mixedprocessing   
    c. tutorial-3-cameracontrol     
    d. camera-calibration       
    e. image-manipulations      
    f. color-blob-detection     
    g. face-detection   
    h. 15-puzzle
