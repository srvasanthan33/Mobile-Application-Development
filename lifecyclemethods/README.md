# Ex.No:1 To create a HelloWorld Activity using all lifecycles methods to display messages.


## AIM:

To create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

Main_activity.java
```
package com.example.androidlifecycles;

import static androidx.constraintlayout.helper.widget.MotionEffect.TAG;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.util.Log;
import android.widget.Toast;


public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Toast.makeText(getApplicationContext(),"onCreate called",Toast.LENGTH_LONG).show();
        Log.d("Vasanthan","on create called");

    }
    @Override
    protected void onStart() {
        super.onStart();
        Toast.makeText(getApplicationContext(), "onStart Called", Toast.LENGTH_LONG).show();
        Log.d("Vasanthan","on start called");
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        Toast.makeText(getApplicationContext(), "onRestart Called", Toast.LENGTH_LONG).show();
        Log.d("Vasanthan","on Restart called");
    }
    @Override
    protected void onPause() {
        super.onPause();
        Toast.makeText(getApplicationContext(), "onPause Called", Toast.LENGTH_LONG).show();
        Log.d("Vasanthan","on pause called");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Toast.makeText(getApplicationContext(), "onResume Called", Toast.LENGTH_LONG).show();
        Log.d("Vasanthan","on resume called");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Toast.makeText(getApplicationContext(), "onStop Called", Toast.LENGTH_LONG).show();
        Log.d("Vasanthan","on stop called");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Toast.makeText(getApplicationContext(), "onDestroy Called", Toast.LENGTH_LONG).show();
        Log.d("Vasanthan","on destroy called");
    }




}
```

Program created by 
Vasanthan S R
212221220058

## OUTPUT

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/a731e1db-c81f-439a-b597-99c9f8cc462d)

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/46215534-a280-4940-b450-3225f1200853)

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/25b9b348-892c-4c8b-9912-0d9e9bc2c458)

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/c37c4b4a-c617-48dd-b71e-5b3805994d16)

<img width="766" alt="image" src="https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/f50174ab-2be7-402b-82f9-87795b0fd233">

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/94ae575a-1288-4c98-98ba-a0a782234e2f)

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/5adb470c-4c76-4afa-a1f2-7e47ef189a61)

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/0ff4f893-1670-4e96-be4f-edb85eb41a30)

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/8eee206e-a805-4a84-a6d9-bd8401d52468)






## RESULT
Thus a Simple Android Application create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio is developed and executed successfully.
