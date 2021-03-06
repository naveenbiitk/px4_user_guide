# Flight Modes

*Flight Modes* define how the autopilot responds to user input and controls vehicle movement. The tables below summarizes flight modes for fixed wing and copter ([table key is below](#key)). Note that this is the "high level" default behaviour, and may vary based on vehicle parameters. The linked topics (sidebar) provide more detailed information about individual modes, including their tuning parameters.

> **Tip** A *beginner friendly* explanation of all flight modes is provided in [Getting Started > Flight Modes](../getting_started/flight_modes.md). 

<!-- Styles used for tables below -->
<style>
table {
  display: block;
  overflow: scroll;
  width: 100%;
  font-size:1.5rem;
  text-align:center;
}

.markdown-section table {
  display: block;
}

tr td:nth-last-child(1) {
    text-align:left;
}

/*
  .col_summary {
    width:50px;
  }
*/


th {
  font-size:1.0rem;
}


@media (min-width: 1500px){
.page-inner {
  max-width: 1100px;
  }
}

@media (min-width: 1400px) and (max-width: 1500px) {
.page-inner {
  max-width: 1000px;
  }
}

@media (min-width: 1200px) and (max-width: 1400px) {
.page-inner {
  max-width: 800px;
  }
}

</style>

## Fixed Wing

<table>
 <thead>
   <tr>
     <th class="col_modes">Modes</th>
     <th class="col_r_p">Roll & Pitch</th>
     <th class="col_yaw">Yaw</th>
     <th class="col_throttle">Throttle</th>
     <th class="col_sensor">Position Sensors</th>
     <th class="col_summary">Summary</th></tr>
   </tr>
 </thead>
<tbody>

<tr id="position_fw">
 <td><a href="../flight_modes/position_fw.md">Position</a>
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_1.svg" title="Difficulty (Easiest)" width="20px" /></a></p>
 </td>
 <td>S<sup>+</sup></td>
 <td>S<sup>+</sup></td>
 <td>S<sup>+</sup></td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td><p>RC/manual mode where centered sticks put vehicle into straight and level flight where vehicle posture/attitude, altitude, and the straight line vehicle path are maintained against wind (and other forces).
   <ul>
       <li>Centered RC RPY sticks – level flight that follows a straight line ground track in the current direction against any wind.</li>
       <li>Outside center:
      <ul>
       <li>Pitch is used to ascend/descend (controls altitude).</li>
       <li>Throttle determines airspeed (at 50% throttle the aircraft will hold its current altitude with a preset cruise speed).</li> 
       <li>Roll, pitch and yaw are all angle-controlled (so it is impossible to roll over or loop the vehicle).</li>
     </ul></li>
   </ul>
  </p>
  </td>
</tr>


<tr id="altitude_fw">
 <td><a href="../flight_modes/altitude_fw.md">Altitude</a>
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_2.svg" title="Difficulty (Easy)" width="20px" /></a></p>
 </td>
 <td><p>S (roll)</p><p>S<sup>+</sup>(pitch)</p></td>
 <td>M</td>
 <td>S<sup>+</sup></td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Altitude required (e.g. Baro, Rangefinder)" width="20px" /></a><sup><a href="#baro_only">++</a></sup></td>
 <td>
 <p>RC/manual mode like <a href="#stabilized_fw">Stabilized</a> mode but with <em>altitude stabilization</em> (centered sticks put vehicle into straight and level flight and maintain current altitude). The vehicle course is not maintained, and can drift due to wind.
  <ul>
    <li>Centered sticks (inside deadband):
      <ul>
       <li>Pitch input is used to control the altitude. If zero pitch input – autopilot holds current altitude against wind.</li> 
       <li>RPY sticks gives level flight.</li> 
       <li>Throttle stick controls the airspeed of the aircraft if an airspeed sensor is connected (without airspeed sensor, the user cannot control throttle).</li>
    </ul>
    <li>Outside center:
      <ul>
       <li>Pitch stick controls altitude.</li>
       <li>Throttle sets airspeed.</li> 
       <li>If roll/pitch sticks are non-zero the vehicle does a coordinated turn (manual yaw input is added to rudder control input to control sideslip).</li>
    </ul>
  </li>
  </ul>
 </p>
 </td>
</tr>


<tr id="stabilized_fw">
 <td><a href="../flight_modes/stabilized_fw.md">Stabilized</a>
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_3.svg" title="Difficulty (Medium)" width="20px" /></a></p>
 </td>
 <td>S</td>
 <td>M</td>
 <td>M</td>
 <td></td>
 <td>
  <p>RC/manual mode where centered RP sticks level vehicle (centered sticks put vehicle into straight and level flight). The vehicle course and altitude are not maintained, and can drift due to wind.</p>
  <p>If roll/pitch sticks are non-zero the vehicle does a coordinated turn (manual yaw input is added to rudder control input to control sideslip).</p>
 </td>
</tr>

<tr id="acro_fw">
 <td>Acro
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_5.svg" title="Difficulty (Hard)" width="20px" /></a></p>
 </td>
 <td>S<sub>rate</sub></td>
 <td>S<sub>rate</sub></td>
 <td>M</td>
 <td></td>
 <td><p>This mode can be used to perform acrobatic maneuvers.</p>
<p>RC RPY stick inputs are translated to angular rate commands that are stabilized by autopilot.</p></td>
</tr>

<tr id="manual_fw">
 <td>Manual
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_6.svg" title="Difficulty (Hardest)" width="20px" /></a></p>
 </td>
 <td>M</td>
 <td>M</td>
 <td>M</td>
 <td></td>
 <td>User RC sticks input directly sent to the output mixer for manual control.</td>
</tr>


<tr id="takeoff_fw">
 <td><a href="../flight_modes/takeoff.md">Takeoff</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle initiates the takeoff sequence using either <em>catapult/hand-launch mode</em> or <em>runway takeoff mode</em> (in the current direction).</td>
</tr>


<tr id="land_fw">
 <td><a href="../flight_modes/land.md">Land</a></td>
 <td class="centred" colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle initiates the <a href="../flying/fixed_wing_landing.md">fixed-wing landing</a> sequence.</td>
</tr>

<tr id="hold_fw">
 <td><a href="../flight_modes/hold.md">Hold</td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle circles around the GPS hold position at the current altitude.</td>
</tr>

<tr id="return_fw">
 <td><a href="../flight_modes/return.md">Return</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle ascends to a safe height and then returns to its home position and circles. </td>
</tr>


<tr id="mission_fw">
 <td><a href="../flight_modes/mission.md">Mission</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle executes a <a href="../flying/missions.md">predefined mission/flight plan</a> that has been uploaded to the flight controller. </td>
</tr>
 
</tbody></table>



## Multicopter

<table>
 <thead>
   <tr>
     <th>Modes</th>
     <th>Roll & Pitch</th>
     <th>Yaw</th>
     <th>Throttle</th>
     <th>Position Sensors</th>
     <th class="col_summary">Summary</th></tr>
   </tr>
 </thead>
<tbody>


<tr id="position_mc">
 <td><a href="../flight_modes/position_mc.md">Position</a>
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_1.svg" title="Difficulty (Easiest)" width="20px" /></a></p>
 </td>
 <td>S<sup>+</sup></td>
 <td>S<sub>rate</sub></td>
 <td>S<sup>+</sup></td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td><p>RC/manual mode where RPT sticks control <em>speed</em> in corresponding directions. Centered sticks level vehicle and hold it to fixed position and altitude against wind.
  <ul>
    <li>Centered RPT sticks hold x, y, z position steady against any wind and levels attitude.</li>
    <li>Outside center:
      <ul>
       <li>Roll/Pitch sticks control speed over ground in left-right and forward-back directions (respectively) relative to the "front" of the vehicle.</li>
       <li>Throttle stick controls speed of ascent-descent.</li>
       <li>Yaw stick controls rate of angular rotation above the horizontal plane.</li>
      </ul>
    </li>
    </ul>
  </li>
  </ul>
 </p>
</td>
</tr>

<tr id="altitude_mc">
 <td><a href="../flight_modes/altitude_mc.md">Altitude</a>
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_2.svg" title="Difficulty (Easy)" width="20px" /></a></p>
 </td>
 <td>S</td>
 <td>S<sub>rate</sub></td>
 <td>S<sup>+</sup></td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Altitude required (e.g. Baro, Rangefinder)" width="20px" /></a><sup><a href="#baro_only">++</a></sup></td>
 <td><p>RC/manual mode like <a href="#manual_stabilized_mc">Manual/Stabilized</a> mode but with <em>altitude stabilization</em> (centered sticks level vehicle and hold it to fixed altitude). The horizontal position of the vehicle can move due to wind (or pre-existing momentum).
  <ul>
    <li>Centered sticks (inside deadband):
      <ul>
       <li>RPY sticks levels vehicle.</li> 
       <li>Throttle (~50%) holds current altitude steady against wind.</li>
    </ul>
    <li>Outside center:
      <ul>
       <li>Roll/Pitch sticks control tilt angle in respective orientations, resulting in corresponding left-right and forward-back movement.</li>
       <li>Throttle stick controls up/down speed with a predetermined maximum rate (and movement speed in other axes).</li> 
       <li>Yaw stick controls rate of angular rotation above the horizontal plane.</li> 
    </ul>
  </li>
  </ul>
 </p>
 </td>
</tr>


<tr id="manual_stabilized_mc">
 <td><a href="../flight_modes/manual_stabilized_mc.md">Manual/ Stabilized</a>
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_3.svg" title="Difficulty (Medium)" width="20px" /></a></p>
 </td>
 <td>S</td>
 <td>S<sub>rate</sub></td>
 <td>M</td>
 <td></td>
 <td><p>RC/manual mode where centered sticks level vehicle (only - position is not stabilized).</p>
   <p>
   <ul>
    <li>Centered RP sticks level vehicle.</li>
    <li>Outside center:
      <ul>
       <li>Roll/Pitch sticks control tilt angle in those orientations, resulting in corresponding left-right and forward-back movement.</li>
       <li>Throttle stick controls up/down speed (and movement speed in other axes).</li>
       <li>Yaw stick controls rate of angular rotation above the horizontal plane.</li>
      </ul>
    </li>
    </ul>
  <p>
</td>
</tr>


<tr id="rattitude_mc">
 <td>Rattitude
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_4.svg" title="Difficulty (Medium-hard)" width="20px" /></a></p>
 </td>
 <td>S or S<sub>rate</sub></td>
 <td>S<sub>rate</sub></td>
 <td>M</td>
 <td></td>
 <td>
 <p><a href="#acro_mc">Acro</a> mode with <em>attitude stabilization</em> (centered sticks level vehicle).
  <ul>
    <li>Centered sticks: Vehicle levels out (i.e. like <a href="#manual_stabilized_mc">Manual/Stabilized</a> mode).</li>
    <li>Sticks outside center: RPY stick inputs control the rate of angular rotation around the respective axes. (i.e. like <a href="#acro_mc">Acro</a> mode).</li>
  </ul>
 </p>
</td>
</tr>


<tr id="acro_mc">
 <td>Acro
 <p><a href="#key_difficulty"><img src="../../assets/site/difficulty_5.svg" title="Difficulty (Hard)" width="20px" /></a></p>
 </td>
 <td>S<sub>rate</sub></td>
 <td>S<sub>rate</sub></td>
 <td>M</td>
 <td></td>
 <td><p>RC/manual mode for performing acrobatic maneuvers e.g. flips.</p> 
<p>RC RPY stick inputs control the rate of angular rotation around the respective axes. When sticks are centered the vehicle will stop rotating, but remain in its current orientation (not necessarily level!)</p></td>
</tr>


<tr id="takeoff_mc">
 <td><a href="../flight_modes/takeoff.md">Takeoff</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle ascends to takeoff altitude and holds position.</td>
</tr>

<tr id="land_mc">
 <td><a href="../flight_modes/land.md">Land</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle lands at the position where the mode was engaged.</td>
</tr>

<tr id="hold_mc">
 <td><a href="../flight_modes/hold.md">Hold</td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle hovers at the current GPS position and altitude.</td>
</tr>

<tr id="return_mc">
 <td><a href="../flight_modes/return.md">Return</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle ascends to a safe height and then returns to its home position and lands. 
</td>
</tr>


<tr id="mission_mc">
 <td><a href="../flight_modes/mission.md">Mission</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle executes a <a href="../flying/missions.md">predefined mission/flight plan</a> that has been uploaded to the flight controller. </td>
</tr>

<tr id="followme_mc">
 <td><a href="../flight_modes/follow_me.md">Follow Me</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle autonomously follows a user using an Android phone/tablet running QGC.</td>
</tr>

<tr id="offboard_mc">
 <td><a href="../flight_modes/offboard.md">Offboard</a></td>
 <td colspan="3">Auto</td>
 <td><a href="#key_position_fixed"><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /></a></td>
 <td>Vehicle obeys a position, velocity or attitude setpoint provided over MAVLink (often from a companion computer connected via serial cable or wifi).</td>
</tr>
 
</tbody></table>


## VTOL

VTOL vehicles support both fixed-wing and multicopter flight modes, executing them based on the current vehicle mode (MC or FW).

VTOL supports <a href="../flight_modes/offboard.md">Offboard</a> mode in either configuration.


## Key

Key for understanding the table is as follows:

Symbol | Description
--- | ---
M | Manual control via RC sticks. RC input is sent directly to the output mixer.
S | Assistance from autopilot to stabilize the attitude. RC input is required. Position of RC stick maps to the orientation of vehicle.
S<sub>rate</sub> |  Assistance from autopilot to stabilize the attitude rate. RC input is required. Position of RC stick maps to the rate of rotation of vehicle in that orientation.
S<sup>+</sup> | Assistance from autopilot to hold position or altitude against wind. RC input is required.
Auto | This mode is automatic (RC control is disabled by default except to change modes).
<span id="key_position_fixed"></span><img src="../../assets/site/position_fixed.svg" title="Position fix required (e.g. GPS)" width="20px" /> | Sensor(s) that measures position/height needed e.g. optical flow, GPS+barometer, visual-inertial odometry. <p id="baro_only"><b>++</b> - <em>Altitude Mode</em> only requires altitude sensor (e.g. Baro, Rangefinder).</p>
<span id="key_difficulty">[<img src="../../assets/site/difficulty_1.svg" title="Difficulty (Easiest)" width="20px" />&nbsp;<img src="../../assets/site/difficulty_2.svg" title="Difficulty (Easy)" width="20px" />&nbsp;<img src="../../assets/site/difficulty_3.svg" title="Difficulty (Medium)" width="20px" />&nbsp;<img src="../../assets/site/difficulty_4.svg" title="Difficulty (Medium-hard)" width="20px" />&nbsp;<img src="../../assets/site/difficulty_5.svg" title="Difficulty (Hard)" width="20px" />&nbsp;<img src="../../assets/site/difficulty_6.svg" title="Difficulty (Hardest)" width="20px" />](#key_difficulty) | Flight mode difficulty (easy to hard).


Abbreviations:
  * RPY: Roll, Pitch, Yaw
  * RPT: Roll, Pitch Throttle



<!-- 

## Manual modes {#manual-modes}

"Manual" flight modes are those where the user has control over vehicle movement via the RC control sticks (or joystick). 

**Fixed wing aircraft:**

- **Manual**: The pilot has direct control (via the safety
  coprocessor). This is the only mode that overrides the FMU. It provides a safety mechanism
  which allows full control of throttle, elevator, ailerons and rudder
  via RC in the event of an FMU firmware malfunction.
- **Stabilized (aka fly-by-wire)**: The pilot's pitch and roll inputs are passed as angle commands to the autopilot, while the yaw input is sent directly via the output mixer to the rudder (manual control). If the RC roll and pitch sticks are centered, the autopilot regulates the roll and pitch angles to zero, hence stabilizing (leveling-out) the attitude against any wind disturbances. However, in this mode the position of the aircraft is not controlled by the autopilot, hence the position can drift due to wind. With nonzero roll input the vehicle does a coordinated turn to achieve zero sideslip (the acceleration in y-direction (sidewards) is zero). During a coordinated turn, the rudder is used to control the sideslip and any manual yaw input is added to that.
- **Acro:** The pilot's inputs are passed as roll, pitch, and yaw *rate* commands to the autopilot. The autopilot controls the angular rates. Throttle is passed directly to the output mixer.


**Multirotors:** 

Throttle Command is mapped direct to Motor Speed.

- [Manual/Stabilized](../flight_modes/manual_stabilized_mc.md) The pilot's inputs are passed as roll and pitch angle commands and a yaw rate command. Throttle is passed directly to the output mixer. The autopilot controls the attitude, meaning it regulates the roll and pitch angles to zero when the RC sticks are centered, consequently leveling-out the attitude. The autopilot does not compensate for drift due to wind (or other sources).
- **Acro:** The pilot's inputs are passed as roll, pitch, and
  yaw *rate* commands to the autopilot. The Aircraft will not
  level out after Sticks return to Center. This allows maneuvers like Loops.
- **Rattitude:** The pilot's inputs are passed as roll, pitch, and
  yaw *rate* commands to the autopilot at the extreme positions of
  the sticks. If not the inputs are passed as roll and
  pitch *angle* commands and a yaw *rate* command.
  
  > **Note** For Multirotors, the Manual and Stabilized modes are the same.



## Assisted modes {#assisted-modes}

"Assisted" flight modes are also user controlled but offer some level of "automatic" assistance to gain or restore controlled flight.

- **Altitude** ([FW](../flight_modes/altitude_fw.md)/[MC](../flight_modes/altitude_mc.md)): More easily control vehicle altitude, and in particular reach and maintain a fixed altitude. The mode does not use GPS, and hence will not attempt to hold the vehicle x and y position or course against wind.

- **Position**
  - **Fixed wing aircraft:** Neutral inputs (meaning when roll, pitch and yaw sticks are centered) provide a level flight and
    will crab against the wind if needed to maintain a straight line.
  - **Multirotors** Roll controls left-right speed, pitch controls
    front-back speed. When roll and pitch are all centered (inside
    deadzone) the multirotor will hold position. Yaw controls yaw rate
    as in MANUAL mode. Throttle controls climb/descent rate as in Altitude
    mode.

    > **Warning** Care must be taken when landing in *Position mode* to ensure that landing is 
    > *correctly detected*. When first landing in this mode, be ready to switch 
    > to *Stabilized mode* in order to be able to disarm. If landing is correctly 
    > detected, motors will spin down after touch down and then disarm shortly after. 
    > If the motors keep spinning at higher RPM or start spinning up, first switch 
    > to *Stabilized mode*, and then disarm. Be aware that the vehicle may tip over 
    > on the ground due to GPS drift. 


## Auto modes {#auto-modes}

"Auto" flight modes are those where the controller requires little to no user input (e.g. to takeoff, land and fly missions).

- [Hold](../flight_modes/hold.md): Holds at the current position (hovers for copter, circles for fixed-wing)
- [Return (RTL)](../flight_modes/return.md): Return to the home position and land (copter) or circle (fixed-wing).
- [Takeoff](../flight_modes/takeoff.md): Take off and wait for further input.
- [Land](../flight_modes/land.md): Land at the location where the mode was engaged. 
- [Mission](../flight_modes/mission.md): The vehicle follows a programmed mission, which is usually planned and uploaded using a ground control station (GCS).
- [Follow Me](../flight_modes/follow_me.md) (Multicopter-only): The vehicle autonomously follows a user with an Android phone/tablet running *QGroundControl*.
- [Offboard](../flight_modes/offboard.md): The vehicle obeys a position, velocity or attitude
  setpoint provided over MAVLink (often from a companion computer connected via serial cable). The setpoint can be
  provided by APIs like [DroneCore](http://dronecore.io/) or [MAVROS](https://github.com/mavlink/mavros).
  
-->

