# Workshop-MAD

# CODE

# MAINACTIVITY.JAVA

```JAVA
package com.example.workshop;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    private EditText editTextName, editTextAge, editTextEmail, editTextContact;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextName = findViewById(R.id.editTextName);
        editTextAge = findViewById(R.id.editTextAge);
        editTextEmail = findViewById(R.id.editTextEmail);
        editTextContact = findViewById(R.id.editTextContact);

        Button buttonSubmit = findViewById(R.id.buttonSubmit);

        buttonSubmit.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String name = editTextName.getText().toString();
                String age = editTextAge.getText().toString();
                String email = editTextEmail.getText().toString();
                String contact = editTextContact.getText().toString();

                Intent intent = new Intent(MainActivity.this, MainActivity2.class);
                intent.putExtra("name", name);
                intent.putExtra("age", age);
                intent.putExtra("email", email);
                intent.putExtra("contact", contact);
                startActivity(intent);
            }
        });
    }
}
```
# MAINACTIVITY2.JAVA
```JAVA
package com.example.workshop;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;

public class MainActivity2 extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        TextView textViewName = findViewById(R.id.textViewName);
        TextView textViewAge = findViewById(R.id.textViewAge);
        TextView textViewEmail = findViewById(R.id.textViewEmail);
        TextView textViewContact = findViewById(R.id.textViewContact);

        Intent intent = getIntent();

        if (intent != null) {
            String name = intent.getStringExtra("name");
            String age = intent.getStringExtra("age");
            String email = intent.getStringExtra("email");
            String contact = intent.getStringExtra("contact");

            textViewName.setText("Name: " + name);
            textViewAge.setText("Age: " + age);
            textViewEmail.setText("Email: " + email);
            textViewContact.setText("Contact: " + contact);
        }
    }
}
```
# ACTIVITY_MAIN.XML

```XML
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <EditText
            android:id="@+id/editTextName"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter Name" />

        <EditText
            android:id="@+id/editTextAge"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/editTextName"
            android:hint="Enter Age" />

        <EditText
            android:id="@+id/editTextEmail"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/editTextAge"
            android:hint="Enter Email" />

        <EditText
            android:id="@+id/editTextContact"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/editTextEmail"
            android:hint="Enter Contact Number" />

        <Button
            android:id="@+id/buttonSubmit"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@id/editTextContact"
            android:layout_centerHorizontal="true"
            android:text="Submit" />
    </RelativeLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```

# ACTIVITY2_MAIN.XML

```XML
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="16dp"
        android:layout_centerInParent="true">

        <TextView
            android:id="@+id/textView"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerHorizontal="true"
            android:layout_alignParentTop="true"
            android:layout_marginTop="16dp"
            android:text="Details"
            android:textColor="#15A6E8"
            android:textSize="20sp" />

        <TextView
            android:id="@+id/textViewName"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@id/textView"
            android:layout_centerHorizontal="true"
            android:layout_marginTop="32dp"
            android:text="Name"
            android:textColor="#12E4D1" />

        <TextView
            android:id="@+id/textViewAge"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@id/textViewName"
            android:layout_centerHorizontal="true"
            android:layout_marginTop="16dp"
            android:text="Age"
            android:textColor="#25CCBC" />

        <TextView
            android:id="@+id/textViewEmail"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@id/textViewAge"
            android:layout_centerHorizontal="true"
            android:layout_marginTop="16dp"
            android:text="Email"
            android:textColor="#32C8BA" />

        <TextView
            android:id="@+id/textViewContact"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@id/textViewEmail"
            android:layout_centerHorizontal="true"
            android:layout_marginTop="16dp"
            android:text="Contact"
            android:textColor="#38DACB" />

    </RelativeLayout>


</androidx.constraintlayout.widget.ConstraintLayout>
```

# OUTPUT

![Screenshot 2024-04-08 090634](https://github.com/VISHVA12300/WORKSHOP/assets/119404426/b220582b-6048-4d55-be0b-e0e03045d3c9)



![Screenshot 2024-04-08 090403](https://github.com/VISHVA12300/WORKSHOP/assets/119404426/6245b039-f2e8-4688-ab84-dc20b3bf85bc)

# RESULT

Thus a Simple Android Application to pass the data between the activities using Intent in Android Studio is developed and executed successfully.
