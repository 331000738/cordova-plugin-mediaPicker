# cordova-plugin-mediaPicker
android  mediaPicker support  selection of multiple image and video 

How do I use?
-------------------

use npm:

```npm
    cordova-plugin-mediapicker-dmcbig
```

code:

    ArrayList<Media> select;
    void go(){
        Intent intent =new Intent(MainActivity.this, PickerActivity.class);
        intent.putExtra(PickerConfig.SELECT_MODE,PickerConfig.PICKER_IMAGE_VIDEO);//default image and video (Optional)
        long maxSize=188743680L;//long long long
        intent.putExtra(PickerConfig.MAX_SELECT_SIZE,maxSize); //default 180MB (Optional)
        intent.putExtra(PickerConfig.MAX_SELECT_COUNT,15);  //default 40 (Optional)
        intent.putExtra(PickerConfig.DEFAULT_SELECTED_LIST,select); // (Optional)
        MainActivity.this.startActivityForResult(intent,200);
    }

    @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if(requestCode==200&&resultCode==PickerConfig.RESULT_CODE){
            select=data.getParcelableArrayListExtra(PickerConfig.EXTRA_RESULT);
        }
    }

# Example
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots1.png)
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots2.png)
![](https://github.com/dmcBig/MediaPickerPoject/blob/master/Screenshots/Screenshots3.png)
