# Android LocationPicker
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
	
	Don't forget to add your api key for loading google map in the manifest file
#License
 	Copyright 2015 Livin Lawrence

	Licensed under the Apache License, Version 2.0 (the "License");
	you may not use this file except in compliance with the License.
	You may obtain a copy of the License at

	http://www.apache.org/licenses/LICENSE-2.0

	Unless required by applicable law or agreed to in writing, software
	distributed under the License is distributed on an "AS IS" BASIS,
	WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
	See the License for the specific language governing permissions and
	limitations under the License.
