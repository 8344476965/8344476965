EXERCISE-1: Arithmetic Operations

xml code:

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical" >



    <EditText
        android:id="@+id/editText1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" android:text="Enter Number">

        <requestFocus />
    </EditText>

    <EditText
        android:id="@+id/editText2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" android:text="Enter Number"/>

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Add" />





    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="left"
        android:text="Sub" />



    <Button
        android:id="@+id/button3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Multiply" />



    <Button
        android:id="@+id/button4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Division" />

    <TextView
        android:id="@+id/textView1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="" />

</LinearLayout>



JAVA CODE:

package com.cal;
import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;


public class ArithmeticOperationsActivity extends Activity {
    /** Called when the activity is first created. */
	EditText no1,no2;
	TextView ans;
	int n1,n2;
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main);
        no1=(EditText)findViewById(R.id.editText1);
        no2=(EditText)findViewById(R.id.editText2);
        ans=(TextView)findViewById(R.id.textView1);
        Button button1=(Button)findViewById(R.id.button1);
        Button button2=(Button)findViewById(R.id.button2);
        Button button3=(Button)findViewById(R.id.button3);
        Button button4=(Button)findViewById(R.id.button4);
        
        button1.setOnClickListener(new View.OnClickListener() {
			public void onClick(View arg0) {
				PerformOperation('+');		
			}
		});
        button1.setOnClickListener(new View.OnClickListener() {
			public void onClick(View arg0) {
				PerformOperation('-');		
			}
		});
        button1.setOnClickListener(new View.OnClickListener() {
			public void onClick(View arg0) {
				PerformOperation('*');		
			}
		});
        button1.setOnClickListener(new View.OnClickListener() {
			public void onClick(View arg0) {
				PerformOperation('/');	
			}
		});
    }
        private void PerformOperation(char op){
        	String n1=no1.getText().toString();
        	String n2=no2.getText().toString();
        	
        	if(!n1.isEmpty() && !n2.isEmpty())
        	{
        		double d1=Double.parseDouble(n1);
        		double d2=Double.parseDouble(n2);
        		double res=0;
        		
        		switch(op){
        		case '+':
        			res=d1+d2;
        			break;
        		case '-':
        			res=d1-d2;
        			break;
        		case '*':
        			res=d1*d2;
        			break;
        		case '/':
        			if(d1!=0)
        				res=d1/d2;
        			else
        				ans.setText("Infinity");
        			break;
        		}
        	}	
        	else{
        		ans.setText("Enter numbers only");
        	}
        }
 }


Output:







Exercise-2: Layouts

