# DEVELOPING-ENERGY-CONSUMPTION-CALCULATOR-APPLICATION.-

## AIM:
To develop an android application to perform energy calculation.

## APPARATUS REQUIRED:
ØComputer
ØAndroid studio software


## THEORY:
The Energy Calculator App allows the user to calculate the energy consumption of electrical appliances based on power usage (in watts) and time (in hours). The app takes these two inputs, calculates the energy consumed in kilowatt-hours (kWh), and displays the result. This experiment involves basic arithmetic calculations and user input handling in Android. It uses EditText for input, Button for user interaction, and TextView to display the result. The app demonstrates how to handle user input for numerical values and perform unit conversions. It is a useful application for understanding how to develop apps that perform mathematical calculations based on user input.

## PROCEDURE:
1. Open Android Studio and then click on File -> New -> New project. 24. Then type the application name as “ex.no.3″ and click Next.
2. Then select the Minimum SDK as shown below and click next. 26. Then select the Empty Activity and click next.
3. Finally click Finish.
4. Click on app -> java -> com.example -> MainActivity.java
5. Now click on Text and type the program, so now the programming part of the main activity is completed.
6. Click on app -> res -> layout -> activity_main.xml.
7. Now click on Text and type the program, so now the designing part of Activity main is also completed.
8. Select the suitable available device to display the output. 33. Now run the application to see the output. 

## PROGRAM:
### MainActivity.java
```
package com.example.energycalculator;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private EditText wattsInput, hoursInput;
    private Button calculateButton;
    private TextView resultView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        wattsInput = findViewById(R.id.watts);
        hoursInput = findViewById(R.id.hours);
        calculateButton = findViewById(R.id.calc);
        resultView = findViewById(R.id.result);

        calculateButton.setOnClickListener(v -> calculateEnergy());
    }

    private void calculateEnergy() {
        String wattsText = wattsInput.getText().toString().trim();
        String hoursText = hoursInput.getText().toString().trim();

        if (wattsText.isEmpty() || hoursText.isEmpty()) {
            Toast.makeText(this, "Please enter both values", Toast.LENGTH_SHORT).show();
            return;
        }

        double watts = Double.parseDouble(wattsText);
        double hours = Double.parseDouble(hoursText);

        double energyUsed = (watts * hours) / 1000.0;
        resultView.setText("Energy Used: " + energyUsed + " kWh");
    }
}
```

### activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="24dp"
    android:gravity="center_horizontal"
    android:background="#FAFAFA">

    <EditText
        android:id="@+id/watts"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Power (Watts)"
        android:inputType="numberDecimal"
        android:layout_marginBottom="12dp"
        android:padding="12dp"
        android:background="@android:drawable/edit_text"
        android:textSize="16sp" />

    <EditText
        android:id="@+id/hours"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Time (Hours)"
        android:inputType="numberDecimal"
        android:layout_marginBottom="16dp"
        android:padding="12dp"
        android:background="@android:drawable/edit_text"
        android:textSize="16sp" />

    <Button
        android:id="@+id/calc"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Calculate Energy"
        android:padding="12dp"
        android:backgroundTint="#6200EE"
        android:textColor="#FFFFFF"
        android:textStyle="bold"
        android:elevation="4dp" />

    <TextView
        android:id="@+id/result"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="24dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="#212121"
        android:gravity="center_horizontal" />

</LinearLayout>
```
## OUTPUT:
<img width="1920" height="1020" alt="Screenshot 2025-10-07 155419" src="https://github.com/user-attachments/assets/5ab974ce-deb1-4a5f-87a6-003cbcf17a68" />

## RESULT:
Thus, the energy consumption calculator app is developed and the output is verified. 

