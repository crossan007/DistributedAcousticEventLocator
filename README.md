# DistributedAcousticEventLocator

Because this is a thing: http://www.fox29.com/news/bucks-county-residents-report-loud-boom-noises-in-middle-of-night

Premise:

* 3 or more raspberry pi devices with 3 microphones each
* all devices have barometric pressure sensor
* all devices have a compass for geomagnetic orientation
* all devices have a synchronized clock
* all devices run software analyzing the incoming audio stream for "high amplitude events"
* Upon detection of an "event," the device will send a message to a centralized server containing: 
   * the device's latitude/longitude, 
   * the timestamp of the event,
   * the device's mesaured barometric pressure, 
   * the event's detected amplitude
   * device's cardinal orientation
   * measured incoming event angle

*  Centralized server correlates events within a sliding window (so that there is sufficient time for more distant detectors to have detected and submitted the event) and preforms some fancy triginometry on the values correlating:
   * position
   * amplitude
   * barometric presure (for approximate speed of sound adjustments)


References:
  *  https://www.raspberrypi.org/forums/viewtopic.php?t=165996