Xml code:
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <LinearLayout
        android:id="@+id/linearLayout1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <TextView
            android:id="@+id/textView1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginLeft="60dp"
            android:layout_marginRight="60dp"
            android:text="Students Mark Details"
            android:textColor="#0e0eff"
            android:textSize="20dp" />

    </LinearLayout>

    <LinearLayout
        android:id="@+id/linearLayout2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" >

        <TextView
            android:id="@+id/textView2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="NAME:" 
            android:textSize="20dp"
            android:textColor="#ff0e0e"
            android:layout_marginTop="20dp"/>

        <TextView
            android:id="@+id/textView3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Velan"
            android:layout_marginTop="20dp"
            android:layout_marginLeft="20dp"
            android:textAppearance="?android:attr/textAppearanceLarge" />

        <ImageView
            android:id="@+id/imageView1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginLeft="30dp"
            android:layout_marginTop="15dp"
             />

    </LinearLayout>

    <LinearLayout
        android:id="@+id/linearLayout3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" >
        <TextView
            android:id="@+id/textView4"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="D.NO:"
            android:layout_marginTop="20dp"
            android:textSize="20dp"
            android:textColor="#ff0e0e" />

        <TextView
            android:id="@+id/textView5"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="21ucs513"
            android:layout_marginTop="20dp"
            android:layout_marginLeft="20dp"
            android:textAppearance="?android:attr/textAppearanceLarge" />

        <ImageView
            android:id="@+id/imageView2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/ic_launcher" />

    </LinearLayout>

    <TableLayout
        android:id="@+id/tableLayout1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <TableRow
            android:id="@+id/tableRow1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content">

            <TextView
                android:id="@+id/textView6"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="SUBJECTS"
                android:layout_marginTop="20dp"
                android:layout_marginLeft="20dp" />

            <TextView
                android:id="@+id/textView7"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="JAVA"
                android:layout_marginTop="20dp"
                android:layout_marginLeft="30dp" />

            <TextView
                android:id="@+id/textView8"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="CN"
                android:layout_marginTop="20dp"
                android:layout_marginLeft="20dp" />

            <TextView
                android:id="@+id/textView9"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="OS"
                android:layout_marginTop="20dp"
                android:layout_marginLeft="20dp" />

            <TextView
                android:id="@+id/textView10"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="SE"
                android:layout_marginTop="20dp"
                android:layout_marginLeft="20dp" />

        </TableRow>

        <TableRow
            android:id="@+id/tableRow2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content" >
           <TextView
                android:id="@+id/textView11"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content" 
                android:layout_marginLeft="20dp"
                android:text="MARKS"
                 android:layout_marginTop="10dp" />

            <EditText
                android:id="@+id/editText2"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="10dp"
                 android:layout_marginTop="10dp"
                android:text="90" />

            <EditText
                android:id="@+id/editText1"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="15dp"
                 android:layout_marginTop="10dp"
                android:text="100" >

                <requestFocus />
            </EditText>

            <EditText
                android:id="@+id/editText3"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="20dp"
                 android:layout_marginTop="10dp"
                android:text="85" />

            <EditText
                android:id="@+id/editText4"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="20dp" 
                 android:layout_marginTop="10dp"
                android:text="75"/>

        </TableRow>

    </TableLayout>

    <LinearLayout
        android:id="@+id/linearLayout4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" >

        <Button
            android:id="@+id/Save"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Save"
            android:layout_marginLeft="50dp" 
            android:layout_marginTop="30dp"
            android:textColor="#ffa500"
            android:textSize="15dp"
            android:textStyle="bold"
            android:width="90dp" />

        <Button
            android:id="@+id/first"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Home"
            android:layout_marginLeft="50dp" 
            android:layout_marginTop="30dp"
            android:textColor="#ffa500"
            android:textSize="15dp"
            android:textStyle="bold"
            android:width="90dp" />

    </LinearLayout>
    
</LinearLayout>


Java Code:

package com.login;
import android.app.Activity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class login extends Activity {
    /** Called when the activity is first created. */
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.login);

        Button b11, b22;
        b11 = (Button) findViewById(R.id.Save);
        b11.setOnClickListener(new View.OnClickListener() {
            public void onClick(View view) {
                // Perform actions when the "Save" button is clicked
                // For now, just show a toast message
                Toast.makeText(login.this, "Data Saved", Toast.LENGTH_SHORT).show();
            }
        });

        b22 = (Button) findViewById(R.id.first);
        b22.setOnClickListener(new View.OnClickListener() {
            public void onClick(View view) {
                // Navigate back to the HhActivity when the "Home" button is clicked
                Intent in = new Intent(login.this, LoginpageActivity.class);
                startActivity(in);
            }
        });
    }
}

Output:







Exercise-3: CALCULATOR

XML CODE:
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >


    <RelativeLayout
        android:id="@+id/relativeLayout1"
        android:layout_width="match_parent"
        android:layout_height="match_parent" >

        <EditText
            android:id="@+id/editText1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_alignParentRight="true"
            android:layout_alignParentTop="true" />

        <Button
            android:id="@+id/button1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/editText1"
            android:text="1" />

        <Button
            android:id="@+id/button2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@+id/editText1"
            android:layout_toRightOf="@+id/button1"
            android:text="2" />

        <Button
            android:id="@+id/button3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignTop="@+id/button2"
            android:layout_toRightOf="@+id/button2"
            android:text="3" />

        <Button
            android:id="@+id/button4"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignTop="@+id/button3"
            android:layout_toRightOf="@+id/button3"
            android:text="4" />

        <Button
            android:id="@+id/button6"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/button1"
            android:text="6" />

        <Button
            android:id="@+id/button7"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignTop="@+id/button6"
            android:layout_toRightOf="@+id/button6"
            android:text="7" />

        <Button
            android:id="@+id/button8"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignTop="@+id/button7"
            android:layout_toRightOf="@+id/button7"
            android:text="8" />

        <Button
            android:id="@+id/button9"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignLeft="@+id/button4"
            android:layout_alignTop="@+id/button8"
            android:text="9" />

        <Button
            android:id="@+id/button5"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@+id/editText1"
            android:layout_toRightOf="@+id/button4"
            android:text="5" />

        <Button
            android:id="@+id/button10"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@+id/button4"
            android:layout_toRightOf="@+id/button4"
            android:text="0" />

        <Button
            android:id="@+id/BPlus"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/button6"
            android:text="+" />

        <Button
            android:id="@+id/BMinus"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignTop="@+id/BPlus"
            android:layout_toRightOf="@+id/BPlus"
            android:text="-" />

        <Button
            android:id="@+id/BStar"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignLeft="@+id/button8"
            android:layout_alignTop="@+id/BMinus"
            android:text="*" />

        <Button
            android:id="@+id/BSlash"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignTop="@+id/BStar"
            android:layout_toLeftOf="@+id/button10"
            android:text="/" />

        <Button
            android:id="@+id/BEqual"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignLeft="@+id/button10"
            android:layout_alignTop="@+id/BSlash"
            android:text="=" />

        <Button
            android:id="@+id/button11"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/BPlus"
            android:text="Clear" 
            android:textColor="#ff0000"/>

    </RelativeLayout>

