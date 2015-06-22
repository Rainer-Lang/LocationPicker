# LocationPicker
Simple Android activity for picking a location from google map or from the google place suggestions list.
Android has created new place picker action intent similar to it I had created a Activity with google map and auto completed place api textview. This activity has a center point with a geo marker and it always takes the location of that point. When i was working on a project I asked to do so. Along with these this activity can receive two parameters that is lat and lon to point on the map.

# Usage  Start the activity,:
    Intent pickup = new Intent(this,LocationPickerActivity.class);
  				pickup.putExtra("lat", latitude);
  				pickup.putExtra("lon", longitude);
  				startActivityForResult(pickup, LOCATION_PICKER);
				
	Above two are optional paramters. Get the result from the activity like this,
	
		protected void onActivityResult(int requestCode, int resultCode, Intent data) {
		super.onActivityResult(requestCode, resultCode, data);
        	selectedLat = data.getDoubleExtra(AppConfig.USER_LAT, 00);
					selectedLon = data.getDoubleExtra(AppConfig.USER_LNG, 00);
					selectedLocation=data
							.getStringExtra(AppConfig.USER_LOCATION);			
		
	}
