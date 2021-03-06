# Getting started in Companion 1.1.1.



### This article is an introduction to Companion’s basic principles and user interface.
- - - -

### Before you open Companion
* Connect your hardware and software you want to control. Make sure you are in the same network with them.
* In the original elgato streamdeck app, make sure to firmware upgrade the streamdeck to the latest version available
* Close the original elgato streamdeck app. Companion will not find your device if this is open.

### Starting the server
When you open Companion a server window will open.
From the opening view choose your network interface, and change the port if needed, the default is 8000. This is the port of the Companion server.

![Server](images/server.png?raw=true "Server")


Companion should be running on the same computer the streamdeck is connected, maximum of three units, the number might increase in future updates.
Companion can run on the same machine than Barco eventmaster or other control/playback software; it uses minimal resources.

If you need to remotely control companion from other computers in the network, use the URL under the text “Running”. Normally to configure Companion from the computer your running it click green “Launch GUI” button, it will open the Admin page in your default browser.

We recommend using Google Chrome

### The user interface / Admin GUI
- - - -
The main window is divided into three parts.
From left to right Community section, Main admin controls and Log
![Admin GUI](images/admingui.jpg?raw=true "Admin GUI")

## Community section with links
[Companion GitHub to report bugs.](https://github.com/bitfocus/companion/issues)

[Facebook group to share information and ask questions.](https://www.facebook.com/groups/2047850215433318/)

[The slack group for developers.](https://bit.ly/2IJ1jT4)

On top, there is also Elgato Emulator.

You can collapse the Community section by clicking the “burger icon” on the right of Companion logo.


### Elgato Emulator
Elgato emulator is a tool to test and use the setup even if you don’t have a streamdeck connected. It will open to a new tab on the browser and will function just like a stream deck would.

- - - -
## Main admin controls 
Here all the connections, buttons and actions are configured.
This section is divided into four tabs.

### Instances
From the Instances tab, you can add, edit and remove devices. You can also see if a device is connected from the Status column.

 **To add a new device** 
 
1. Click on the [Add new instance] scroll down menu.
2. Choose the device you want to add.
3. Give the IP address of the device and apply changes.


Your new device should now show in the instances tab.
Add all the devices you want to control.
Each device needs to be a separate instance. If you have two separate Barco E2, you need to add both of them as a separate instance.

![Instance](images/instance.jpg?raw=true "Instance")

If something is missing, please make a support request on the [GitHub page by creating an issue/feature request](https://github.com/bitfocus/companion/issues) describing the feature, use cases and providing documentation, if needed for the implementation.

---


### Buttons
From the Buttons tab, you can add, edit and remove buttons for your stream deck.
Buttons layout has 99 pages that can be navigated from the blue top arrows left and right. Typing text on the field beside the page number can rename pages.

**Making buttons**

1. First, make at least one instance.
2. Click on the button you want to create on the grid.
3. Set button style from the green “Set button style” button.
4. Add Actions to button

There are three options,

“None” will disable the button.

“Text” will generate text to the button. 

“PNG image” will allow you to upload a 72x58px .png image to be used as a button and also lets you add text over the image.

**Creating a text button**

Type button text to field, select alignment and font size. Text and background colour can also be changed.
Live preview of the button will be shown on the top right corner. Button information will update in real-time to Elgato emulator and stream deck.

Add action to the button from the [Add new action for this button] drop-down menu.

You can add multiple actions and set delay times to each action. Delay times are in milliseconds. 1000ms = 1 second.

![Button](images/button.jpg?raw=true "Button")



**Creating a png button**

Make a 72x58px .png image
Click the blue Browse button and find the png file you want to use. The picture will appear on the top right preview of the button. Text can be applied over the image if wanted, and actions can be created the same way that to text only buttons.

---
### Devices
This tab will show the connected Elgato Streamdecks.
If your streamdecks are not showing, click on the blue Re-scan USB button. Use the re-scan button with care as re-scanning will block all operations while the scan is ongoing.

**Important. If your devices are showing but they don´t show the ID, you need to update your steamdeck using the Elgato app**
[Update instructions] (Updating streamdeck.md)
![Devices](images/devices.jpg?raw=true "Devices")


### User Config
On User Config tab you can change some of the preferences of the page up/down behaviour and symbols used.

- - - -

## Log on the right
On the Log segment right gives status updates of commands going out and coming back to Companion.
 **this section needs still some work **
Meaning of colours blue, grey, red

---

# Modules
All the instances on Companion are modules. 
Here is a list of the current modules. As each module is different, they all have a module specific info.

* AnalogWay Livecore  
* Artnet Sender 
* IfElseWare AV-Playback
* Barco EventMaster
* Barco PDS 
* Blackmagic Design ATEM 
* Blackmagic Design Hyperdeck
* Blackmagic Design VideoHub
* CasparCG
* Dataton Watchout
* OSC Generic (send custom packets)
* d3/disguise (osc control) 
* d3/disguise (json, multi transport control)
* Digital Projection Highlight
* GrandMA 2 (telnet)
* Horae (osc)
* Mitti (osc)
* Millumin (osc)
* Octopus Listener
* PJLink 
* PlaybackPro Plus
* PPT Remote Show Control (Irisdown)
* PVP
* QLab (osc)
* Ross Carbonite/Vision
* Spyder
* VLC



## AnalogWay Livecore

**Available variants for AnalogWay Livecore**

* ACS4806
* ACS3204
* NXT1604
* NXT0802
* SMX12x4

**Available commands for AnalogWay Livecore**

* Take selected screens (Global take)
* Take single screen
* Load Memory
* Load Master Memory
* Set recall filter
* Recall Monitoring Memory
* Select screens for global take
* Load confidence mode
* Switch input plug
* Send custom command


---

## Artnet Sender
This module will transmit ArtNet packets to the ip and universe you specify below. If you need more universes, add multiple artnet instances.


From instances setup ip and universe
![artnet1](images/Modules/artnet1.jpg?raw=true "artnet1")

From Button actions set Channel range and value

![artnet2](images/Modules/artnet2.jpg?raw=true "artnet2")

---

## IfElseWare AV-Playback

**Available commands for IfElseWare AV-Playback**

* Goto 10
* Goto 20
* Goto 30
* Goto 60
* Load Clip (number)
* Play Clip (number)
* Goto (Timecode)
* Play standby clip
* Pause Resume
* Stop
* Freeze temp
* Loop temp

---

## Barco EventMaster
This module uses the official EventMaster JSON API. Unfortunately the JSON API is not available in the simulator, so you need to use the real deal to get this working. If the status is OK, it ONLY means that the IP configured answers on icmp ping.


**Available commands for Barco EventMaster**

* Take/Trans Active
* Cut Active
* Recall Next Preset
* Freeze
* Unfreeze
* Preset in PVW
* Preset in PGM

---

## Barco PDS 

**Available variants for Barco PDS**

* PDS-701
* PDS-901
* PDS-902

**Available commands for Barco PDS**

* Take
* Select Input
* Freeze
* Set Black Output
* Set Testpattern on/off
* Set Testpattern Type
* Set Rasterbox on/off
* Set Transition Time
* Select Black/Logo
* Save Logo
* Set Autotake Mode on/off
* Pend PiP Mode on/off
* Pend PiP Input

---

## Blackmagic Design ATEM 
Should work with all models of Blackmagic Design ATEM mixers

**Available commands for Blackmagic Design ATEM** 

* Set input on Program
* Set input on Preview
* Set AUX bus
* Set Upstream KEY OnAir
* CUT operation
* AUTO transition operation
* Run MACRO


---

## Blackmagic Design Hyperdeck

**Available commands for Blackmagic Design Hyperdeck**

* Play (Speed%)
* Play
* Record
* Stop
* Goto (timecode)
* select (slot)

---

## Blackmagic Design VideoHub

This module will connect to any BlackmagicDesign VideoHub Device.

**Available commands for Blackmagic Design VideoHub**

* Rename destination
* Rename source
* Route

---

## CasparCG

**Available commands for CasparCG**

* LOADBG
* LOAD
* PLAY
* PAUSE
* RESUME
* STOP
* CLEAR
* CALL
* SWAP
* Manually specify AMCP command

---

## Dataton Watchout

**Available commands for Dataton Watchout**

* Run
* Pause
* Kill
* Jump to time
* Jump to cue
* Go online
* Enter Standby
* Set Input

---

## OSC Generic
In instaces tab specify the ip and port you want to send. In button actions tab specify the osc path and value.

**Available commands for OSC Generic**

* Send message
* Send integer
* Send float
* Send string

---

## d3/disguise (OSC)
This module sends default OSC controls to the d3/disguise server. Remember to set up the server to receive OSC.

**Available commands for d3/disguise**

* Play
* Play to end of selection
* Loop selection
* Stop
* Previous Section
* Next Section
* Previous track
* Next track
* Master brightnes - Fade up
* Master brightnes - Fade down

---

## d3/disguise (json, multi transport control)

This module uses the JSON interface in the d3/disguise server to control multiple transports individually.

**Available commands for d3/disguise (json, multi transport control)**

* Track Command w/timecode
* Track Command

---

## Digital Projection Highlight

**Available commands for Digital Projection Highlight**

* Power On Projector
* Power Off Projector
* Open Shutter
* Close Shutter
* Freeze Input
* Unfreeze Input
* Increase Brightnes
* Decrease Brightnes
* Increase Contrast
* Decrease Contrast
* Increase Saturation
* Decrease Saturation

---

## GrandMA 2 (telnet)

Remember to activate Telnet Remote in Setup -> Console -> Global Settings -> Telnet

**Available commands for GrandMA 2 (telnet)**

* Run Command

---

## Horae (osc)

**Available commands for Horae (osc)**

* Start
* Stop
* Arm

---

## Mitti
Sends OSC commands to port 51000. 

From Mittis preferences OSC/UDP Controls tab, make sure its "Enabled"
![Mitti](images/Modules/Mitti.jpg?raw=true "Mitti")

**Available commands for Mitti**

* Play
* Toggle Play
* Stop
* Panic
* Rewind
* Jump to previous cue
* Jump to next cue
* Jump to specific cue (number)
* Select previous cue
* Select next cue
* Goto 30
* Goto 20
* Goto 10

---

## Millumin 2
Sends OSC commands to Millumin 2, Millumin default port is 5000 but you can change that if needed in Millumin Interactions menu. Go to Interactions/Manage devices and from there OSC tab. 

![Millumin](images/Modules/Millumin.jpg?raw=true "Millumin")

**Available commands for Millumin**

* Toggle Column (number)
* Launch Column (number)
* Goto Timeline Segment (name)
* Goto Media Normalized Time (number)
* Start Media at Column (number)
* Start (name) Media
* Next Column
* Previous Column
* Stop all Columns
* Play Timeline
* Pause Timeline
* Play or Pause Timeline
* Restart Media
* Pause Media
* Toggle Play Media
* Stop Media


---

## Octopus Listener

This module is for the Octopus Listener from [noismada.com.](http://noismada.com)

Can be used to send keystrokes. Be carefull, needs to have the application you want to controll active.

**Available commands for Octopus Listener**

* Custom command
* Custom keystroke
* PPT Next slide
* PPT Previous slide
* PPT Start presentation
* PPT First slide
* PPT Exit presentation
* Keynote goto slide (number)
* Keynote Next slide
* Keynote Previous slide
* Keynote Start presentation
* Keynote First slide
* Keynote Exit presentation

---

## PJLink

**Available commands for PJLink**

* Power On Projector
* Power Off Projector
* Open Shutter
* Close Shutter
* Freeze Input
* Unfreeze Input

---

## PlaybackPro Plus

**Available commands for PlaybackPro Plus**

* Goto 10
* Goto 20
* Goto 30
* Take
* Pause Resume
* Kill
* Freeze temp
* Loop temp
* Previous Clip
* Next Clip

---

## PPT Remote Show Control (Irisdown)

**Available commands for PPT Remote Show Control (Irisdown)**

* Open file
* Close file
* Run file
* Stop file
* Next slide
* Previous slide
* Goto Slide
* Set background

---

## PVP

**Available commands for PVP**

* Clear Layer (id)
* Mute Layer (id)
* Unmute Layer (id)
* Select Layer (id)
* Hide Layer (id)
* Unhide Layer (id)
* Select Playlist (id)
* Trigger Cue (id)
* Trigger Playlist (id)
* Trigger Cue in Playlist (Playlist id) (Cue id)
* Trigger Cue in Playlist on Layer (Layer id) (Playlist id) (Cue id)
* Clear Workspace
* Mute Workspace
* Hide Workspace
* Unhide Workspace
* Unmute Workspace

---

## Qlab
Sends OSC commands to port 53000.

From Qlab preferences OSC controls tab make sure you have the "Use OSC controls" checkbox ticked.
![Qlab](images/Modules/Qlab.jpg?raw=true "Qlab")

**Available commands for Qlab**

* Start (cue)
* GO
* Pause
* Stop
* Panic
* Reset
* Previous Cue
* Next Cue
* Resume

---

## Ross Carbonite/Vision

To make sense of the input and output names available in the actions provided by this module, you might want to read the bottom of this [reference manual.](http://help.rossvideo.com/carbonite-device/Topics/Protocol/RossTalk/CNT/RT-CNT-Comm.html)

**Available commands for Ross Carbonite/Vision**

* Trigger GPI
* Fire custom control
* Load Set
* Cut
* Auto Transition
* XPT
* Transition Keyer
* Fade to black

---

## Spyder

**Available commands for Spyder**


* Take
* Basic Preset Recall (Index number)
* Recall Script Cue (Script, Cue)
* Transition Layer(s)
* Freeze Layer(s)
* Background Transition
* Function Key Recall
* Output Freeze
* Device Mixer Transition

---

## VLC

**Available commands for VLC**

* Play
* Stop
* Pause / Resume
* Next
* Previous
* Full Screen
* Loop
* Repeat

---















