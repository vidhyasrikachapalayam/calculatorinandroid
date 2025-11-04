## Ex_5_-Develop a simple calculator using android studio.
Develop a program to create a simple calculator using Android Studio.

## AIM:
To develop a program to create a simple calculator using Android Studio.

## EQUIPMENTS REQUIRED:
Android Studio(Min. required Artic Fox)

## ALGORITHM:
Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as SMSIntent and click Next.

Step 3: Select the Minimum SDK below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally, click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Perform the Calculator Operation in MainActivity.java

Step 7: Save and run the application.

## Program:
```
/*
Program to create simple calculator using Android Studio.
Developed by: Vidhyasri K
RegisterNumber: 212222230170
*/
```

## MainActivity.java:
```
package com.example.calculatorapp;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    EditText etNum1, etNum2;
    TextView tvResult;
    Button btnAdd, btnSub, btnMul, btnDiv;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        etNum1 = findViewById(R.id.etNum1);
        etNum2 = findViewById(R.id.etNum2);
        tvResult = findViewById(R.id.tvResult);

        btnAdd = findViewById(R.id.btnAdd);
        btnSub = findViewById(R.id.btnSub);
        btnMul = findViewById(R.id.btnMul);
        btnDiv = findViewById(R.id.btnDiv);

        btnAdd.setOnClickListener(v -> calculate("+"));
        btnSub.setOnClickListener(v -> calculate("-"));
        btnMul.setOnClickListener(v -> calculate("*"));
        btnDiv.setOnClickListener(v -> calculate("/"));
    }

    private void calculate(String op) {
        String n1 = etNum1.getText().toString();
        String n2 = etNum2.getText().toString();

        if (n1.isEmpty() || n2.isEmpty()) {
            tvResult.setText("Please enter numbers");
            return;
        }

        double a = Double.parseDouble(n1);
        double b = Double.parseDouble(n2);
        double res = 0;

        switch (op) {
            case "+": res = a + b; break;
            case "-": res = a - b; break;
            case "*": res = a * b; break;
            case "/":
                if (b != 0) res = a / b;
                else { tvResult.setText("Cannot divide by 0"); return; }
                break;
        }
        tvResult.setText(n1 + " " + op + " " + n2 + " = "+res);
    }
}
```

## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="16dp"
    android:background="#FFF0F5">

    <!-- Title -->

    <!-- First Number -->
    <TextView
        android:id="@+id/tvTitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="20dp"
        android:text="Calculator"
        android:textSize="24sp"
        android:textStyle="bold" />

    <EditText
        android:id="@+id/etNum1"
        android:layout_width="222dp"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:hint="Enter first number"
        android:inputType="numberDecimal" />

    <!-- Second Number -->
    <EditText
        android:id="@+id/etNum2"
        android:layout_width="217dp"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:hint="Enter second number"
        android:inputType="numberDecimal" />

    <!-- Result -->

    <!-- Buttons -->

    <TextView
        android:id="@+id/tvResult"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"
        android:background="#FFFFFF"
        android:gravity="center"
        android:padding="10dp"
        android:text="Result"
        android:textSize="18sp" />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center"
        android:layout_marginTop="20dp">

        <Button
            android:id="@+id/btnSub"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:backgroundTint="#FF6666"
            android:text="-" />

        <Button
            android:id="@+id/btnAdd"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:backgroundTint="#FF6666"
            android:text="+" />

    </LinearLayout>

    <Button
        android:id="@+id/btnMul"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="5dp"
        android:backgroundTint="#FF6666"
        android:text="x" />

    <Button
        android:id="@+id/btnDiv"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="5dp"
        android:backgroundTint="#FF6666"
        android:text="/" />
</LinearLayout>
AndroidMainfest.xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.CalculatorApp">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

## Output:
<img width="1026" height="528" alt="image" src="https://github.com/user-attachments/assets/a3450f62-9b9c-409d-872e-3f2619b8f1af" />

## Result:
Thus a Simple Android Application to create a calculator using Android Studio was developed and executed successfully.
