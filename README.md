# DistanceTracking
Sample Android app to measure the distance traveled by a device since launching the app and display it on the screen. The distance calculation does not stop even if the app has been thrown into the background. Only when the app is killed, the distance is reset to 0. For best results, GPS should be kept on the whole time while moving.

# How it works
As the app is launched, a sticky service, TrackingService, is started from the MainActivity for tracking location. While asking for location updates, provider is not specified so as to get any possible data, though high accuracy is demanded. Once a location update comes the service calulcates the distance covered and fires a local broadcast intent which the activity, if visible, captures and updates the UI.

To prevent battery drain, location updates are requested with minTime of 10 seconds and minDistance of 10 meters. These parameters can be modified as per requirements.