</LinearLayout>

Java code:
package com.calc;

import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class CalculatorActivity extends Activity {
	EditText box;
	Button b1,b2,b3,b4,b5,b6,b7,b8,b9,b0,badd,bsub,bmul,bdiv,beql,bclr;
	double num1,num2,result;
	String option;
	
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main);
        box=(EditText)findViewById(R.id.editText1);
        
        b1=(Button)findViewById(R.id.button1);
        b2=(Button)findViewById(R.id.button2);
        b3=(Button)findViewById(R.id.button3);
        b4=(Button)findViewById(R.id.button4);
        b5=(Button)findViewById(R.id.button5);
        b6=(Button)findViewById(R.id.button6);
        b7=(Button)findViewById(R.id.button7);
        b8=(Button)findViewById(R.id.button8);
        b9=(Button)findViewById(R.id.button9);
        b0=(Button)findViewById(R.id.button10);
        
        badd=(Button)findViewById(R.id.BPlus);
        bsub=(Button)findViewById(R.id.BMinus);
        bmul=(Button)findViewById(R.id.BStar);
        bdiv=(Button)findViewById(R.id.BSlash);
        beql=(Button)findViewById(R.id.BEqual);
        bclr=(Button)findViewById(R.id.button11);
        
        b1.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("1");
			}
		});
        b2.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("2");
			}
		});
        b3.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("3");
			}
		});
        b4.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("4");
			}
		});
        b5.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("5");
			}
		});
        b6.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("6");
			}
		});
        b7.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("7");
			}
		});
        b8.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("8");
			}
		});
        b9.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("9");
			}
		});
        b0.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				box.append("0");
			}
		});
        badd.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				num1=Double.parseDouble(box.getText().toString());
				box.setText("");
				option="+";
				}
		});
        bsub.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				num1=Double.parseDouble(box.getText().toString());
				box.setText("");
				option="-";
				}
		});
        bmul.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				num1=Double.parseDouble(box.getText().toString());
				box.setText("");
				option="*";
				}
		});
        bdiv.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				num1=Double.parseDouble(box.getText().toString());
				box.setText("");
				option="/";
				}
		});
        beql.setOnClickListener(new View.OnClickListener() {
			public void onClick(View v) {
				if(option.equals("+"))
				{
					num2=Double.parseDouble(box.getText().toString());
					result=num1+num2;
					box.setText(String.valueOf(result));
				}
				if(option.equals("-"))
				{
					num2=Double.parseDouble(box.getText().toString());
					result=num1-num2;
					box.setText(String.valueOf(result));
				}
				if(option.equals("*"))
				{
					num2=Double.parseDouble(box.getText().toString());
					result=num1*num2;
					box.setText(String.valueOf(result));
				}
				if(option.equals("/"))
				{
					num2=Double.parseDouble(box.getText().toString());
					if(num2==0)
					{
						box.setText("Zero Division Error");
					}
					else
					{
						result=num1/num2;
						box.setText(String.valueOf(result));
					}
				}
			}
		});
        bclr.setOnClickListener(new View.OnClickListener() {
			
			public void onClick(View v) {
				num1=0;
				num2=0;
				result=0;
				box.setText("");
			}
		});
    }
}

Output:



Exercise-4: login page

xml code

first.xml

