# Ex.No: 2 To develop an application that uses GUI Components with Fonts and Colors. 
Note: Create button for colors and fonts while clicking color or font button should change 
## AIM:
To create an application that uses GUI Components with Fonts and Colors using Android Studio.
## EQUIPMENTS REQUIRED:
Latest Version Android Studio
## ALGORITHM:
STEP-1 : Open Android Studio.

STEP-2 : Create a new Android project.

STEP-3 : Configure the project settings.

STEP-4 : Design the User Interface

STEP-5 : Handle UI Components in Java

STEP-6 : Initialize the UI components in the onCreate method.

STEP-7 : Define click listeners for the font and color buttons.

STEP-8 : Implement Font and Color Changing Logic

STEP-9 : Build and run the Android application on an emulator or a physical device.

STEP-10: Test the functionality by clicking the font and color buttons to see the changes applied to the sample text.
## PROGRAM:
```
/*
Program to print the text “GUIcomponent”.
Developed by:NAVEENAA V.R
Registeration Number :212221220035
*/
```
## activitymain.xml
```
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout 
xmlns:android="http://schemas.android.com/apk/res/android" 
    xmlns:app="http://schemas.android.com/apk/res-auto" 
    xmlns:tools="http://schemas.android.com/tools" 
    android:layout_width="match_parent" 
    android:layout_height="match_parent" 
    tools:context=".MainActivity"> 
 
    <TextView 
        android:id="@+id/textView" 
        android:layout_width="339dp" 
        android:layout_height="124dp" 
        android:text="GOOGLE" 
        android:fontFamily="cursive" 
        android:textAlignment="center" 
        android:textSize="80sp" 
        app:layout_constraintBottom_toBottomOf="parent" 
        app:layout_constraintEnd_toEndOf="parent" 
        app:layout_constraintStart_toStartOf="parent" 
        app:layout_constraintTop_toTopOf="parent" 
        app:layout_constraintVertical_bias="0.36" />
 <Button 
        android:id="@+id/button" 
        android:layout_width="120dp" 
        android:layout_height="120dp" 
        android:text="COLOUR" 
        app:layout_constraintBottom_toBottomOf="parent" 
        app:layout_constraintEnd_toStartOf="@+id/button2" 
        app:layout_constraintHorizontal_bias="0.515" 
        app:layout_constraintStart_toStartOf="parent" 
        app:layout_constraintTop_toTopOf="parent" 
        app:layout_constraintVertical_bias="0.706" />
<Button 
        android:id="@+id/button2" 
        android:layout_width="120dp" 
        android:layout_height="120dp" 
        android:layout_marginEnd="56dp" 
        android:text="FONT" 
        app:layout_constraintBottom_toBottomOf="parent" 
        app:layout_constraintEnd_toEndOf="parent" 
        app:layout_constraintTop_toTopOf="parent" 
        app:layout_constraintVertical_bias="0.706" /> 
</androidx.constraintlayout.widget.ConstraintLayout>
```
## MainActivity.java
```
package com.example.guiapplication; 
 
import android.graphics.Color; 
import android.graphics.Typeface; 
import android.os.Bundle; 
import android.view.View;                                                                                                                               
import android.widget.Button; 
import android.widget.TextView; 
import androidx.appcompat.app.AppCompatActivity; 
 
public class MainActivity extends AppCompatActivity { 
 
    private TextView textView; 
    private Button colorButton; 
    private Button fontButton; 
 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_main); 
 
        // Initialize UI elements 
        textView = findViewById(R.id.textView); 
        colorButton = findViewById(R.id.button); 
        fontButton = findViewById(R.id.button2); 
 
        // Set click listeners for buttons 
        colorButton.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View view) { 
                // Change text color to a random color 
                int randomColor = Color.rgb( 
                        (int)(Math.random() * 256), 
                        (int)(Math.random() * 256), 
                        (int)(Math.random() * 256) 
                );                         
                textView.setTextColor(randomColor); 
            } 
        }); 
 
        fontButton.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View view) { 
                // Change text font to a different typeface 
                Typeface newFont = Typeface.create("monospace", Typeface.BOLD); 
                textView.setTypeface(newFont); 
            } 
        }); 
    } 
}
```
## OUTPUT
![image](https://github.com/suryacse05/Mobile-Application-Development/assets/131433133/44e8aa09-1d9a-4e07-a1fc-718abf5a789e)![image](https://github.com/suryacse05/Mobile-Application-Development/assets/131433133/5dc1258b-3cb0-434b-ae24-d254ba4570f1)

## RESULT
Thus a Simple Android Application that uses GUI Components with Fonts and Colors using Android Studio is developed and executed successfully.


