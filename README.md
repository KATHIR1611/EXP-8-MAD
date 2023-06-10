# Ex.No:8 To create a gallery control using android studio to display images or photos


### AIM:

To create a gallery control using android studio to display images or photos.

### EQUIPMENTS REQUIRED:

Latest Version Android Studio

### ALGORITHM:

Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as GalleryControl and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Create a CustomizedGalleryAdapter file.

Step 7: Set the adapter for gallery in MainActivity file.

Step 8: Save and run the application.


### PROGRAM:
Program to print the text “GalleryControl”.

Developed by:Kathirvelan.K

Registeration Number : 212221220026

activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="36dp"
        app:layout_constraintBottom_toTopOf="@+id/languagesGallery"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.413"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:srcCompat="@tools:sample/avatars" />
    <Gallery
        android:id="@+id/languagesGallery"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="171dp"
        android:layout_marginBottom="204dp"
        android:animationDuration="2000"
        android:padding="10dp"
        android:spacing="5dp"
        android:unselectedAlpha="50"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView" />

</androidx.constraintlayout.widget.ConstraintLayout>

```
CustomizedGalleryAdapter.java

```
package com.example.gallerycontrol;

import android.content.Context;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class CustomizedGalleryAdapter extends BaseAdapter {
    private Context context;
    private int[] images;
    public CustomizedGalleryAdapter(Context c, int[] images) {
        context = c;
        this.images = images;
    }
    // returns the number of images, in our example it is 10
    public int getCount() {
        return images.length;
    }
    // returns the Item of an item, i.e. for our example we can get the image
    public Object getItem(int position) {
        return position;
    }
    // returns the ID of an item
    public long getItemId(int position) {
        return position;
    }
    // returns an ImageView view
    public View getView(int position, View convertView, ViewGroup parent) {
// position argument will indicate the location of image
// create a ImageView programmatically
        ImageView imageView = new ImageView(context);
// set image in ImageView
        imageView.setImageResource(images[position]);
// set ImageView param
        imageView.setLayoutParams(new Gallery.LayoutParams(200, 200));
        return imageView;
    }
}
```
MainActivity.java

```
package com.example.gallerycontrol;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.Gallery;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {
    Gallery simpleGallery;
    CustomizedGalleryAdapter customGalleryAdapter;
    ImageView selectedImageView;
    int[] images = {R.drawable.f1,R.drawable.f2,R.drawable.f3,R.drawable.f4,R.drawable.f5,R.drawable.f6};

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        simpleGallery = (Gallery) findViewById(R.id.languagesGallery);
// get the reference of ImageView
        selectedImageView = (ImageView) findViewById(R.id.imageView);
// initialize the adapter
        customGalleryAdapter = new CustomizedGalleryAdapter(getApplicationContext(), images);
// set the adapter for gallery
        simpleGallery.setAdapter(customGalleryAdapter);
// Let us do item click of gallery and image can be identified by its position
        simpleGallery.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
// Whichever image is clicked, that is set in the selectedImageView
// position will indicate the location of image
                selectedImageView.setImageResource(images[position]);
            }
        });
    }
}
```
## OUTPUT:

<img src="https://github.com/sreevarshad/EXP-8-MAD/blob/main/mmm%208.png" width=800 height=400>

<img src="https://github.com/KATHIR1611/EXP-8-MAD/blob/main/vc%201.png" width=300 height=400> <img src="https://github.com/KATHIR1611/EXP-8-MAD/blob/main/vc%202.png" width=300 height=400>
<img src="https://github.com/KATHIR1611/EXP-8-MAD/blob/main/vc%203.png" width=300 height=400>




## RESULT:
Thus a Simple Android Application to create a gallery control using android studio to display image or photos is developed and executed successfully.


