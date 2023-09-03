# Ex.No: 2 To develop an application that uses GUI Components with Fonts and Colors. 
Note: Create button for colors and fonts while clicking color or font button should change 


## AIM:

To create an application that uses GUI Components with Fonts and Colors using Android Studio.

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
```
/*
Program to print the text “GUIcomponent”.
Developed by: Vasanthan S R
Registeration Number : 212221220058
*/
```
activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/lay1"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#e5cafa"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/tv1"
        android:layout_width="360dp"
        android:layout_height="195dp"
        android:layout_marginTop="80dp"
        android:text="GUI Component - Dark/Light mode"
        android:textAlignment="center"
        android:textColor="#260C3B"
        android:textSize="20sp"
        android:textStyle="bold"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.49"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/toChangeColor"
        android:layout_width="154dp"
        android:layout_height="96dp"
        android:layout_marginStart="128dp"
        android:layout_marginTop="296dp"
        android:text="Button"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
Main_Activity.java
```
package com.example.guicomponent;

import androidx.appcompat.app.AppCompatActivity;
import androidx.constraintlayout.widget.ConstraintLayout;
import androidx.core.content.ContextCompat;

import android.graphics.Color;
import android.graphics.Typeface;
import android.os.Bundle;
import android.provider.CalendarContract;
import android.view.View;
import android.widget.Button;
import android.widget.LinearLayout;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    Button button1;
    ConstraintLayout layout1;
    TextView tv1;
    int count = 2;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        button1 = findViewById(R.id.toChangeColor);
        tv1 = findViewById(R.id.tv1);
        layout1 = findViewById(R.id.lay1);
        // Java
        int purpsdark = ContextCompat.getColor(this, R.color.purpsdark);
        // Java
        int purpslite = ContextCompat.getColor(this, R.color.purpslite);




        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(MainActivity.this, "color "+ Math.random(), Toast.LENGTH_SHORT).show();
                if (count % 2 == 0)
                {
                    tv1.setTextColor(Color.rgb(229, 202, 250));
                    tv1.setTypeface(Typeface.MONOSPACE);
                    tv1.setText("This is Dark Mode");
                    layout1.setBackgroundColor(purpsdark);
                    count++;
                }
                else
                {
                    tv1.setTextColor(Color.rgb(38, 12, 59));
                    tv1.setTypeface(Typeface.SANS_SERIF);
                    tv1.setText("This is Light Mode");
                    layout1.setBackgroundColor(purpslite);
                    count++;
                }
            }
        });
    }
}
```

## OUTPUT
![AM](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/36eb074a-0bbe-4fa8-90d7-e4d13f802fa6)
![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/513c280e-e80c-44ae-8686-28e976948cac)
![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/3596f228-45d7-4ae9-b308-871bdfd668ca)




## RESULT
Thus a Simple Android Application that uses GUI Components with Fonts and Colors using Android Studio is developed and executed successfully.


