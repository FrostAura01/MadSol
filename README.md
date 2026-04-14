### MAD PRACTICAL EXAM CODES


### ⁜ Practical 4: Develop android application using View Text and Edit Text 



 ### 1] Aim: 
 Develop android application using View Text and Edit Text.
 


### 2] Resources Required:

| Sr. No. | Name of Resource | Specification | Quantity |
| :--- | :--- | :--- | :--- |
| 1 | Android enabled smartphone / Android version emulator | 4GB RAM | 1 |


### 3] Code:


activity_main.xml


```
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

### ⁜ Practical 7: Develop a program to implement Progress Bar 
<br>

### 1] Aim:
Develop a program to implement Progress Bar 
<br>
<br>

### 2] Resources Required:
<br>

| Sr. No. | Name of Resource | Specification | Quantity |
| :--- | :--- | :--- | :--- |
| 1 | Android enabled smartphone / Android version emulator | 4GB RAM | 1 |



### 3] Code:

activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="20dp">

    <ProgressBar
        android:id="@+id/progressBar"
        style="?android:attr/progressBarStyleHorizontal"
        android:layout_width="300dp"
        android:layout_height="wrap_content"
        android:max="100"
        android:progress="10" />

    <Button
        android:id="@+id/btnStart"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Start Progress"
        android:layout_marginTop="20dp" />

</LinearLayout>
```
MainActivity.java
```
package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.os.Handler;
import android.widget.Button;
import android.widget.ProgressBar;

public class MainActivity extends AppCompatActivity {

    ProgressBar progressBar;
    Button btnStart;
    int progressStatus = 0;
    Handler handle = new Handler();

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        progressBar = findViewById(R.id.progressBar);
        btnStart = findViewById(R.id.btnStart);

        btnStart.setOnClickListener(v -> {
            progressStatus = 0;
            new Thread(() -> {
                while (progressStatus < 100) {
                    progressStatus += 1;
                    
                    handle.post(() -> {
                        progressBar.setProgress(progressStatus);
                    });

                    try {
                        Thread.sleep(50);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }
            }).start();
        });
    }
}
```
### 4] Output:
<img width="472" height="637" alt="image" src="https://github.com/user-attachments/assets/e675ce87-7a59-44ae-97bd-17657d4588e8" />
<br>

### 5] Conclusion:
This Progress Bar implementation provides clear visual feedback in mobile apps, showcasing effective UI Progress tracking and user experience enhancement 
<br>
<br>
<br>
### ⁜ Practical 16: Develop a program to implement Date Picker in application 
<br>

### 1] Aim: 
Develop a program to implement Date Picker in application
<br>
<br>

### 2] Resources Required:


| Sr. No. | Name of Resource | Specification | Quantity |
| :--- | :--- | :--- | :--- |
| 1 | Android enabled smartphone / Android version emulator | 4GB RAM | 1 |


### 3] Code:
activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 android:orientation="vertical"
 android:gravity="center"
 android:padding="24dp">
 <Button
 android:id="@+id/btnPickDate"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Pick a Date" />
 <TextView
 android:id="@+id/tvDate"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="No date selected"
 android:textSize="18sp"
 android:layout_marginTop="20dp"/>
</LinearLayout>
```
MainActivity.java
```
package com.example.practical_16;
import android.app.DatePickerDialog;
import android.os.Bundle;
import android.widget.Button;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;
import java.util.Calendar;
public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 Button btn = findViewById(R.id.btnPickDate);
 TextView tv = findViewById(R.id.tvDate);
 btn.setOnClickListener(v -> {
 Calendar cal = Calendar.getInstance();
 int y = cal.get(Calendar.YEAR);
 int m = cal.get(Calendar.MONTH);
 int d = cal.get(Calendar.DAY_OF_MONTH);
 DatePickerDialog dpd = new DatePickerDialog(this,
 (view, year, month, day) ->
 tv.setText("Date: " + day + "/" + (month+1) + "/" + year),
 y, m, d);
 dpd.getDatePicker().setMinDate(cal.getTimeInMillis());
 dpd.show();
 });
 }
}
```

### 4] Output:
<img width="305" height="627" alt="image" src="https://github.com/user-attachments/assets/73a1b645-b83b-4297-b216-776d0b856a59" />

### 5] Conclusion:
This Date Picker implementation enhances mobile app usability with intuitive date selection demostrating key UI component integration and user experience design principles

