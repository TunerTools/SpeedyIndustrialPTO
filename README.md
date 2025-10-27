This is a modified version of Speeduino firmware 202526.1 by Josh Stewart https://github.com/speeduino/speeduino/releases

This firmware is modified to allow direct drive of a servo motor for fixed rpm control. Servo control is driven by an inverted square wave
(5 or 12V, depending on the servo specifications).  The existing VVT Table was repurposed for this function and will no longer be available.
Table axes are load and RPM. Higher duty cycle = lower servo and throttle positions. A secondary load sensor was used and interupted via a signal relay. 
Pull down was enabled on the input to ensure a value of 0 when not enabled. This allowed external switch to command idle or high rpm operation. 

Modifications include
- Repurpsosing VVT table and changing axis to secondary load sensor (i.e. MAP)
- Repurposing Oil Pressure sensor as secondary load
- Changing the axis on Rev Limit table to reference secondary load, thus providing a safety limit when not requesting high RPM
- Changes to Tuner Studio INI file to reflect these changes. 

This is a beta firmware. Use at your own risk. Functionality may vary and owner/creator holds no liability for use or issues or damages that may occur 
from use of this firmware.
