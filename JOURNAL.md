---

**Title:** PATRA (Parallel Axis TriTeron Robotic Arm)  
**Author:** Sunrit Hazra  
**Description:** A Hybrid robot architecture of a kinematically linear 3 DOF parallel axis triteron system and a 6 DOF serial robotic arm.  
**Created on:** 2026-05-02  

---

# Flashback

A Random Day in December, 2026, I was scrolling through my YouTube feed. I came across this [video](https://www.youtube.com/shorts/74T0LF2l5Ck) with Tripteron Robot concept, and immediately my mind was blown up due to the awesomeness and coolness of the robot. I immediately had the idea to add a robotic arm to its head, to make it even cooler and more usable.

---

# 10.04.2026: Planning & Studying

Ever since I was a member at Hack Club, I wanted to make this. Originally, I thought of doing this in Blueprint as two seperate modular projects: TriTeron Robot for $400 and Robotic Arm for $400. But, Blueprint ended even before I could start. So, I chose Fallout. I did not start because I was doing Construct and Stasis, and I also lazy.

The perfect opportunity came when I came across the new hardware YSWS — Forge. I knew that I had to keep my budget really high. That's why I decided to choose Tier 1 and keep my budget at maximum $700.

Now, here’s what inspired me:

* https://www.youtube.com/shorts/74T0LF2l5Ck  
This is the video that first sparked my interest.

* https://www.youtube.com/watch?v=6EtXycVGJg4  
This video by Rudmin introduced the original concept.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1e31c116-bfa6-4f96-a2c2-00662f581cc6" />

* https://www.youtube.com/watch?v=io4S9amExNM  
Rowan introduces a more complex carriage system. I have literally watched this probably three times in a row, replaying every assembly step just to understand the machine.

* https://www.youtube.com/watch?v=3fbmguBgVPA  
This pushed me toward adding a robotic arm.

* https://www.youtube.com/watch?v=MeRaYVntxMk  
A really clear explanation of the difference between serial and parallel systems. My robot combines both.

To get started, I did focused research on the following (only this time is counted): 

* **Kinematics:** Beyond just the general definition, I read articles and watched detailed videos specifically on parallel axis kinematics and kinematically linear systems. https://en.wikipedia.org/wiki/Kinematics https://www.youtube.com/watch?v=3fbmguBgVPA

* **Robotic Arms:** I did a deep dive into 5 DOF and 6 DOF robotic arms, studying their structure, joint arrangements, and torque requirements. I also carefully studied the Meca500 robotic arm as a size and precision reference.

* **Linear Belts:** Although I was already familiar with them, I studied motor selection, torque transmission, belt pitch types, and tensioning systems in more detail.

* **Ball Screws:** This was a completely new concept for me. I learned that ball screws offer higher precision and better load handling compared to belts, but at the cost of speed and higher complexity.

* **Aluminium Extrusions:** I knew nothing beyond 2022 and 4040 aluminium extrusion. So, for the sake of this project, I made a deep dive into JLCMC's Aluminium Extrusion Profiles, and I read their [datasheets](https://drive.google.com/file/d/1X2043j8HutSmY2QTKigUobWLhu9sI9k2/view?usp=sharing).

* **Zaber LC40:** Rudmin used [LC40 family](https://www.zaber.com/products/families/LC40) for the tripteron, which is configurable, belt brive, t-slot profile linear stages. I looked at the prices which were mostly in $2000s and $3000s, and honestly not that shocked.

Things I Learned:

* How ball screws work internally (recirculating ball mechanism and lead mechanics)
* Differences between NEMA motor sizes and torque ratings
* Trade-offs between belt drives and screw drives
* The structure of linear actuators
* The mechanical difference between serial and parallel robotic systems
* Why rigidity and repeatability matter more than just “cool movement”
* How can I make my robotic arm modular
* A little about the LC40 family

**Total time spent: 4h 54m**

---

# 11.04.2026: The First Pitch

I guess it was time for the pitch finally. This was my first pitch out of two. I had made a very rough plan in my mind, went to ChatGPT to get it sanity checked, and then I sat with a paper in my hand and drew what I could think of about the robot. Then, I spent some hours researching about the parts in Google and JLC. I also used a bit of AI to search in unknown websites for the parts. Then, I came up with a very rough estimate of the parts and the BOM. Initially, my target was to spend maximum $500 for the TripTeron and $500 for the 6 DOF robotic arm.

I was so much confused with my plan that I drew up 7 different drawings of the thing I want to make. I have not started modelling yet, so I have no idea about what I am doing. But still I want to pitch, I don't know why. Maybe just because I want to see the reaction on people. Will they react like me to the idea?

After that, the draft of the pitch was ready. I manually searched up everything and wrote the BOM. Then, I pitched it in the #forgery channel, waiting for insights. I saw some suggestions and reactions.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/afd7d77b-3889-44e8-b776-08f510aa0ad4" />

Personally, the most frustratirng thing was the fact that I have a pen and a paper with a simple drawing and list of things I have no idea about, and when I search that, there are so many options that I am overwhelmed. I learned about a lot of types of Linear Guides, Rails and NEMA motors.

**A little fast forward:** This project was returned for changes by the reviewer on **14th April, 2026**. I did not make any changes as he said, but my overall plan had changed a lot! So, I re-pitched offically on **30th April, 2026**.

**Please note that I did not use AI for any fields of the pitch. I have only used it to search the sources of my parts (pretty much like Google, but better). Then, manually I visited the sites and made the estimates. Please try to understand.**

**Total time spent: 3h 42m**

---

# 12.04.2026: Starting to Model

I started simple. I clicked on [this](https://www.youtube.com/watch?v=io4S9amExNM&t=1s) video of Rowan, who I definetly an engineer (critiques may argue). I watched it full, tried to understand the carraige this time, specifically, how it moves, and the assembly of the X and Y axis leg and the linear guides, and of course the confusion linear belts. I went to his Patreon and downloaded the Fusion file. Thank god he uses Autodesk Fusion, just like me. I now better understood evrything.

I offically created my project on Fusion, then. And, of course, I totally copied pasted Rowan's model, to modify for my needs. I am of course going to model the thing myself, but with that inspiration. I studied primarily the linear guide on the main rail and the 2040 aluminium extrusion.

So, here's the plan. Rudmin has used two linear axes for the X, Y and Z (on both), which looks more clean and minimalist. Rowan made a different approach by adding in a carraige that independently controlled the X and Y axes legs. I thought of going by Rowan's design as it looked cooler, and with that, I am also going to use ball screw for the main axis! I am planning to make it on 1 metre rail!

Now, to source my parts, I am going to use only JLCMC because there are tons of options, configgurations and customization available. 

I started with the the 4040 T-slot aluminium extrusions. I read the [datasheets](https://drive.google.com/file/d/1X2043j8HutSmY2QTKigUobWLhu9sI9k2/view?usp=sharing) again for 2 minutes and downloaded the STEP files for [TXCL-H7-4040E-L1000](https://jlcmc.com/product/s/T01/TXCL/extruded-aluminum-t-slot-40-series(eu)-8mm-slot-width?k=TXCL-H7-4040E-L1000&productModelNumber=TXCL-H7-4040E-L%5B50~6000%2F0.1%5D). Just look at the prcice of that! Just $8.9920. It is so cheap! I added two of them to cart.

I then went for the Ball Screw. There were a lot of options, and this time I throughly had to read the datasheet this time before making choices. I finally chose BSUF-C7-20-5-L640-F30-P12, and then I added it to cart and downloaded the STEP file.

I did the same with the linear guides. I read the datasheet and chose E-BMN15H-2-L1000-ZF-C-E20, added two of them to cart and downloaded the STEP file.

Then, I did a smart move. To have a rough idea about how my PATRA would look, I downloaded the [Meca500-CAD-model](https://www.3dfindit.com/en/digitaltwin/meca500-assembled?path=mecademic%2Findustrial20robotic20arms%2Fmeca50020six-axis20robot20arm%2Fmeca50020assembled.prj&mident=%7Bmecademic%2Findustrial20robotic20arms%2Fmeca50020six-axis20robot20arm%2Fmeca50020assembled.prj%7D%2C013+%7BLINEID%3D10%7D++%7BNB%3DMeca500+Assembly+simple%7D%2C%7BORDERNO%3DMeca500+Assembly+simple%7D%2C%7BMOUNTING%3Dany+orientation%7D%2C%7BPAYLOAD%3D0.5+kg+rated+%28max.+1+kg%29%7D%2C%7BREACH%3D260+mm+%28see+diagram+below%29%7D%2C%7BWEIGHT%3D4.5+kg%7D%2C%7BNAME%3DMeca500+Assembly+simple%7D%2C%7BSOURCEURL%3Dhttps%3A%2F%2Fwww.mecademic.com%2Fen%2Fdownloads%7D) from 3Dfindit. Again, I will model by myself, but this is just an inspiration; for now it is just a reference. But out of curiosity, I read the [offical docs](https://resources.mecademic.com/en/doc/MC-OM-MECA500/11.1/mc-om-meca500.pdf) on MC-OM-MECA500 from Mecademic.

I brought it all together and after the work of about half an hour, basically this is how it looks!

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ae1e4371-f2ac-4b45-ac44-78ecef0699c0" />

But unfortunately, my excitement was totally killed after looking at the shipping costs. I was totally devastated. It reached more than $200 in shipping alone even in the cheapest options. I am sorry I deleted the cart, so I have no proof, but I learned one really important thing, I just can't use JLCMC for this as there are also customs that I will have to cover, and will make the overall cost a lot high!

I chose to keep the rail at 600 mm and keep the travel length at 500 mm. This rose a lot of problems:

* Firstly, the tripteron had to be scaled at least 1.5 times to make sure that the Meca500 remains in a perfect size, with no scaling down.
* Secondly, the tripteron will have very less space to move if I scaled the tripteron, and kept the travel length at 500 mm.
* Thirdly, the tripteron looks quite ugly.

Now, I have two options now:

1. Scale everything down, including the arm.
2. Just for the time being, keep everything as it is, and test with 600 mm rail.
3. Get relieved from the stress by ignoring the rails, and actually working on the carraige.

But, I chose the third option, for the time being. So, I continued modelling for more hours and this was the result. What I basically did was that unlike Rowan's design, I am going to make the carraige completely independent, so I will add motors seperately to the carraige. For that, I extended the base of the carraige and for that I used extrusions on the frontmost face, and modified the design, maaking it possible to make the rails wide and to let me use ball screw.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/28d18e54-e5e2-471f-a430-8d8cc5a90f1b" />

If you want a rough picture of how I did the CAD throughout today, [here](https://drive.google.com/file/d/17hyzQvfrPkSDDIoYjY-ttWvvfYUGDrAG/view?usp=sharing) is a timelapse-like video, where I have smartly exploited the Fusion Timeline. I'm glad Fusion is parametric.

Well, in this one single day, I did so much (at least for me) due to my dedication and curiosity. I really hope this pays of well.


**Total time spent: 6h 22m**

---

# 13.04.2026: The Second CAD Session

I chose the second option as I wanted to keep my arm at the exact size of Meca500. For contuinuing the option two, I had to go to JLCMC, and individually choose smaller variants of each part, making sure the usable length remains at 500 mm. And after three hours of endless cadding, this is what I got:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/51f2d2e0-dca3-43d2-9c9e-54db52e20baf" />

It just looks wierd. I have to have a better solution to this! But still, this is quite expensive. But surely this is cheaper than the 1 metre travel length one.

Now, I am really tired after all of this.

# [Date]: [Title]

[Content]

**Total time spent: **

---
