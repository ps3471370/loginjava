# loginjava
                                                 MainActivity.java

package com.example.simmar;

import android.graphics.drawable.ColorDrawable;
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
    EditText txt1, txt2;
    Button bt1, bt2;
    TextView lbl;
    int count = 3;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        getSupportActionBar().setBackgroundDrawable(new ColorDrawable(getResources().getColor(R.color.purpleColor)));

        txt1 = findViewById(R.id.tx1);
        txt2 = findViewById(R.id.tx2);
        bt1 = findViewById(R.id.btn1);
        bt2 = findViewById(R.id.btn2);
        lbl = findViewById(R.id.txt3);

        bt1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                String uname = txt1.getText().toString();
                String pass = txt2.getText().toString();

                if (uname.equals("simar") && pass.equals("1234")) {
                    Toast.makeText(MainActivity.this, "Login Successful", Toast.LENGTH_SHORT).show();
                }
                else
                {
                    Toast.makeText(MainActivity.this, "Login Failed", Toast.LENGTH_SHORT).show();
                    count--;
                    lbl.setText(Integer.toString(count));
                    if (count==0){
                        bt1.setEnabled(false);
                    }

                }
                bt2.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {finish();}
                });
            }
        });
    }
}
