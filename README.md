
# Ex.No:5 Develop a program to create a simple calculator using Android Studio.


## AIM:

To develop a program to create a simple calculator using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as `Calculativour` and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get contacts details and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the contact name and phone number using content providers.
Developed by : Mohamed Athif Rahuman J 
Registeration Number : 212223220058
*/

package com.example.calc;

import android.os.Bundle;
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

    EditText num1, num2;
    TextView result;
    Button btnAdd, btnSub, btnMul, btnDiv;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);
        result = findViewById(R.id.result);

        btnAdd = findViewById(R.id.btnAdd);
        btnSub = findViewById(R.id.btnSub);
        btnMul = findViewById(R.id.btnMul);
        btnDiv = findViewById(R.id.btnDiv);

        btnAdd.setOnClickListener(v -> performOperation("+"));
        btnSub.setOnClickListener(v -> performOperation("-"));
        btnMul.setOnClickListener(v -> performOperation("*"));
        btnDiv.setOnClickListener(v -> performOperation("/"));
    }

    private void performOperation(String op) {
        String s1 = num1.getText().toString().trim();
        String s2 = num2.getText().toString().trim();

        if (s1.isEmpty() || s2.isEmpty()) {
            Toast.makeText(this, "Enter both numbers", Toast.LENGTH_SHORT).show();
            return;
        }

        double n1 = Double.parseDouble(s1);
        double n2 = Double.parseDouble(s2);
        double res = 0;

        switch (op) {
            case "+": res = n1 + n2; break;
            case "-": res = n1 - n2; break;
            case "*": res = n1 * n2; break;
            case "/":
                if (n2 == 0) {
                    Toast.makeText(this, "Cannot divide by zero", Toast.LENGTH_SHORT).show();
                    return;
                }
                res = n1 / n2;
                break;
        }

        result.setText("Result: " + res);
    }
}
```

## OUTPUT

#### Coding Part
<img width="1920" height="1200" alt="Screenshot (202)" src="https://github.com/user-attachments/assets/2ffa997e-4fe3-47a4-8536-392f14fc0435" />


#### Design Part
<img width="1920" height="1200" alt="Screenshot (203)" src="https://github.com/user-attachments/assets/480dcfb0-e45b-4d83-a340-599c36753513" />


#### App Image
<img width="144" height="321" alt="image" src="https://github.com/user-attachments/assets/64063160-b03f-4f0a-9031-1bfed16bbe41" />

## RESULT
Thus a Simple Calculator Application using Android Studio is developed and executed successfully.