<?xml version="1.0" encoding="utf-8"?> 
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"  android:layout_width="fill_parent" 
 android:layout_height="fill_parent" 
 android:orientation="vertical" > 
 <RelativeLayout 
 android:id="@+id/relativeLayout1" 
 android:layout_width="match_parent" 
 android:layout_height="match_parent" > 
 <TextView 
 android:id="@+id/textView1" 
 android:layout_width="wrap_content" 
 android:layout_height="wrap_content" 
 android:layout_alignParentTop="true" 
 android:layout_centerHorizontal="true" 
 android:layout_marginTop="36dp" 
 android:text= "LOGIN PAGE"  
 android:textColor="#ff0000" 
 android:textSize="20dp" 
 android:textStyle="bold" /> 
 <TextView 
 android:id="@+id/textView2"
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_alignParentLeft="true"  android:layout_below="@+id/textView1"  android:layout_marginLeft="50dp"  android:layout_marginTop="58dp"  android:text= "User Name"  
 android:textColor="#0000ff" 
 android:textSize="15dp" 
 android:textStyle="bold" /> 
 <EditText 
 android:id="@+id/un" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_below="@+id/textView1"  android:layout_marginLeft="24dp"  android:layout_marginTop="42dp"  android:layout_toRightOf="@+id/textView2"  android:width="150dp" /> 
 <EditText 
 android:id="@+id/pas" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_alignLeft="@+id/un"  android:layout_below="@+id/un"  android:layout_marginTop="30dp"  android:width="150dp" /> 
 <TextView 
 android:id="@+id/textView3" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_alignLeft="@+id/textView2"  android:layout_alignTop="@+id/pas"  android:layout_marginTop="14dp"  android:text= "Password"  
 android:textColor="#0000ff" 
 android:textSize="15dp" 
 android:textStyle="bold" /> 
 <Button 
 android:id="@+id/login" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_alignLeft="@+id/textView3"  android:layout_below="@+id/pas"  android:layout_marginTop="44dp"  android:text= "LOGIN"  
 android:textColor="#ffa500" 
 android:textSize="15dp" 
 android:textStyle="bold" 
 android:width="90dp" /> 
 <Button 
 android:id="@+id/cancel" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_alignRight="@+id/pas"  android:layout_alignTop="@+id/login"  android:layout_marginRight="20dp"  android:text= "CANCEL"  
 android:textColor="#ffa500" 
 android:textSize="15dp" 
 android:textStyle="bold"
 android:width="90dp" /> 
 </RelativeLayout> 
