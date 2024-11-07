### TextView

Used to Display Text

```java
<TextView
        android:id="@+id/textView2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:autoLink="web"
        android:clickable="true"
        android:focusable="true"
        android:linksClickable="true"
        android:padding="10dp"
        android:text="@string/web_link_textView"
        android:textColor="#A7FFEB"
        android:textColorLink="#FFFFFF"
        android:textStyle="bold" />
```

###EditText

Used to take user input

```java
<EditText
 
        android:id="@+id/edittext6"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:maxLength="3"
        android:importantForAutofill="no"
        android:inputType="text"
        tools:ignore="LabelFor" />
```

### Intent Passing

here hashmap is similar to arrayadaper or array

```java
Intent intent = new Intent(getApplicationContext(), Second_activity.class);

intent.putExtra("message_key", str); 
startActivity(intent);


//in second Activity write

Intent intent = getIntent(); 
String str = intent.getStringExtra("message_key");
```
