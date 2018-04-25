# DistributedAcousticEventLocator

Premise:

* 3 or more raspberry pi devices with microphones
* all devices have barometric pressure sensor
* all devices have a synchronized clock
* all devices run software analyzing the incoming audio stream for "high amplitude events"
* Upon detection of an "event," the device will send a message to a centralized server containing the device's latitude/longitude, the timestamp of the event, and the event's detected amplitude

*  Centralized server correlates events within a sliding window (so that there is sufficient time for more distant detectors to have detected and submitted the event) and preforms some fancy triginometry on the values correlating:
   * position
   * amplitude
   * barometric presure (for approximate speed of sound adjustments)
