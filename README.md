# ODCON2

***The ODCON2 is presently in a BETA status***
If you are interested in printing and testing the files to submit feedback to assist in my continued development, the prepared STLs are contained within the BETA.rar file hosted in the link above.

**PLEASE NOTE** 
While these files will work to create a working lightgun, they are still being revised and edited to improve the printability, functionality and general aesthetics.

The files are direct exports from Fusion 360 and as such may import into your slicer in odd orientations. These will need to be adjusted in many cases to print optimally.

If you require any assistance or you would like to provide more direct feedback to me, myself and our supportive community can be located on Discord in the ODCON channel of the DIY Lightgun server: https://discord.gg/VgTxVRnuNB

---

The ODCON2 is the second release in my line of open 3D printable lightgun pistols with full-slide solenoid recoil. 
This new design aims to improve upon the original to produce a lightgun that is easier to print, wire, and assemble while being more ergonomically friendly, aesthetically cleaner, and mechanically reliable.

(insert a promo photo here)

This design is completely platform agnostic and will work with any IR based lightgun system, but I strongly recommend the use of the free and open source OpenFIRE platform. 
**Due to the proprietary nature of some platforms, I will not be sharing those circuits or schematics.**
For the sake of offering a comprehensive guide, the following instructions will make use of OpenFIRE's excellent and freely available electronics solution and software.

I strongly suggest you join the following active Discord communities for further build support:
[DIY Lightgun](https://discord.com/invite/hVU49XuuPv "https://discord.com/invite/hvu49xuupv") 
[OpenFIRE](https://discord.com/invite/ZnGaVaRcFg "https://discord.com/invite/zngavarcfg")

---

## Bill of Materials

**Camera**
- DFRobot (https://s.click.aliexpress.com/e/_DBF2QCF)

**Lenses**
- Lens Kit (https://www.aliexpress.us/item/3256802101574676.html)

**Linear Rail**
- LWL 7B 40mm (https://www.aliexpress.us/item/3256806030208453.html)

**Solenoid**
- 24V (https://s.click.aliexpress.com/e/_DeMXpxz)
- Rubber Washer [5x13x4] (https://s.click.aliexpress.com/e/_DFrdXlp)

**Rumble**
- N20 (https://s.click.aliexpress.com/e/_DF0LCQb)

**Switches**
- Trigger (https://s.click.aliexpress.com/e/_DBphiBp)
- Side Buttons [Pale Blue (but any will work)] (https://s.click.aliexpress.com/e/_DFT7OOR)

**Springs**
- Trigger + Return Assist [3x15x.2] (https://s.click.aliexpress.com/e/_DDOggYJ)

**Connector**
- GX16 Connector (https://s.click.aliexpress.com/e/_DkaVC7h)
- GX16 Cable (https://s.click.aliexpress.com/e/_DeEKQhl)

**Fasteners**
- M2 Kit (https://s.click.aliexpress.com/e/_DB4gK07)
- M3 Kit (https://s.click.aliexpress.com/e/_Dn3xiN9)
- M4 Kit ()
- MCU mounting screws [Pan M1.2x4] (https://www.aliexpress.us/item/2251832857570651.html)
- Threaded Inserts [M3x5x5] (https://s.click.aliexpress.com/e/_DkHyn2F)

**MCU**
-Pico RP2040 ()
-Micro USB adapter ()

**Electronics**
-D4184 board()
-Rumble Circuit Stuff()

---

## Printing

The provided files have been exported in an orientation that has been thoroughly tested and should be ideal for most users to print on any FDM printer (although these are just suggestions).

The print settings that have produced the best consistent results are as follows:
- .12mm Layer Height
- %20 Infill
- Automated Tree Supports (touching buildplate)

*Use of a brim is recommended for small or narrow parts such as the iron sights/side panels/trigger guard and can typically be enabled in your slicers "Per Object" settings.

(Insert photo or two of build plate orientation)

---

## Preparation

**Make sure all of your parts have been cleaned of their supports and any protrusions on rough surfaces where supports and brims have contacted have been cleaned to allow for appropriate clearances**

Starting with the Heel Plate, insert the nut from the GX16 connector into the recess on the interior of the part and thread the connecter in until it's secure from the bottom.
Now is the ideal time to solder you wires to the GX16 connector, make sure to leave plenty of slack on your cables as you can always trim them to length later.
Unless you have a preferred pinout, follow the provided diagram:

(Insert photo of GX16 wiring diagram)

The screw holes on the print have been sized to ensure a snug fit to eliminate any slop, to improve the ease of the build, now is a good opportunity to dry thread all holes using their appropriate sized hardware.

Brass inserts should be prepared and inserted before continuing.
Two should be installed on the lower frame assembly: One beneath the trigger switch recess and one on the tongue nearest to the heelplate:

(Insert pictures of the installed brass inserts)

One should be installed in the rear of the Front Panel:

(Insert picture)

A final brass insert should be installed towards the tail of the body of the gun pictured here:

(Insert picture)

In lieu of brass inserts, some of the thinner areas of the gun use press fit M3 nuts, once pressed into place these can be given a small shot of super glue to help retain them more permanently (be careful that the glue does not contact the threads)
6 M3 nuts will be required in total:
2 for each side panel on the interior of the body of the gun:

(insert pictures)

1 for the front panel on the interior of the body of the gun:

(Insert picture)

And finally 1 in the trigger assembly of the upper frame:

(Insert picture)

**SLIDE LOCK AND TRIGGER SPRING CATCH**

**LINEAR RAIL, RUBBER WASHER AND END STOP**

---

## Assembly

We'll begin with the Lower Frame piece, preparing this section with it's accompanying circuits is important. 

(Insert Rumble Circuit Graphic)

Wire the rumble motor with a minimal amount of slack to the driver circuit above and then install it into the recess as shown below:

(Insert picture)

The rumble motor and driver board can be affixed in place with a small amount of hot glue.

Next, solder the wires you'll need to the "Common" and "NO" (normally open) legs on the trigger microswitch. If the legs of your switch are bent at a right angle, use a pair of pliers to flatten them and then snip them to an appropriate length before soldering.
Once complete, you can feed the wires through the hole and press the microswitch into position as shown below:

(Insert picture)

Feed your wires out of the small opening near the top of the frame piece as shown below, and you're ready to proceed to the next step:

(Insert picture)

Insert the heel plate into the bottom of the gun.
Start by inserting the tongue on the heelplate into the groove on the bottom of the grip, and feed the wires up through the body of the gun as pictured below:

(Insert picture)

Now feed the lower frame into the body of the gun from above being careful to guide the GX16 wires through the channel on the side of the frame. Be sure to tuck the wires through the same hole you fed the rumble and trigger wires as shown below:

(Insert picture)

We will want to lock the lower frame into position before we continue working.
This will include installing a temporary screw into the trigger guard slot, install a short M3 screw into the trigger screw hole. Once the trigger screw is in place the M3 screw in the heelplate can be installed and tightened.

Prepare the solenoid and solenoid sled print.
Using two 8mm M4 screws attach the solenoid to it's sled as shown below:

(Insert picture)

The sled is installed into the top of the body by first sliding the tip of the sled into the catch at the top of the lower frame at an angle. With the tip inserted, lower the back end into the body and press firmly until it seats itself, lock this in place using an M3 screw, this process is shown below:

(Insert pictures)