</LinearLayout> 
First.Xml
<?xml version="1.0" encoding="utf-8"?> 
<LinearLayout 
 xmlns:android="http://schemas.android.com/apk/res/android"  android:layout_width="match_parent" 
 android:layout_height="match_parent" 
 android:orientation="vertical"> 
 <LinearLayout 
 android:id="@+id/linearLayout1" 
 android:layout_width="match_parent" 
 android:layout_height="wrap_content" 
 android:orientation="vertical"> 
 <TextView 
 android:id="@+id/textView1" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_marginLeft="60dp" 
 android:layout_marginRight="60dp" 
 android:text="Students Mark Details"  android:textColor="#0e0eff" 
 android:textSize="20dp" /> 
 </LinearLayout> 
 <LinearLayout 
 android:id="@+id/linearLayout2" 
 android:layout_width="match_parent" 
 android:layout_height="wrap_content" > 
 <TextView 
 android:id="@+id/textView2"
 android:layout_width="wrap_content" 
 android:layout_height="wrap_content" 
 android:text="NAME:"  
 android:textSize="20dp" 
 android:textColor="#ff0e0e" 
 android:layout_marginTop="20dp"/> 
 <TextView 
 android:id="@+id/textView3" 
 android:layout_width="wrap_content" 
 android:layout_height="wrap_content" 
 android:text="DANIJOSE" 
 android:layout_marginTop="20dp" 
 android:layout_marginLeft="20dp" 
 android:textAppearance="?android:attr/textAppearanceLarge" /> 
 <ImageView 
 android:id="@+id/imageView1" 
 android:layout_width="wrap_content" 
 android:layout_height="wrap_content" 
 android:layout_marginLeft="30dp" 
 android:layout_marginTop="15dp" 
 android:src="@drawable/a" /> 
 </LinearLayout> 
 <LinearLayout 
 android:id="@+id/linearLayout3" 
 android:layout_width="match_parent" 
 android:layout_height="wrap_content" > 
 <TextView 
 android:id="@+id/textView4" 
 android:layout_width="wrap_content" 
 android:layout_height="wrap_content" 
 android:text="D.NO:" 
 android:layout_marginTop="20dp" 
 android:textSize="20dp" 
 android:textColor="#ff0e0e" /> 
 <TextView 
 android:id="@+id/textView5" 
 android:layout_width="wrap_content" 
 android:layout_height="wrap_content" 
 android:text="12345" 
 android:layout_marginTop="20dp" 
 android:layout_marginLeft="20dp" 
 android:textAppearance="?android:attr/textAppearanceLarge" />  </LinearLayout> 
 <TableLayout 
 android:id="@+id/tableLayout1" 
 android:layout_width="match_parent" 
 android:layout_height="wrap_content"> 
 <TableRow 
 android:id="@+id/tableRow1" 
 android:layout_width="wrap_content" 
 android:layout_height="wrap_content"> 
 <TextView 
 android:id="@+id/textView6"
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="Name" 
 android:layout_marginTop="20dp"  android:layout_marginLeft="20dp" /> 
 <TextView 
 android:id="@+id/textView7"  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="Tamil" 
 android:layout_marginTop="20dp"  android:layout_marginLeft="30dp" /> 
 <TextView 
 android:id="@+id/textView8"  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="English" 
 android:layout_marginTop="20dp"  android:layout_marginLeft="20dp" /> 
 <TextView 
 android:id="@+id/textView9"  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="Maths" 
 android:layout_marginTop="20dp"  android:layout_marginLeft="20dp" /> 
 <TextView 
 android:id="@+id/textView10"  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="Science" 
 android:layout_marginTop="20dp"  android:layout_marginLeft="20dp" /> 
 </TableRow> 
 <TableRow 
 android:id="@+id/tableRow2" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content" >  <TextView 
 android:id="@+id/textView11"  android:layout_width="wrap_content"  android:layout_height="wrap_content"   android:layout_marginLeft="20dp"  android:text="DaniJose" 
 android:layout_marginTop="10dp" /> 
 <EditText 
 android:id="@+id/editText2"  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_marginLeft="10dp"  android:layout_marginTop="10dp"  android:text="90" /> 
 <EditText
 android:id="@+id/editText1"  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_marginLeft="15dp"  android:layout_marginTop="10dp"  android:text="100" > 
 <requestFocus /> 
 </EditText> 
 <EditText 
 android:id="@+id/editText3"  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_marginLeft="20dp"  android:layout_marginTop="10dp"  android:text="85" /> 
 <EditText 
 android:id="@+id/editText4"  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:layout_marginLeft="20dp"   android:layout_marginTop="10dp"  android:text="75"/> 
 </TableRow> 
 </TableLayout> 
 <LinearLayout 
 android:id="@+id/linearLayout4"  android:layout_width="match_parent"  android:layout_height="wrap_content" > 
 <Button 
 android:id="@+id/Save" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="Save" 
 android:layout_marginLeft="50dp"   android:layout_marginTop="30dp"  android:textColor="#ffa500"  android:textSize="15dp" 
 android:textStyle="bold" 
 android:width="90dp" /> 
 <Button 
 android:id="@+id/first" 
 android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="Home" 
 android:layout_marginLeft="50dp"   android:layout_marginTop="30dp"  android:textColor="#ffa500"  android:textSize="15dp" 
 android:textStyle="bold" 
 android:width="90dp" /> 
 </LinearLayout> 
 
</LinearLayout> 

package com.hh; 
import android.app.Activity; 
import android.content.Intent; 
import android.os.Bundle; 
import android.view.View; 
import android.widget.Button; 
import android.widget.EditText; 
import android.widget.Toast; 
public class HhActivity extends Activity { 
 Button b1, b2; 
 EditText ed1, ed2; 
 /** Called when the activity is first created. */ 
 @Override 
 public void onCreate(Bundle savedInstanceState) { 
 super.onCreate(savedInstanceState); 
 setContentView(R.layout.main); 
 ed1 = findViewById(R.id.un); 
 ed2 = findViewById(R.id.pas); 
 b1 = findViewById(R.id.login); 
 b1.setOnClickListener(new View.OnClickListener() {  public void onClick(View v) { 
 if (ed1.getText().toString().equals("hi") &&  ed2.getText().toString().equals("mas")) { 
 Intent in = new Intent(HhActivity.this, login.class);  startActivity(in); 
 } else { 
 // If incorrect, show a toast message  Toast.makeText(HhActivity.this, "Incorrect username or  password",Toast.LENGTH_SHORT).show(); 
 } 
 } 
 }); 
 b2 = findViewById(R.id.cancel); 
 b2.setOnClickListener(new View.OnClickListener() {  public void onClick(View v) { 
 finish(); 
 } 
 }); 
 } 
} 
Login.java 
package com.hh; 
import android.app.Activity; 
import android.content.Intent; 
import android.os.Bundle; 
import android.view.View; 
import android.widget.Button;
import android.widget.Toast; 
public class login extends Activity { 
 /** Called when the activity is first created. */ 
 public void onCreate(Bundle savedInstanceState) { 
 super.onCreate(savedInstanceState); 
 setContentView(R.layout.first); 
 Button b11, b22; 
 b11 = findViewById(R.id.Save); 
 b11.setOnClickListener(new View.OnClickListener() {  public void onClick(View view) { 
 // Perform actions when the "Save" button is clicked  // For now, just show a toast message 
 Toast.makeText(login.this, "Data Saved",  
Toast.LENGTH_SHORT).show(); 
 } 
 }); 
 b22 = findViewById(R.id.first); 
 b22.setOnClickListener(new View.OnClickListener() {  public void onClick(View view) { 
 // Navigate back to the HhActivity when the "Home" button is  clicked 
 Intent in = new Intent(login.this, HhActivity.class);  startActivity(in); 
 } 
 }); 
 } 
} 
AndroidManifest.xml 
<?xml version="1.0" encoding="utf-8"?> 
<manifest xmlns:android="http://schemas.android.com/apk/res/android"  package="com.hh" 
 android:versionCode="1" 
 android:versionName="1.0" > 

