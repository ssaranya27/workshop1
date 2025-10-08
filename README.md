# workshop1 : Addition of Two Numbers using Android Studio

## AIM :
    To develop an Android application that takes two numbers as input, adds them, and displays the result in a text box.
## Steps:
1. **Open Android Studio.**

2. **Create a new project** → Choose **Empty Activity** template.

3. **Set application name** (e.g., *AdditionApp*) and choose **Java** as the programming language.

4. **Design the user interface** in `activity_main.xml`:

   * Add two **EditText** fields for entering numbers.
   * Add one **Button** labeled **Add Numbers**.
   * Add one **TextView** to display the result.

5. **Open `MainActivity.java`** file and do the following:

   * Link all UI components using `findViewById()`.
   * Get input values from EditText fields.
   * Convert string inputs to numeric values.
   * Perform the addition operation.
   * Display the result in the TextView.

6. **Modify `AndroidManifest.xml`**:

   * Add the line `android:exported="true"` inside the `<activity>` tag.

7. **Save and build the project.**

8. **Run the application** on an emulator or Android device.

9. **Enter two numbers** in the input boxes.

10. **Click the Add button** to display the result (sum of the two numbers).

## PROGRAM:

```
PROGRAM DEVELOPED BY: SARANYA S.
REGISTER NUMBER: 212223220101

```
ACTIVITYMAIN.JAVA
```
package com.example.additionapp;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    EditText num1, num2;
    Button addButton;
    TextView resultText;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);
        addButton = findViewById(R.id.addButton);
        resultText = findViewById(R.id.resultText);

        addButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String n1 = num1.getText().toString();
                String n2 = num2.getText().toString();

                if (n1.isEmpty() || n2.isEmpty()) {
                    Toast.makeText(MainActivity.this, "Please enter both numbers", Toast.LENGTH_SHORT).show();
                } else {
                    double number1 = Double.parseDouble(n1);
                    double number2 = Double.parseDouble(n2);
                    double sum = number1 + number2;

                    resultText.setText("Result: " + sum);
                }
            }
        });
    }
}
```
activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:padding="24dp"
    android:background="#FAFAFA">

    <EditText
        android:id="@+id/num1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:padding="12dp"
        android:layout_marginBottom="12dp"
        android:background="@android:drawable/edit_text" />

    <EditText
        android:id="@+id/num2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:padding="12dp"
        android:layout_marginBottom="12dp"
        android:background="@android:drawable/edit_text" />

    <Button
        android:id="@+id/addButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Add Numbers"
        android:textAllCaps="false"
        android:padding="12dp"
        android:backgroundTint="#4CAF50"
        android:textColor="#FFFFFF"
        android:layout_marginBottom="12dp" />

    <TextView
        android:id="@+id/resultText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Result will appear here"
        android:textSize="18sp"
        android:textColor="#000000"
        android:gravity="center" />
</LinearLayout>
```
ANDROIDMANIFEST.XML

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.additionapp">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/Theme.AdditionApp">

        <activity
            android:name=".MainActivity"
            android:exported="true">   <!-- ✅ Add this line -->
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>

</manifest>
```
## OUTPUT:

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2d7d4a33-e4fe-4efd-804c-b226864c8530" />


##  **Result:**

The Android application to add two numbers and display the result was successfully created and executed.
