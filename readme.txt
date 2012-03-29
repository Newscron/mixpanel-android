Documentation: http://mixpanel.com/api/docs/guides/android

Demo: See the demo/ folder for a working demo application

This is the version of the library that provides a function to set sending of events over a Wifi connection only.
The reason this is a separate branch is that this requires you to set the additional android.permission.ACCESS_NETWORK_STATE permission.

Changelog:

v1.2
-------------------
* Add country geolocation by default. Now all events tracked will have the property 'Country.'

v1.1
-------------------
* Convert MPMetrics into a singleton, fixing a rare race caused by multiple instances.
* Reduce the number of flushes being called when events are backed up.
* Correctly check status of API call result
* Better support for using multiple tokens within a single Android application

v1.0 (original)
------------------
* Removed the funnel() methods. Funnels have been built from events for some time now, and this update to Android simply reflects that change we have made.
  The proper way to perform funnel analysis is to create a funnel based on events that you are sending. For more information, please see http://mixpanel.com/api/docs/guides/funnel-analysis

* Renamed the event method to track, to be more consistent with the existing APIs. 
  Furthermore, the propeties object passed to the new track method is no longer a HashMap, but a JSONObject.
  This will cause types to be correctly preseved in Segmentation.
