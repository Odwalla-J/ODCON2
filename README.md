# ODCON2

***The ODCON2 is presently in BETA status***
If you are interested in printing and testing the files to submit feedback to assist in my continued development you can download the prepared STLs contained within the BETA.rar file hosted in the repository.

**PLEASE NOTE** 
While these files will work to create a working lightgun, they are still being revised and edited to improve the printability, functionality and general aesthetics. THESE ARE NOT THE FINAL FILES. 

The files are direct exports from Fusion 360 and as such may import into your slicer in odd orientations. These will need to be adjusted in many cases to print optimally. Check below in the "Printing" section of the guide for advice on how to orient your parts for printing.

If you require any further assistance or you would like to provide more direct feedback, you can most easily reach myself and my supportive community on Discord in the ODCON channel of the DIY Lightgun server: [DIY Lightgun](https://discord.com/invite/hVU49XuuPv "https://discord.com/invite/hvu49xuupv") 

---
## It's finally here!

The ODCON2 is the second release in my line of open hardware 3D printable lightgun pistols with full-slide solenoid recoil. 
This new design aims to improve upon the original to produce a lightgun that is easier to print, wire, and assemble while being more ergonomically friendly, aesthetically cleaner, and mechanically reliable.

(insert a promo photo here)

This design is completely platform agnostic and will work with any IR based lightgun system (Samco, OpenFIRE, Gun4IR, etc.)

**Due to the proprietary nature of some platforms, I will not be sharing those circuits or schematics, because of this (and for the sake of offering a comprehensive guide) the following instructions will make use of OpenFIRE's excellent and freely available electronics solution and software**

The OpenFIRE firmware and software can be located here:
[Team OpenFIRE GitHub](https://github.com/TeamOpenFIRE "https://github.com/TeamOpenFIRE")

I strongly suggest you join the following active Discord communities for further build support:
[DIY Lightgun](https://discord.com/invite/hVU49XuuPv "https://discord.com/invite/hvu49xuupv") 
[OpenFIRE](https://discord.com/invite/ZnGaVaRcFg "https://discord.com/invite/zngavarcfg")

**While following along with the guide below I strongly suggest users to test their gun as they go along to prevent having to completely disassemble the gun to troubleshoot at a later step.**

---

## Bill of Materials

**BE CAREFUL WHEN ORDERING FROM THESE LINKS, SOME PARTS HAVE MULTIPLE OPTIONS, THESE PARTS HAVE SQUARE BRACKETS PROCEEDING THE LINK TO INDICATE EXACTLY WHICH PART TO SELECT**

**Camera**
- DFRobot (https://s.click.aliexpress.com/e/_DBF2QCF)

**Lenses**
- Lens Kit (https://www.aliexpress.us/item/3256802101574676.html)

**Linear Rail**
- LWL 7B 40mm (https://www.aliexpress.us/item/3256806030208453.html)

**Solenoid**
- JF-1039B [DC24V] (https://s.click.aliexpress.com/e/_m0wx99w)
- Rubber Washer [5x13x4] (https://s.click.aliexpress.com/e/_DFrdXlp)

**Rumble**
- N20 (https://s.click.aliexpress.com/e/_DF0LCQb)

**Switches**
- Trigger (https://s.click.aliexpress.com/e/_DBphiBp)
- Side Buttons [Pale Blue (but any will work)] (https://s.click.aliexpress.com/e/_DFT7OOR)

**Springs**
- Trigger + Return Assist [3x15x.2] (https://s.click.aliexpress.com/e/_DDOggYJ)

**DIY Cable**
- GX16 Connector (https://s.click.aliexpress.com/e/_DkaVC7h)
- 6 Conductor Cable [22AWG 6C 5Meter] (https://s.click.aliexpress.com/e/_mr87lHE)
- USB Connector (https://s.click.aliexpress.com/e/_mqPPXtW)
- Barrel Jack (https://s.click.aliexpress.com/e/_mPR2KtS)

**Fasteners**
- M2 Kit (https://s.click.aliexpress.com/e/_DB4gK07)
- M3 Kit (https://s.click.aliexpress.com/e/_Dn3xiN9)
- M4 Kit [M4 20pcs, Length: 6mm] (https://s.click.aliexpress.com/e/_m03UCyc)
- MCU mounting screws [Pan M1.2x4] (https://www.aliexpress.us/item/2251832857570651.html)
- Threaded Inserts [M3x5x5] (https://s.click.aliexpress.com/e/_DkHyn2F)

**MCU**
- Pico RP2040 (https://s.click.aliexpress.com/e/_m0uYkDA)

**Electronics**
- Micro USB breakout(https://s.click.aliexpress.com/e/_mL7v6bi)
- D4184 board [AOD4184 - 40V 50A] (https://s.click.aliexpress.com/e/_mNJ5ZTq)

**Rumble Circuit**
- 2N2222 (https://s.click.aliexpress.com/e/_mMfKNbm)
- 1kOhm Resistor [1k] (https://s.click.aliexpress.com/e/_mLR72WC)
- 100nF Capacitor [100NF] (https://s.click.aliexpress.com/e/_mKIjqbS)
- Diode (https://s.click.aliexpress.com/e/_mMPhXt6)

**IR Tracking LEDs**

These should work for all IR gun systems, only one set of these are required per TV.
- IR LED Setup (https://a.aliexpress.com/_mKVuVFi)

**PSU**

- 24V 3A Power Supply (https://s.click.aliexpress.com/e/_mry11qu)

---

## Recommended Tools and Materials

Before beginning a build it is advisable to have a few of the following tools to assist you.

- A 3D Printer: not entirely necessary if you can have a friend print this for you, I've printed these models sucessfully on a 2018 Ender 3 and a Bambu Labs P1P.
- A Soldering Iron: A reasonable variable temperature iron is recommended, the Pinecil V2 by Pine64 is an excellent budget model that will work using the same PSU required by the gun. 
- Hex Drivers/Bits: A set of drivers for M2/3/4 screws will be needed, **ball-end drivers are HIGHLY recommeded.**
- Needle Nose Pliers
- Adjustable Wrench
- Small Phillips Head (+) screwdriver

Thin silicone wire is preferred for work inside of the gun, I prefer to use 24AWG wire harvested from old network cables as they come in conveniently color coated twisted pairs that make wiring components pretty easy.
Thicker guage wire will need to be used for the solenoid power lines, I suggest using nothing smaller than 22AWG. To save an extra expense you can salvage some from a short piece of the 6-conductor wire you'll need for the DIY cable.

Several other materials like hot glue, super glue and solder will be will be required, materials like heat shrink tube and electrical tape are left to the users discretion or preferrence. 

---

## Printing

The provided files have been exported in an orientation that has been thoroughly tested and should be ideal for most users to print on any FDM printer (although these are just suggestions).
**The beta files may not be exported in their proper orientations due to my rapid itteration, follow the pictures below to verify part orientation or check on the Discord for support with this if required.**

The print settings that I suggest that have produced the best consistent results are as follows:
- .12mm Layer Height
- %20 Infill
- Automated Tree Supports (touching buildplate)

*Use of a brim is recommended for small or narrow parts such as the iron sights/side panels/trigger guard, if you are printing these files all at once you can typically enable brims selectively in your slicers "Per Object" settings.

(Insert photo or two of build plate orientation)

---

## Preparation

**Make sure all of your parts have been cleaned of their supports and any protrusions or rough surfaces where supports and brims have contacted have been cleaned to allow for appropriate clearances. Now is also a good opportunity to dry thread all holes using their appropriate sized hardware to ensure ease of installation later, undersized holes can be slightly widened using your hex drivers or hobby knife.**

Starting with the Heel Plate, insert the nut from the GX16 connector into the recess on the interior of the part and then thread the connector in from the bottom until it's secure using an adjustable wrench.
Now is the ideal time to solder your wires to the GX16 connector, make sure to leave plenty of slack on your cables as you can always trim them to length later (roughly 10" should be sufficient).
Unless you have a preferred pinout, follow the provided diagram:

(Insert photo of GX16 wiring diagram)

Brass inserts should be prepared and inserted before continuing.
Two should be installed on the lower frame assembly: One beneath the trigger switch recess and one on the tongue nearest to the heelplate:

(Insert pictures of the installed brass inserts)

One should be installed in the rear of the Front Panel:

(Insert picture)

A final brass insert should be installed towards the tail of the body of the gun pictured here:

(Insert picture)

In lieu of brass inserts, some of the thinner areas of the gun use press fit M3 nuts, once pressed into place these can be given a small shot of super glue to help retain them more permanently (be careful that the glue does not contact the threads)
7 M3 nuts will be required in total:
2 for each side panel on the interior of the body of the gun:

(insert pictures)

1 for the front panel on the interior of the body of the gun:

(Insert picture)

1 on the bottom of the slide carriage:

(Insert picture)

And finally 1 in the trigger assembly of the upper frame:

(Insert picture)

You may pre-prepare your side panels by inserting the switched into the holes and pressing them firmly into place, friction should be enough to hold them firmly in place but small amount of hot glue from behind isn't a bad idea. I like to install them with the centered pin in the downwards position as shown below, now is also an excellent opportunity to pre-solder the wires:

(Insert picture)

The body of the gun has three small pieces that need glued into position, dry fit the parts to test their fit before committing with the glue, the support material may need to be carved away from the slide locks if they do no lay flush with the top of the body as shown below. Once they are in good condition apply super glue to the interior of the slide lock and then press firmly into place as shown below:

(Insert picture)

The Trigger Catch will need to be installed as well, test fit the part with the arrow facing forward as shown below, if it fits well then super glue can be applied to the recesses of the body and the part can be pushed firmly into place until it dries, it's not a bad idea to add some glue to the outsides of the part from above once locked into position:

(Insert picture)

The Upper Frame prep is fairly simple. Start by removing the bearing block from the rail carefully (if you were supplied with a plastic rail you can slide the bearing block directly onto this) Now place the linear rail into the matching groove and then inserting the M2 screws into the two available holes. From below you should be able to place an M2 nut on each thread by holding it in place with a pair of pliers. Firmly install the screws without overtightening:

(Insert picture)

Carefully re-install the bearing block onto the linear rail. Now you can insert the rubber washer into it's recess as shown below, now is also an excellent time to lube the linear rail if you have a lubricant like white lithium grease available, just make sure to wipe away any excess:

(Insert picture)

Before applying glue, it's a good idea to dry fit the end cap, it's a very tight fit and it helps to insert the piece at an angle. Once you're confident with the fit, apply super glue to the underside of the part as shown and reinstall the piece, hold it in place until it sets: 

(Insert picture)

The DFRobot camera will need to be dissected for it to fit properly. This includes stripping it's cable all the way to the plastic body of the camera, as well as removing the rubber strain relief nub for the cable, the only protrusion on the back of the camera should be the LED:

(Insert picture)

Once the camera seats flush against the piece as shown you're safe to hot glue it into position. Ignore the "TOP" marking on the label, this is incorrect for our application. If you're an OpenFIRE user the LED should be on the left and the wires on the right, there is a small notch in the top of the frame piece to help you locate center (Refer to your IR solutions provider to verify installation orientation)

(Insert picture)

The trigger is the final piece that requires pre assembly. Install the washers into the grooves on the trigger to test fit them, if they need some minor adjustments use a hobby knife to shave away small amounts from the body of the trigger at a time. These can be super glued into place once they are ready. Now you will want to test fit the trigger to make sure the tolerances are snug but not too tight that it prevents smooth motion. Insert the trigger between the gap in the top frame as shown below to test the fit, if the trigger is too tight, use sand paper to remove a small amount from each side carefully until the perfect fit is achieved:

(Insert picture)

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

With the rear half complete and the wires fished to the front of the gun, it's now time to prepare the upper frame piece to install. 
Install the DFRobot IR camera into the front of the frame, ignore the "TOP" marking on the label as this is incorrect for our purposes. Make sure the **LED is on the left** and the wires are exiting the body on the right. With this installed onto the frame with the wires fed through the bottom you can now affix this in place with hot glue on either side as shown below:

(Insert picture)

Flip the frame over and install the Pico with the USB end facing away from the camera, affix this to the frame using the MCU short screws, now is an excellent time to snip your camera wires to length and solder them to the Pico as shown below:

(Insert pictures)

Align the components on your desk as shown to prepare for the remainder of the wiring for your build: 

(Insert picture)

Stretch the 4 USB wires to the USB port on your Pico making sure to leave about a half inch of slack as shown, then strip a small amount of the tips of the wires to prepare them for soldering:

(Insert picture)

Solder the wires to the micro USB breakout as shown below:

(Insert micro USB diagram and picture)

Once complete you may attach this to the Pico.
Now is an excellent opportunity to wire the remaining cables from the rear of the gun to your Pico. The 5V power, rumble, trigger, and grounds are connected as shown below, leave a similar half inch of slack and strip a small amount of each cable for soldering to the points shown below:

(Insert wiring diagram and picture)

It's a good time to start your D4184 board assembly. Install the diode across the legs of the smaller through-hole points in the orientation shown below and solder making sure not to cover the larger pads for later. Make sure the diode is oriented in the correct direction: 

(Insert picture)

Now is a good time to solder the solenoid and 24v leads to the D4184 board. We will be tucking this board in the front cavity of the gun as shown below, so use that as your gauge for how to measure your wires. Allow yourself the same half inch of slack as before and strip away a small portion of the cable to solder. Solder the leads as shown below with the 24v voltage to + and the 24v ground to -, then solder one lead of the solenoid to + and the other lead to LOAD:

(Insert picture)

With this board complete you can tuck it into position, it may help to install it with the side panels as connected shown to ensure a good fit. This can be held in place with a dab of hot glue:

(Insert picture)

Now with the sides removed it's a good opportunity to install the signal wires to the D4184 board, ground goes to ground and PWM goes to the solenoid control pin on the Pico as shown below, allow for similar wire length tolerances as normal: 

(Insert picture)

Finally, solder wires to both side panel buttons, solder these to your Pico as shown below:

(Insert picture)

Now we can begin the final assembly of the gun. 
Starting with the Front panel, install the wide angle lens by pressing it firmly into the recess in the barrel. Then line the panel up with the notch on the body, and install the front screw. Once tight, install the second screw from the interior of the gun as shown below:

(Insert pictures)

Now you can install both side panels, the procedure will be identical. Install the tongue into the groove in the body at an angle and then slowly flip the side panel up into position against the body of the gun. Once firmly installed, install both screws and repeat for the other side. Pictures shown below:

(Insert pictures)

Now install the Top Frame piece. The front of the frame where the camera is installed has triangular cut-outs that match the same triangles in the body. Start by inserting the frame at an angle as pictured below with forward pressure until the triangular sections mate, then press the rear of the frame down into position. Pictures shown below:

(Insert pictures)

Now we can finalize the trigger installation. 
Remove the temporary screw from the trigger hole, the lower frame will be locked into position between the solenoid sled and heelplate. The trigger spring will need to trimmed roughly to 10mm and installed into the hole in the trigger, carefully raise the trigger into position making sure to aim the spring into the spring catch hole above (you can help guide this with a small screwdriver from above) Once in position you can install the trigger screw through the body until tight. Be careful not to overtighten the screw as this will prevent the smooth actuation of the trigger. Once installed successfully, take the completed Trigger Guard assembly and insert the rear end with the screw hole into it's recess, once firmly in place, carefully but firmly push the other end into it's matching recess, it will snap in locking it firmly in place. You can now reinstall the trigger screw. Pictures below:

(Insert pictures)

To install the carriage on the slide make sure to depress the solenoid and align the cutouts for the shaft with the nut side down, gently press the carriage into place and install the M3 screw through the hole to lock the carriage into place: 

(Insert pictures)

Now you should be able to complete the assembly by installing the slide.
Make sure that the bearing block is completely forward and then lower the slide onto the gun from above making sure that the wings on the carriage slide into place on the slide. Install the 4 M2 screws through the slide and into the bearing block and tighten firmly but gently, the M2 screws will snap if over-torqued. Pictures below:

(Insert pictures)

Be sure to assess the fit and finish of the gun.
There should be a consistent gap from front to back along the slide and body and the actuation of the slide should be smooth and it should snap quickly back into it's rest position even against gravity.
If everything appears to be in good order we can proceed to making the cable GX16 cable for the gun. 

---

## Building a GX-16 Cable

First determine the length of the cable that you will need.
You will need to cut an appropriate length of cable from the roll about 3 inches longer than you'll need to account for stripping. 
Strip about an inch away from the end of the first end of the cable, you should have 6 individual wires beneath the sheathing that are also sheathed. In the case that our cables aren't identical I will not be color coating this next step.
Determine which colors you will be using for each feature of the wire:
- VCC
- Data +
- Data -
- Ground
- 24v +
- 24v -
Be careful to make sure you document this accurately.

Disassemble the female GX16 connector, you will need to unscrew the set screw on the side of the connector and twist it gently before it will pull apart, refer to the pictures below:

(Insert picture)

Using the pinout from earlier, we will make sure that the GX16 matches our gun, the ports will just be wired in reverse. Pictures below:

(Insert pictures)

Once the wires are soldered accordingly be sure to triple check that everything is correctly wired, you can now reassemble the cable, it should clamp securely over the thick sheathing on the larger wire.
We can now move on to the USB and barrel jack end.
Splice away roughly 2 inches of the cable and separate the USB lines of the cable for now.
You may want to slide on some heat shrink tubing now to use for later, when ready, strip and solder those to our male USB header according to the diagram. Pictures below:

(Insert pictures)

Now is an excellent time to slip some heat shrink over the USB portion of the cable making sure to cover a portion of the body of the connector. Heat and shrink. Pictures below:

(Insert picture)

Now you can solder the remaining two wires to your barrel jack connector according to the picture below. Once complete, install heat shrink tubing and heat it. Pictures below:

(Insert picture)

Now that both connections are complete you can use the preemptively applied piece of heat shrink to finalize the cable. Pictures below:

(Insert picture)

Make sure to test your cable without the 24V applied first, and if possible, test the 24V pins of the cable with a meter before connecting it to your gun. 
Once complete we can proceed to flashing the Pico. 

---

## Flashing the MCU

This should be the easy part.
If you haven't already downloaded it, both the firmware and software for the OpenFIRE lightgun project can be located here: [Team OpenFIRE GitHub](https://github.com/TeamOpenFIRE "https://github.com/TeamOpenFIRE")
Instructions exist on their respective pages, but I will cover the process briefly here:

Plug your gun into your computer using the cable you just completed.
The Pico should appear as a storage device mounted to your PC, open it in your file explorer and copy the latest .UF2 binary from the OpenFIRE firmware page onto your Pico.
Once the copy has completed your Pico should automatically reboot and reconnect with the firmware installed. Your gun is basically complete.

---

## Basic Software Config

Make sure your gun is connected and flashed with the OpenFIRE firmware, the app will not run if it doesn't detect your gun. 
Run the OpenFIRE application, in the top left corner you will need to select the drop down next to "COM Port" there should only be one available device if this is the only gun connected. Select it and you can now edit parameters of your gun using the simple UI.
A detailed guide can be found on the [Team OpenFIRE GitHub](https://github.com/TeamOpenFIRE "https://github.com/TeamOpenFIRE"), but most importantly you will want to go to the "Gun Tests" tab and run the IR configuration.
Once complete your gun should now be operational, aiming at the screen should move your mouse curser and pulling the trigger should register as a mouse click.
Under the "Gun Tests" menu you can press each of your buttons to verify that they are operational, and you can send vibrate and solenoid commands to your gun to test those features.
Be mindful that the solenoid will not trigger if the 24V power is not connected.
Conversely if the 24v power is connected the solenoid will trigger with each trigger pull as long as the gun is aimed at the screen which can be troublesome if you're navigating using the gun instead of your mouse or a dedicated frontend. 

---


