# Ex.No:10 To create a option menu to display menu items.
## AIM:
To create a option menu to display menu items using Android Studio.
## EQUIPMENTS REQUIRED:
Latest Version Android Studio
## ALGORITHM:
Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as OptionMenu and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Create a option.xml file to create options in your menu.

Step 7: Display options in MainActivity file.

Step 8: Save and run the application.
## PROGRAM:
## activtity_main.xml:
~~~
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"/>
option.xml:

<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:title="@string/item_1" />
    <item android:title="@string/item_2" />
    <item android:title="@string/item_3" />
</menu>
~~~
## MainActivity.java:
~~~
package com.example.optionmenu;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.Menu;
import android.view.MenuInflater;

import com.example.optionmenu.R;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        MenuInflater m = getMenuInflater();
        m.inflate(R.menu.option,menu);
        return true;
    }
}
~~~
## OUTPUT
![image](https://github.com/PREETHI-B0/Mobile-Application-Development/assets/136311079/2194a683-7b1e-48d0-8e8c-0d8ec769b399)
![image](https://github.com/PREETHI-B0/Mobile-Application-Development/assets/136311079/f910c937-548d-4efd-9401-07f93f588aed)
## RESULT
Thus a Simple Android Application to create a option menu to display menu items using Android Studio is developed and executed successfully.


