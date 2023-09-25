# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by: Vasanthan S R
Registeration Number : 212221220058
*/
```
MainActivty.java
```
package com.example.workshop2_explicit_new;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    EditText et ,et2;
    Button button;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        et = findViewById(R.id.et);
        et2 = findViewById(R.id.et2);
        button = findViewById(R.id.button);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String name = et.getText().toString();
                int i1 = Integer.parseInt(name);

                int i2 = Integer.parseInt(et2.getText().toString());

                int val = i1/i2 ;

                Toast.makeText(MainActivity.this, "Computing...." + val , Toast.LENGTH_SHORT).show();
                Intent intent =  new Intent(MainActivity.this,MainActivity2.class);
                intent.putExtra("data",Integer.toString(val));
                startActivity(intent);

            }
        });
    }
}
```
MainActivity2.java
```
package com.example.workshop2_explicit_new;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity2 extends AppCompatActivity {
    Button home;

    TextView tv2_int2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        tv2_int2 = findViewById(R.id.tv2_int2);
        home = findViewById(R.id.button2);

        Intent parentIntent = getIntent();
        String data = parentIntent.getStringExtra("data");

        tv2_int2.setText("Result   "+data.toString());

        home.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {


                Intent home = new Intent(MainActivity2.this,MainActivity.class);
                startActivity(home);
            }
        });
    }
}
```

actvity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#6AB6BD"
    android:backgroundTint="#FAC1E2E6"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/et2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="252dp"
        android:backgroundTint="#4B58B5"
        android:ems="10"
        android:foregroundTint="#525FBD"
        android:inputType="text"
        android:shadowColor="#6E7BD6"
        android:text="Enter a Number"
        android:textColor="#000000"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.507"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/et"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="188dp"
        android:backgroundTint="#4B58B5"
        android:ems="10"
        android:foregroundTint="#525FBD"
        android:inputType="text"
        android:shadowColor="#6E7BD6"
        android:text="Enter a Number"
        android:textColor="#000000"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="136dp"
        android:layout_marginTop="116dp"
        android:background="#7fffd4"
        android:backgroundTint="#3DB8C3"
        android:text="Compute"
        app:icon="@android:drawable/btn_star"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/et"
        app:rippleColor="#AD1457" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="72dp"
        android:background="#D4EEF1"
        android:text="Welcome to V's App"
        android:textAlignment="center"
        android:textColor="#00838F"
        android:textSize="24sp"
        android:textStyle="bold"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="209dp"
        android:layout_height="197dp"
        android:layout_marginStart="100dp"
        android:layout_marginBottom="72dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:srcCompat="@drawable/happycat" />

    <TextView
        android:id="@+id/textView3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="44dp"
        android:layout_marginTop="188dp"
        android:text="1."
        android:textSize="24sp"
        app:layout_constraintEnd_toStartOf="@+id/et"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:text="1." />

    <TextView
        android:id="@+id/textView4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="44dp"
        android:layout_marginTop="268dp"
        android:text="2."
        android:textSize="24sp"
        app:layout_constraintEnd_toStartOf="@+id/et2"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:text="2." />
</androidx.constraintlayout.widget.ConstraintLayout>
```

activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2">

    <TextView
        android:id="@+id/tv1_int2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="156dp"
        android:text="Second Activity"
        android:textSize="24sp"
        android:textStyle="bold"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="148dp"
        android:layout_marginTop="180dp"
        android:text="Home"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/tv1_int2" />

    <TextView
        android:id="@+id/tv2_int2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="148dp"
        android:layout_marginTop="272dp"
        android:text="Result"
        android:textSize="24sp"
        android:textStyle="bold"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

## OUTPUT

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/58b96a23-1c5d-4c6b-bbab-40e66bfe63e3)

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/dbe898b5-222c-4066-b4e0-451b497d45fc)

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/b378dffd-19be-4bf8-9856-011df33a61f0)





## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.


