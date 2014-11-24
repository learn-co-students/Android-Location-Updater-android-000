Android-Location-Updater
========================

##The Gist 

Our goal is simple: Get the devices current location and display it in a Toast.  That's it... 

##Instructions 

### Manifest and Build.gradle 

	* Add Permissions to Manifest.xml to enable fine location updates
	* Add MetaData Tag to Application tag in Manifest.xml `<meta-data 	android:name="com.google.android.gms.version" 	android:value="@integer/google_play_services_version" />`
	* Add Google Play Services to Build.gradle file 


### LocationUpdaterActivity.java 

	* Set your activity to implement `GooglePlayServicesClient.	ConnectionCallbacks` , `GooglePlayServicesClient.	OnConnectionFailedListener` , and `LocationListener`
	* Initialize a LocationClient member variable `mLocationClient` in (	OnCreate() ) (all params will be `this` since we're implementing 	the listeners internally)
	* Initialze a LocationRequest member varialbe `mRequest` in (	onCreate() ) 
	* Set mRequests' priority, interval, and fastestInterval in (	onCreate() )
	* Connect to your locationClient in onStart()
	* disconect from your locationClient in onStop()

### Callbacks

	* call requestLocationUpdates on the mLocationClient in `onConnected(Bundle bundle)`
	* show a toast that the user has been disconnected in `onDisconnected()`
	* show a toast with the users Location in `onLocationChanged(Location location)`

##Resources 

* [Receive Location Updates](http://developer.android.com/training/location/receive-location-updates.html)

