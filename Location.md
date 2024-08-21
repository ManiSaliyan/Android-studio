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

### Get Longitude and Latitude 

Two points will get fron this method
by posting it on firebase we xan track it in other phone. by setting a loop of sending change in location every 5 second we can make it as Real Time Location Tracking 

set two global variables x and Y
to assing longitude and latitude value
longitude= 31.976887577
latitude = 45.87589 
so we take datatype as double

```java
double x;
double y;
private void getLocation() {
      if (ActivityCompat.checkSelfPermission(
         MainActivity.this,Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED && ActivityCompat.checkSelfPermission(
            MainActivity.this, Manifest.permission.ACCESS_COARSE_LOCATION) != PackageManager.PERMISSION_GRANTED) {
               ActivityCompat.requestPermissions(this, new String[]{Manifest.permission.ACCESS_FINE_LOCATION}, REQUEST_LOCATION);
       } else {
         Location locationGPS = locationManager.getLastKnownLocation(LocationManager.GPS_PROVIDER);
         if (locationGPS != null) {
            x = locationGPS.getLatitude();
            y = locationGPS.getLongitude()
            double lat = locationGPS.getLatitude();
            double longi = locationGPS.getLongitude();
            latitude = String.valueOf(lat);
            longitude = String.valueOf(longi);
            showLocation.setText("Your Location: " + "
" + "Latitude: " + latitude + "
" + "Longitude: " + longitude);
         } else {
            Toast.makeText(this, "Unable to find location.", Toast.LENGTH_SHORT).show();
        }
      }
   }

https://www.tutorialspoint.com/how-to-get-current-location-latitude-and-longitude-in-android
```
