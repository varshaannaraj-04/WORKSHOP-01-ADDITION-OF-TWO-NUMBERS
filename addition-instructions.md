# WORKSHOP-01-ADDITION-OF-TWO-NUMBERS
# Objective
To create a simple Android application that accepts two numbers from the user, performs addition, and displays the summation result in a text box.
# Description

This Android application allows the user to:
1. Enter two numeric values.
2. Click the Add button.
3. Display the summation result in a text box.

The application demonstrates:
1. User input handling
2. Button click events
3. Basic arithmetic operations
4. Displaying output in Android UI components

# Algorithm – Addition of Two Numbers Android Application
1. Start the application.
2. Create the user interface with:
   * Two input text boxes for numbers
   * One button for addition
   * One text view/text box to display the result
3. Enter the first number.
4. Enter the second number.
5. Click the ADD button.
6. Read the values from both input fields.
7. Convert the entered values into integer numbers.
8. Perform addition: Sum=Number1+Number2
9. Display the summation result in the result text box.
10. Stop the application.

# Program
Name : VARSHA A

Register No : 212223220121

# Main Activity.java
```
package com.example.additionof2num;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {

    private EditText etNum1, etNum2;
    private Button btnAdd;
    private TextView tvResult;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });

        etNum1 = findViewById(R.id.num1);
        etNum2 = findViewById(R.id.num2);
        btnAdd = findViewById(R.id.btnAdd);
        tvResult = findViewById(R.id.tvResult);

        btnAdd.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                calculateSum();
            }
        });
    }

    private void calculateSum() {
        String s1 = etNum1.getText().toString();
        String s2 = etNum2.getText().toString();

        if (s1.isEmpty() || s2.isEmpty()) {
            Toast.makeText(this, "Please enter both numbers", Toast.LENGTH_SHORT).show();
            return;
        }

        try {
            double n1 = Double.parseDouble(s1);
            double n2 = Double.parseDouble(s2);
            double sum = n1 + n2;
            tvResult.setText("Result: " + sum);
        } catch (NumberFormatException e) {
            Toast.makeText(this, "Invalid input", Toast.LENGTH_SHORT).show();
        }
    }
}
```

# activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/num1"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:textSize="20sp"
        android:layout_margin="16dp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

    <EditText
        android:id="@+id/num2"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:textSize="20sp"
        android:layout_margin="16dp"
        app:layout_constraintTop_toBottomOf="@id/num1"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

    <Button
        android:id="@+id/btnAdd"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Add"
        android:textSize="20sp"
        android:layout_marginTop="16dp"
        app:layout_constraintTop_toBottomOf="@id/num2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />
    <TextView
        android:id="@+id/tvResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Result will appear here"
        android:textSize="24sp"
        android:layout_marginTop="24dp"
        app:layout_constraintTop_toBottomOf="@id/btnAdd"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

# Output 
<img width="1920" height="1080" alt="muid ws" src="https://github.com/user-attachments/assets/68f63ebc-ebf1-49a5-9f4e-3a2fa3d4edf3" />
<img width="1920" height="1080" alt="muid ws add" src="https://github.com/user-attachments/assets/6a303ea9-69ba-4225-8b30-c99ec1879fa4" />

# Result
The Android application was successfully developed using Android Studio. 
The app accepts two input values, performs addition, and displays the result dynamically in the text box.
