This is a modified version of Speeduino firmware 202526.1 by Josh Stewart https://github.com/speeduino/speeduino/releases

This firmware is modified to allow direct drive of a servo motor for fixed rpm control. Servo control is driven by an inverted square wave (5 or 12V, depending on the servo specifications).  The existing VVT Table was repurposed for this function and will no longer be available. Table axes are load and RPM. Higher duty cycle = lower servo and throttle positions. A secondary load sensor was used and interupted via a signal relay (currently secondary load sensor is utilizing oil pressure channel and name - will be revised for future firmwares and named appropriately)  Pull down was enabled on the input to ensure a value of 0 when not enabled. This allowed external switch to command idle or high rpm operation. 

Modifications include
- Repurpsosing VVT table and changing axis to secondary load sensor (i.e. MAP)
- Repurposing Oil Pressure sensor as secondary load *Note to simplify logging and TunerStudio, VVT settings and Oil Pressure nomenclature and naming are still present)
- Changing the axis on Rev Limit table to reference secondary load, thus providing a safety limit when not requesting high RPM
- Changes to Tuner Studio INI file to reflect these changes. 

To utilize: Enable oil pressure sensor and configure appropriately for board/analog input. Configure approprately to match the MAP sensor or load measuring method being used. Enable VVT and assign your output pin (highly suggested to utilize a tacho output or add a pull up resistor circuit to match your servo). VVT enable conditions will still be utilized to enable servo control. You MUST use open loop VVT control.  Set your minimum and maximum duty to prevent servo overrun. The VVT base duty table will be your servo duty table. Note most servos use an inverted control wave (i.e. 100% high = servo at minimum position). It is recommend to retain this logic and position so the servo will home to it's lowest throttle position.  Servo will not function without engine running. 

This is a beta firmware. Use at your own risk. Functionality may vary and owner/creator holds no liability for use or issues or damages that may occur 
from use of this firmware.
