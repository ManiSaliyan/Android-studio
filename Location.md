### Location Permission

allow location 
```java
ActivityCompat.requestPermissions( this,
      new String[] {Manifest.permission.ACCESS_FINE_LOCATION}, REQUEST_LOCATION);
```

### Turning on GPS

```java
private void OnGPS() {
      final AlertDialog.Builder builder = new AlertDialog.Builder(this);
      builder.setMessage("Enable GPS").setCancelable(false).setPositiveButton("Yes", new  DialogInterface.OnClickListener() {
         @Override
         public void onClick(DialogInterface dialog, int which) {
            startActivity(new Intent(Settings.ACTION_LOCATION_SOURCE_SETTINGS));
         }
      }).setNegativeButton("No", new DialogInterface.OnClickListener() {
         @Override
         public void onClick(DialogInterface dialog, int which) {
            dialog.cancel();
         }
      });
      final AlertDialog alertDialog = builder.create();
      alertDialog.show();
   }
```

### Things to Import

here hashmap is similar to arrayadaper or array

```java
import com.google.firebase.database.DatabaseReference;
import com.google.firebase.database.FirebaseDatabase;
```
