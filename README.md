# Android-Buttons
Buttons in Android 
A button consists of text or an icon (or both text and an icon) that communicates what action occurs when the user touches it.
There are two ways of using buttons in android
  1) onClick
      In the XML file
  2) OnClickListener
      In the MainActivity java file
  
  In the code I gave below, the first button(id= button1) is by onclick and the second one(id= button2) is by OnClickListener
  
  ************Code in the XML File is***************
  
  <?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="395dp"
        android:layout_height="715dp"
        android:orientation="vertical"
        tools:layout_editor_absoluteX="8dp"
        tools:layout_editor_absoluteY="8dp">

        <Button
            android:id="@+id/button1"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="OnClick"
            android:onClick="displayToastMsg" />

        <Button
            android:id="@+id/button2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="OnClickListener" />
    </LinearLayout>
</androidx.constraintlayout.widget.ConstraintLayout>


*********Code in the MainActivity java file***********

package com.example.buttonbasic;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.app.Activity;
import android.view.View;
import android.widget.Toast;
import android.widget.Button;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        final Button button = findViewById(R.id.button2);
        button.setOnClickListener(new View.OnClickListener() {
            public void onClick(View v) {
                Toast.makeText(getApplicationContext(),
                        "Button2 is clicked", Toast.LENGTH_LONG).show();
            }
        });
    }
    public void displayToastMsg(View v)
    {
        Button button1 = (Button) v;
        ((Button) v).setText("Clicked");
        Toast.makeText(getApplicationContext(),
                "Button1 is clicked", Toast.LENGTH_LONG).show();
    }

}
