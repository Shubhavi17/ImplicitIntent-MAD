# Ex.No:3a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: Shubhavi M
Registeration Number : 212223040199
*/
```

## Activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="25dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Implicit Intent"
        android:textSize="26sp"
        android:textStyle="bold"
        android:layout_marginBottom="40dp"/>

    <EditText
        android:id="@+id/editTextUrl"
        android:layout_width="250dp"
        android:layout_height="wrap_content"
        android:hint="Enter Website URL"
        android:inputType="textUri"/>

    <Button
        android:id="@+id/buttonNavigate"
        android:layout_width="100dp"
        android:layout_height="wrap_content"
        android:text="Search"
        android:layout_marginTop="20dp"/>

</LinearLayout>
```
## MainActivity.java
```
package com.example.implicitintent;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    EditText editTextUrl;
    Button buttonNavigate;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextUrl = findViewById(R.id.editTextUrl);
        buttonNavigate = findViewById(R.id.buttonNavigate);

        buttonNavigate.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                String url = editTextUrl.getText().toString().trim();

                if(url.isEmpty()){
                    Toast.makeText(MainActivity.this,
                            "Please enter a URL",
                            Toast.LENGTH_SHORT).show();
                    return;
                }

                if(!url.startsWith("http://") &&
                        !url.startsWith("https://")){
                    url = "https://" + url;
                }

                Intent intent = new Intent(Intent.ACTION_VIEW);
                intent.setData(Uri.parse(url));
                startActivity(intent);
            }
        });
    }
}
```

## OUTPUT
<img width="1917" height="1018" alt="Screenshot 2026-08-07 095219" src="https://github.com/user-attachments/assets/2005cfdf-d91a-4d58-84b7-a0db3c725adb" />
<img width="1917" height="1017" alt="Screenshot 2026-08-07 095232" src="https://github.com/user-attachments/assets/2a567548-a39e-41ba-adfa-f5789f80ecb0" />
<img width="1917" height="1022" alt="Screenshot 2026-08-07 095259" src="https://github.com/user-attachments/assets/9709e544-f8f2-4a1f-a765-f4975ea6382c" />

## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