output:






Exercise-5: Bouncing ball animation

Xml code:
// Open res/layout/activity_main.xml and add the following code: 

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <View
        android:id="@+id/ballView"
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:background="@drawable/ball" />

</RelativeLayout> 

// 2. Create a new XML file in res/drawable/ball.xml and add the following code

<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="oval">
    <solid android:color="#FF5733" />
</shape>

JAVA CODE:
package com.example.yourappname;

import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.TranslateAnimation;
import android.widget.RelativeLayout;

public class MainActivity extends Activity {

    private View ballView;
    private int screenHeight;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        ballView = findViewById(R.id.ballView);
        screenHeight = getResources().getDisplayMetrics().heightPixels;

        startBouncingAnimation();
    }

    private void startBouncingAnimation() {
        TranslateAnimation animation = new TranslateAnimation(0, 0, 0, screenHeight);
        animation.setDuration(2000);
        animation.setFillAfter(true);
        animation.setRepeatMode(Animation.REVERSE);
        animation.setRepeatCount(Animation.INFINITE);
        ballView.startAnimation(animation);
    }
}

Output:



Exercise-6: DATABASE CONNECTIVITY

XML CODE:

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:baselineAligned="false"
    android:orientation="horizontal" >




    <RelativeLayout
        android:id="@+id/relativeLayout1"
        android:layout_width="wrap_content"
        android:layout_height="427dp" >

        <TextView
            android:id="@+id/textView1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_alignParentTop="true"
            android:layout_marginTop="85dp"
            android:text="USERNAME"
            android:textAppearance="?android:attr/textAppearanceMedium" />

        <EditText
            android:id="@+id/editText1"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/textView1" />

        <TextView
            android:id="@+id/textView2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/editText1"
            android:layout_marginTop="18dp"
            android:text="PASSWORD"
            android:textAppearance="?android:attr/textAppearanceMedium" />

        <EditText
            android:id="@+id/editText2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/textView2" />

        <Button
            android:id="@+id/button1"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/editText2"
            android:layout_marginTop="18dp"
            android:text="lOGIN" />



        <Button
            android:id="@+id/button3"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_below="@+id/button1"
            android:text="EXIT" />

    </RelativeLayout>

</LinearLayout>


JAVA CODE:

 package com.database;

import android.app.Activity;
import android.app.AlertDialog.Builder;
import android.content.Context;
import android.database.Cursor;
import android.database.sqlite.SQLiteDatabase;
import android.os.Bundle;
import android.view.View;
import android.view.View.OnClickListener;
import android.widget.Button;
import android.widget.EditText;
 
