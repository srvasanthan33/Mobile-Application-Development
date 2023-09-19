
# Ex.No:5 Create Your Own Content Providers to get Contacts details.


## AIM:

To create your own content providers to get contacts details using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as “contentprovider″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get contacts details and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the text create your own content providers to get contacts details.
Developed by: Vasanthan S R
Registration Number : 212221220058
*/
```
Activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button"
        android:layout_width="192dp"
        android:layout_height="107dp"
        android:layout_marginStart="108dp"
        android:layout_marginTop="244dp"
        android:text="Get Contacts"
        android:onClick="btnGetContactPressed"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
MainActivity.java
```
package com.example.contentprovider;

import androidx.appcompat.app.AppCompatActivity;
import androidx.core.app.ActivityCompat;
import androidx.core.content.ContextCompat;

import android.Manifest;
import android.content.ContentResolver;
import android.content.pm.PackageManager;
import android.database.Cursor;
import android.net.Uri;
import android.os.Bundle;
import android.provider.ContactsContract;
import android.util.Log;
import android.view.View;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    public void btnGetContactPressed(View v)
    {
        Toast.makeText(this, "Button Clicked", Toast.LENGTH_SHORT).show();
        getPhoneContacts();
    }
    private void getPhoneContacts()
    {
        if (ContextCompat.checkSelfPermission(this, Manifest.permission.READ_CONTACTS ) !=
                PackageManager.PERMISSION_GRANTED) {
            ActivityCompat.requestPermissions(this, new String[] {Manifest.permission.READ_CONTACTS}, 0);

            }

        ContentResolver contentResolver = getContentResolver();
        Uri uri = ContactsContract.CommonDataKinds.Phone.CONTENT_URI;
        Cursor cursor = contentResolver.query(uri,null,null,null,null);
        Log.i("CONTACT_PROVIDER_DEMO","No of Contacts ::: " + Integer.toString(cursor.getCount()));

        if (cursor.getCount() > 0)
        {
            int displayNameIndex = cursor.getColumnIndex(ContactsContract.CommonDataKinds.Phone.DISPLAY_NAME);
            int numberIndex = cursor.getColumnIndex(ContactsContract.CommonDataKinds.Phone.NUMBER);

            if (displayNameIndex > 1 && numberIndex > 1)
            {
                while (cursor.moveToNext())
                {
                    String contactName = cursor.getString(displayNameIndex);
                    String contactNumber = cursor.getString(numberIndex);

                    Log.i("CONTACT_PROVIDER_DEMO","Contact Name " + contactName + " Contact Number " + contactNumber);


                }
            }

        }
    }
}
```

## OUTPUT

![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/c7e279a1-ac0a-4ccb-9cf4-f27241795601)
![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/ac307e35-2524-483c-88e6-38d73c71f64e)
![image](https://github.com/srvasanthan33/Mobile-Application-Development/assets/102546622/64b53f78-d68e-486f-baf6-e738d8d5c405)





## RESULT
Thus a Simple Android Application create your own content providers to get contacts details using Android Studio is developed and executed successfully.
