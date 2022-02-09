# MediaPickerProject

[Cordova](https://github.com/DmcSDK/cordova-plugin-mediaPicker) : https://github.com/DmcSDK/cordova-plugin-mediaPicker 

[IOS](https://github.com/DmcSDK/IOSMediaPicker) : https://github.com/DmcSDK/IOSMediaPicker

use Gradle:

```gradle
repositories {
    mavenCentral() // jcenter() works as well because it pulls from Maven Central
}

dependencies {
    compile 'com.dmcBig:mediapicker:+'
}
```

code:
```
    ArrayList<Media> select = new ArrayList<>();
    void go(){
        Intent intent =new Intent(MainActivity.this, PickerActivity.class);
        intent.putExtra(PickerConfig.SELECT_MODE,PickerConfig.PICKER_IMAGE_VIDEO);
        long maxSize=188743680L;//long long long long
        intent.putExtra(PickerConfig.MAX_SELECT_SIZE,maxSize); 
        intent.putExtra(PickerConfig.MAX_SELECT_COUNT,15);  
        ArrayList<Media> defaultSelect = select;
        intent.putExtra(PickerConfig.DEFAULT_SELECTED_LIST,defaultSelect); 
        MainActivity.this.startActivityForResult(intent,200);
    }

    @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if(requestCode==200&&resultCode==PickerConfig.RESULT_CODE){
            select=data.getParcelableArrayListExtra(PickerConfig.EXTRA_RESULT);
        }
    }
    
    
    // Intent intent =new Intent(MainActivity.this, TakePhotoActivity.class); //Take a photo with a camera
    // MainActivity.this.startActivityForResult(intent,200);
```    

# Screenshots
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots1.png)
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots2.png)
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots3.png)
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots4.png)
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots5.png)
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots6.png)
