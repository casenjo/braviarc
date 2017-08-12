# BraviaRC Python 2 Package


About
=====

This is a Python 2 conversion of the ``BraviaRC`` Python library by aparraga (https://github.com/aparraga/braviarc).
I did this mainly because Kodi only runs on Python 2 and I needed this library for Kodi development.


Usage
=====

```python

from __future__ import absolute_import
from braviarc import braviarc

#new instance for TV at 192.168.1.25
braviarc = braviarc.BraviaRC(u'192.168.1.25')

#connect to the instance (or register)
pin = u'5285'
braviarc.connect(pin, u'deviceNameInternally', u'deviceNameToDisplay')

#check connection
if braviarc.is_connected():

  #get power status
  power_status = braviarc.get_power_status()
  print power_status

  #get playing info
  playing_content = braviarc.get_playing_info()

  #print current playing channel
  print playing_content.get(u'title')

  #get volume info
  volume_info = braviarc.get_volume_info()

  #print current volume
  print volume_info.get(u'volume')

  #turn off the TV
  braviarc.turn_off()
