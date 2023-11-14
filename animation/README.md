# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.
## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:
Step1: Start the program

Step2: Create a necessary xml files

Step3: Import the necessary packages and libraries.

Step4: Create a class named MainActivity that extends AppCompatActivity.

Step5: Declare ImageView and Button variables for the views in the layout.

Step6: Override the onCreate() method and set the content view to the activity_main layout.

Step7: Initialize the ImageView and Button variables by finding them using their IDs.

Step8: Set click listeners for each button to handle the animation actions.

Step9: End the click listeners.

Step10: End the onCreate() method.

Step11: End the program.

## PROGRAM:
```
/*
Program to display animation operation”.
Developed by:NAVEENAA V.R
Registeration Number :212221220035
*/
```
## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button16"
        android:layout_width="130dp"
        android:layout_height="wrap_content"
        android:text="CLOCKWISE"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.794"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.829" />

    <Button
        android:id="@+id/button18"
        android:layout_width="130dp"
        android:layout_height="wrap_content"
        android:text="SLIDE"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.794"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.925" />

    <Button
        android:id="@+id/button17"
        android:layout_width="130dp"
        android:layout_height="wrap_content"
        android:text="ZOOM"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.167"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.925" />

    <ImageView
        android:id="@+id/imageView2"
        android:layout_width="328dp"
        android:layout_height="466dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.492"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.134"
        app:srcCompat="@drawable/android" />

    <Button
        android:id="@+id/button13"
        android:layout_width="130dp"
        android:layout_height="wrap_content"
        android:text="MOVE"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.167"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.738" />

    <Button
        android:id="@+id/button14"
        android:layout_width="130dp"
        android:layout_height="wrap_content"
        android:text="FADE"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.798"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.738" />

    <Button
        android:id="@+id/button15"
        android:layout_width="130dp"
        android:layout_height="wrap_content"
        android:text="BLINK"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.167"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.829" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
## MainActivity.java
```
package com.example.animation;
import android.os.Bundle;
import android.view.View;
import android.view.animation.AlphaAnimation;
import android.view.animation.Animation;
import android.view.animation.RotateAnimation;
import android.view.animation.ScaleAnimation;
import android.view.animation.TranslateAnimation;
import android.widget.Button;
import android.widget.ImageView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    private ImageView imageView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageView2);

        Button moveButton = findViewById(R.id.button13);
        moveButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Move animation
                TranslateAnimation animation = new TranslateAnimation(0, 200, 0, 0);
                animation.setDuration(1000);
                imageView.startAnimation(animation);
            }
        });

        Button blinkButton = findViewById(R.id.button15);
        blinkButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Blink animation
                Animation animation = new AlphaAnimation(1, 0);
                animation.setDuration(500);
                animation.setRepeatMode(Animation.REVERSE);
                animation.setRepeatCount(Animation.INFINITE);
                imageView.startAnimation(animation);
            }
        });

        Button fadeButton = findViewById(R.id.button14);
        fadeButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Fade animation
                Animation animation = new AlphaAnimation(1, 0);
                animation.setDuration(1000);
                imageView.startAnimation(animation);
            }
        });

        Button clockwiseButton = findViewById(R.id.button16);
        clockwiseButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Rotate clockwise animation
                RotateAnimation animation = new RotateAnimation(0, 360,
                        Animation.RELATIVE_TO_SELF, 0.5f,
                        Animation.RELATIVE_TO_SELF, 0.5f);
                animation.setDuration(1000);
                imageView.startAnimation(animation);
            }
        });

        Button zoomButton = findViewById(R.id.button17);
        zoomButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Zoom animation
                Animation animation = new ScaleAnimation(1, 2, 1, 2,
                        Animation.RELATIVE_TO_SELF, 0.5f,
                        Animation.RELATIVE_TO_SELF, 0.5f);
                animation.setDuration(1000);
                imageView.startAnimation(animation);
            }
        });

        Button slideButton = findViewById(R.id.button18);
        slideButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Slide animation
                TranslateAnimation animation = new TranslateAnimation(0, 200, 0, 0);
                animation.setDuration(1000);
                imageView.startAnimation(animation);
            }
        });
}
}
```
## OUTPUT
![image](https://github.com/suryacse05/Mobile-Application-Development/assets/131433133/b869b090-6ffe-41de-8b14-e3d4318e7d23)
## RESULT
Thus a Simple Android Application develop to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio is developed and executed successfully.