public class DatabaseActivity extends Activity implements OnClickListener
{
    EditText Rollno,Name,Marks;
    Button Insert,Delete,Update,View,ViewAll;
    SQLiteDatabase db;
    /** Called when the activity is first created. */
    @Override
    public void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main);
 
        Rollno=(EditText)findViewById(R.id.Rollno);
        Name=(EditText)findViewById(R.id.Name);
        Marks=(EditText)findViewById(R.id.Marks);
        Insert=(Button)findViewById(R.id.Insert);
        Delete=(Button)findViewById(R.id.Delete);
        Update=(Button)findViewById(R.id.Update);
        View=(Button)findViewById(R.id.View);
        ViewAll=(Button)findViewById(R.id.ViewAll);
 
        Insert.setOnClickListener(this);
        Delete.setOnClickListener(this);
        Update.setOnClickListener(this);
        View.setOnClickListener(this);
        ViewAll.setOnClickListener(this);
 
        // Creating database and table
        db=openOrCreateDatabase("StudentDB", Context.MODE_PRIVATE, null);
        db.execSQL("CREATE TABLE IF NOT EXISTS student(rollno VARCHAR,name VARCHAR,marks VARCHAR);");
    }
    public void onClick(View view)
    {
        // Inserting a record to the Student table
        if(view==Insert)
        {
            // Checking for empty fields
            if(Rollno.getText().toString().trim().length()==0||
                    Name.getText().toString().trim().length()==0||
                    Marks.getText().toString().trim().length()==0)
            {
                showMessage("Error", "Please enter all values");
                return;
            }
            db.execSQL("INSERT INTO student VALUES('"+Rollno.getText()+"','"+Name.getText()+
                    "','"+Marks.getText()+"');");
            showMessage("Success", "Record added");
            clearText();
        }
        // Deleting a record from the Student table
        if(view==Delete)
        {
            // Checking for empty roll number
            if(Rollno.getText().toString().trim().length()==0)
            {
                showMessage("Error", "Please enter Rollno");
                return;
            }
            Cursor c=db.rawQuery("SELECT * FROM student WHERE rollno='"+Rollno.getText()+"'", null);
            if(c.moveToFirst())
            {
                db.execSQL("DELETE FROM student WHERE rollno='"+Rollno.getText()+"'");
                showMessage("Success", "Record Deleted");
            }
            else
            {
                showMessage("Error", "Invalid Rollno");
            }
            clearText();
        }
        // Updating a record in the Student table
        if(view==Update)
        {
            // Checking for empty roll number
            if(Rollno.getText().toString().trim().length()==0)
            {
                showMessage("Error", "Please enter Rollno");
                return;
            }
            Cursor c=db.rawQuery("SELECT * FROM student WHERE rollno='"+Rollno.getText()+"'", null);
            if(c.moveToFirst()) {
                db.execSQL("UPDATE student SET name='" + Name.getText() + "',marks='" + Marks.getText() +
                        "' WHERE rollno='"+Rollno.getText()+"'");
                showMessage("Success", "Record Modified");
            }
            else {
                showMessage("Error", "Invalid Rollno");
            }
            clearText();
        }
        // Display a record from the Student table
        if(view==View)
        {
            // Checking for empty roll number
            if(Rollno.getText().toString().trim().length()==0)
            {
                showMessage("Error", "Please enter Rollno");
                return;
            }
            Cursor c=db.rawQuery("SELECT * FROM student WHERE rollno='"+Rollno.getText()+"'", null);
            if(c.moveToFirst())
            {
                Name.setText(c.getString(1));
                Marks.setText(c.getString(2));
            }
            else
            {
                showMessage("Error", "Invalid Rollno");
                clearText();
            }
        }
        // Displaying all the records
        if(view==ViewAll)
        {
            Cursor c=db.rawQuery("SELECT * FROM student", null);
            if(c.getCount()==0)
            {
                showMessage("Error", "No records found");
                return;
            }
            StringBuffer buffer=new StringBuffer();
            while(c.moveToNext())
            {
                buffer.append("Rollno: "+c.getString(0)+"\n");
                buffer.append("Name: "+c.getString(1)+"\n");
                buffer.append("Marks: "+c.getString(2)+"\n\n");
            }
            showMessage("Student Details", buffer.toString());
        }
    }
    public void showMessage(String title,String message)
    {
        Builder builder=new Builder(this);
        builder.setCancelable(true);
        builder.setTitle(title);
        builder.setMessage(message);
        builder.show();
    }
    public void clearText()
    {
        Rollno.setText("");
        Name.setText("");
        Marks.setText("");
        Rollno.requestFocus();
    }
}

package com.database;

import android.app.Activity;
import android.app.AlertDialog.Builder;
import android.content.Context;
import android.database.Cursor;
import android.database.sqlite.SQLiteDatabase;
import android.os.Bundle;
import android.view.View;
import android.view.View.OnClickListener;
import android.widget.Button;
import android.widget.EditText;
 
