### MAD PRACTICAL EXAM CODES


### Practical 4: Develop android application using View Text and Edit Text 



 ### 1] Aim: 
 Develop android application using View Text and Edit Text.
 


### 2] Resources Required:


| Sr. No. | Name of Resource                                      | Specification | Quantity | Remarks                          |
|---------|------------------------------------------------------|--------------|----------|----------------------------------|
| 1       | Android enabled smartphone / Android version emulator | 4GB RAM      | 1        | Data cable is mandatory for emulator |


### 3] Code:


activity_main.xml


```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="10dp"
    android:gravity="center"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World App"
        android:textSize="24sp"
        android:textStyle="bold"
        android:layout_marginBottom="20dp" />

    <EditText
        android:id="@+id/edittext"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter your text here"
        android:inputType="text"
        android:padding="12dp"
        android:layout_marginBottom="20dp" />

    <Button
        android:id="@+id/btn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Submit"
        android:paddingHorizontal="32dp"
        android:layout_marginBottom="20dp" />

    <TextView
        android:id="@+id/textview"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=""
        android:textSize="18sp"
        android:textColor="#000000" />

</LinearLayout>
```
MainActivity.java

```
package com.example.thi_test;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {

    EditText editText;
    Button button;
    TextView textView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.edittext);
        button = findViewById(R.id.btn);
        textView = findViewById(R.id.textview);

        button.setOnClickListener(this);
    }

    @Override
    public void onClick(View view) {
        String value = editText.getText().toString();
        textView.setText("Hello, " + value);
    }
}
```

### 4]Output:

<img width="337" height="723" alt="image" src="https://github.com/user-attachments/assets/eb58f01a-d2c4-4eaa-86fa-dbb39426deff" />

<br>

### 5] Conclusion:
Using Text View and Edit Text helps create simple interactive apps where users can enter data and see the result instantly 



<br>
<br>

### Practical 7: Develop a program to implement Progress Bar 
<br>

### 1] Aim:
Develop a program to implement Progress Bar 
<br>
<br>

### 2] Resources Required:
<br>

| Sr. No. | Name of Resource                                      | Specification | Quantity | Remarks                          |
|---------|------------------------------------------------------|--------------|----------|----------------------------------|
| 1       | Android enabled smartphone / Android version emulator | 4GB RAM      | 1        | Data cable is mandatory for emulator |

### 3] Code:






