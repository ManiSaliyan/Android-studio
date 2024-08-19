### Things to Import

here hashmap is similar to arrayadaper or array

```java
import com.google.firebase.database.DatabaseReference;
import com.google.firebase.database.FirebaseDatabase;
```

### Getting Data From Screen

in the screen there is a two input box one for quote and one for author, one button for post data to database

```java
quoteEditText = (EditText) findViewById(R.id.editTextQuote);
authorEditText = (EditText) findViewById(R.id.editTextAuthor);
addButton = (Button) findViewById(R.id.addButton);
String quote = quoteEditText.getText().toString();
String author = authorEditText.getText().toString();
```

### Hashmap

HashMap in Java is a part of the collections framework, which is found in java. util package.HashMap in Java stores the data in (Key, Value) pairs, and you can access them by an index of another type (eg an Integer).
<picture>
<img src="https://github.com/ManiSaliyan/Android-studio/blob/Learn/constructors-in-hashmap-java.webp">
<picture>

### Creating a Hashmap

here the integer key strings have values as object
```java
HashMap<String, Object> quoteHashmap = new HashMap<>();
quoteHashmap.put("quote",quote);
quoteHashmap.put("author",author);
```

### Creating a Firebase Database

```java
FirebaseDatabase database = FirebaseDatabase.getInstance();
DatabaseReference quotesRef = database.getReference("quotes");
```

### Generating key to identify pushed value

Generating key to identify pushed value and putting the generated key to hashmap

```java
String key = quotesRef.push().getKey();
quoteHashmap.put("key",key);
```

### Representation of current Hashmap

| Index |   String  |       Author       |
|------:|-----------|--------------------|
|     0 | Quote     | Life is beautiful  |
|     1 | Author    | manisalian         |
|     2 | Key       | xbdndjdjjndmd      |

### Upload data to Firebase

here hashmap is similar to arrayadaper or array

```java
quotesRef.child(key).setValue(quoteHashmap).addOnCompleteListener(new OnCompleteListener<Void>() {
            @Override
            public void onComplete(@NonNull Task<Void> task) {
                Toast.makeText(AddQuoteActivity.this, "Added", Toast.LENGTH_SHORT).show();
                quoteEditText.getText().clear();
                authorEditText.getText().clear();
            }
        });
```