public class DatabaseActivity extends Activity implements OnClickListener
{
    EditText Rollno,Name,Marks;
    Button Insert,Delete,Update,View,ViewAll;
    SQLiteDatabase db;
    /** Called when the activity is first created. */
    @Override
    public void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main);
 
        Rollno=(EditText)findViewById(R.id.Rollno);
        Name=(EditText)findViewById(R.id.Name);
        Marks=(EditText)findViewById(R.id.Marks);
        Insert=(Button)findViewById(R.id.Insert);
        Delete=(Button)findViewById(R.id.Delete);
        Update=(Button)findViewById(R.id.Update);
        View=(Button)findViewById(R.id.View);
        ViewAll=(Button)findViewById(R.id.ViewAll);
 
        Insert.setOnClickListener(this);
        Delete.setOnClickListener(this);
        Update.setOnClickListener(this);
        View.setOnClickListener(this);
        ViewAll.setOnClickListener(this);
 
        // Creating database and table
        db=openOrCreateDatabase("StudentDB", Context.MODE_PRIVATE, null);
        db.execSQL("CREATE TABLE IF NOT EXISTS student(rollno VARCHAR,name VARCHAR,marks VARCHAR);");
    }
    public void onClick(View view)
    {
        // Inserting a record to the Student table
        if(view==Insert)
        {
            // Checking for empty fields
            if(Rollno.getText().toString().trim().length()==0||
                    Name.getText().toString().trim().length()==0||
                    Marks.getText().toString().trim().length()==0)
            {
                showMessage("Error", "Please enter all values");
                return;
            }
            db.execSQL("INSERT INTO student VALUES('"+Rollno.getText()+"','"+Name.getText()+
                    "','"+Marks.getText()+"');");
            showMessage("Success", "Record added");
            clearText();
        }
        // Deleting a record from the Student table
        if(view==Delete)
        {
            // Checking for empty roll number
            if(Rollno.getText().toString().trim().length()==0)
            {
                showMessage("Error", "Please enter Rollno");
                return;
            }
            Cursor c=db.rawQuery("SELECT * FROM student WHERE rollno='"+Rollno.getText()+"'", null);
            if(c.moveToFirst())
            {
                db.execSQL("DELETE FROM student WHERE rollno='"+Rollno.getText()+"'");
                showMessage("Success", "Record Deleted");
            }
            else
            {
                showMessage("Error", "Invalid Rollno");
            }
            clearText();
        }
        // Updating a record in the Student table
        if(view==Update)
        {
            // Checking for empty roll number
            if(Rollno.getText().toString().trim().length()==0)
            {
                showMessage("Error", "Please enter Rollno");
                return;
            }
            Cursor c=db.rawQuery("SELECT * FROM student WHERE rollno='"+Rollno.getText()+"'", null);
            if(c.moveToFirst()) {
                db.execSQL("UPDATE student SET name='" + Name.getText() + "',marks='" + Marks.getText() +
                        "' WHERE rollno='"+Rollno.getText()+"'");
                showMessage("Success", "Record Modified");
            }
            else {
                showMessage("Error", "Invalid Rollno");
            }
            clearText();
        }
        // Display a record from the Student table
        if(view==View)
        {
            // Checking for empty roll number
            if(Rollno.getText().toString().trim().length()==0)
            {
                showMessage("Error", "Please enter Rollno");
                return;
            }
            Cursor c=db.rawQuery("SELECT * FROM student WHERE rollno='"+Rollno.getText()+"'", null);
            if(c.moveToFirst())
            {
                Name.setText(c.getString(1));
                Marks.setText(c.getString(2));
            }
            else
            {
                showMessage("Error", "Invalid Rollno");
                clearText();
            }
        }
        // Displaying all the records
        if(view==ViewAll)
        {
            Cursor c=db.rawQuery("SELECT * FROM student", null);
            if(c.getCount()==0)
            {
                showMessage("Error", "No records found");
                return;
            }
            StringBuffer buffer=new StringBuffer();
            while(c.moveToNext())
            {
                buffer.append("Rollno: "+c.getString(0)+"\n");
                buffer.append("Name: "+c.getString(1)+"\n");
                buffer.append("Marks: "+c.getString(2)+"\n\n");
            }
            showMessage("Student Details", buffer.toString());
        }
    }
    public void showMessage(String title,String message)
    {
        Builder builder=new Builder(this);
        builder.setCancelable(true);
        builder.setTitle(title);
        builder.setMessage(message);
        builder.show();
    }
    public void clearText()
    {
        Rollno.setText("");
        Name.setText("");
        Marks.setText("");
        Rollno.requestFocus();
    }
}

Output:

 
