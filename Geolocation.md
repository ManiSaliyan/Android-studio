### Things to Import

You can add an image or a code block, too.

```java
import android.location.Location;
import android.location.LocationManager
import com.google.android.gms.location.FusedLocationProviderClient;
import com.google.android.gms.location.LocationCallback;
import com.google.android.gms.location.LocationRequest;
import com.google.android.gms.location.LocationResult;
import com.google.android.gms.location.LocationServices;
import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
```

### Location class Object Initialisation 

```java
FusedLocationProviderClient mFusedLocationClient;
```

### Setting Permission ID

if permission retirns the 44 then permission is granted 

```java
int PERMISSION_ID = 44;
```

### Inside onCreate

Assigning object mfusedLocProvider
and calling getlocation function 

```java
mFusedLocationClient = LocationServices.getFusedLocationProviderClient(this);
getLastLocation();
```

### Check Permission 


```java
 private boolean checkPermissions() {
        return ActivityCompat.checkSelfPermission(this, Manifest.permission.ACCESS_COARSE_LOCATION) == PackageManager.PERMISSION_GRANTED && ActivityCompat.checkSelfPermission(this, Manifest.permission.ACCESS_FINE_LOCATION) == PackageManager.PERMISSION_GRANTED;
 
        // If we want background location
        // on Android 10.0 and higher,
        // use:
        // ActivityCompat.checkSelfPermission(this, Manifest.permission.ACCESS_BACKGROUND_LOCATION) == PackageManager.PERMISSION_GRANTED
    }
```

