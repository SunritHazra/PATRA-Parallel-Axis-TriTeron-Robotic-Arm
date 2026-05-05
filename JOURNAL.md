---

**Title:** PATRA (Parallel Axis TriTeron Robotic Arm)  
**Author:** Sunrit Hazra  
**Description:** A Hybrid robot architecture of a kinematically linear 3 DOF parallel axis triteron system and a 6 DOF serial robotic arm.  
**Created on:** 2026-05-02  

---

# Day 0: Flashback

A Random Day in December, 2026, I was scrolling through my YouTube feed. I came across this [video](https://www.youtube.com/shorts/74T0LF2l5Ck) with Tripteron Robot concept, and immediately my mind was blown up due to the awesomeness and coolness of the robot. I immediately had the idea to add a robotic arm to its head, to make it even cooler and more usable.

---

# Day 1 — 10.04.2026: Planning & Studying

Ever since I was a member at Hack Club, I wanted to make a tripteron robot (which I call a tri-teron). Originally, I thought of doing this project in Blueprint as two seperate modular projects: TriTeron Robot for $400 and Robotic Arm for $400. But, Blueprint ended even before I could start. So, I chose Fallout. But I did not start because I was busy doing Construct and Stasis at the same time, and I also became a little lazy later on.

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

**Total time spent: 5h 54m**

---

# Day 2 — 11.04.2026: The First Pitch

I guess it was time for the pitch finally. This was my first pitch out of two. I had made a very rough plan in my mind, went to ChatGPT to get it sanity checked, and then I sat with a paper in my hand and drew what I could think of about the robot. Then, I spent some hours researching about the parts in Google and JLC. I also used a bit of AI to search in unknown websites for the parts. Then, I came up with a very rough estimate of the parts and the BOM. Initially, my target was to spend maximum $500 for the TripTeron and $500 for the 6 DOF robotic arm.

I was so much confused with my plan that I drew up 7 different drawings of the thing I want to make. I have not started modelling yet, so I have no idea about what I am doing. But still I want to pitch, I don't know why. Maybe just because I want to see the reaction on people. Will they react like me to the idea?

After that, the draft of the pitch was ready. I manually searched up everything and wrote the BOM. Then, I pitched it in the #forgery channel, waiting for insights. I saw some suggestions and reactions.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/afd7d77b-3889-44e8-b776-08f510aa0ad4" />

Personally, the most frustratirng thing was the fact that I have a pen and a paper with a simple drawing and list of things I have no idea about, and when I search that, there are so many options that I am overwhelmed. I learned about a lot of types of Linear Guides, Rails and NEMA motors.

**A little fast forward:** This project was returned for changes by the reviewer on **14th April, 2026**. I did not make any changes as he said, but my overall plan had changed a lot! So, I re-pitched offically on **30th April, 2026**.

**Please note that I did not use AI for any fields of the pitch. I have only used it to search the sources of my parts (pretty much like Google, but better). Then, manually I visited the sites and made the estimates. Please try to understand.**

**Total time spent: 4h 42m**

---

# Day 3 — 12.04.2026: Starting to Model

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

Now, I have two things to do now:

1. Scale everything down, including the arm, and use 500 mm rail.
2. Get relieved from the stress by ignoring the rails, and actually working on the carraige.

I first, scaled everyhting down, including the arm. I literally spend an hour making ajdusments related to the arm placement, and more importantly, seeing that if I can even make the arm smaller in real life. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/19ec1236-b435-48a9-bfb8-c7fb5c37ef8a" />

I really wanted to keep my arm at the exact size of Meca500, I really don't want to do this. For contuinuing the option two, I had to go to JLCMC, and individually choose smaller variants of each part, making sure the usable length remains at 500 mm. And after three hours of endless cadding, this is what I got:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/51f2d2e0-dca3-43d2-9c9e-54db52e20baf" />

It just looks wierd. I have to have a better solution to this! But still, this is quite expensive. But surely this is cheaper than the 1 metre travel length one.

Now, I am really tired after all of this.

I chose the second step, for the time being. I was so disappointed by how it looked, I literally deleted all of the things I imported from JLCMC, to continue fresh. What I basically did was that unlike Rowan's design, I am going to make the carraige completely independent, so I will add motors seperately to the carraige. For that, I extended the base of the carraige and for that I used extrusions on the frontmost face, and modified the design, maaking it possible to make the rails wide and to let me use ball screw. So, I continued modelling for more hours and this was the result. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/28d18e54-e5e2-471f-a430-8d8cc5a90f1b" />

If you want a rough picture of how I did the CAD throughout today, [here](https://drive.google.com/file/d/17hyzQvfrPkSDDIoYjY-ttWvvfYUGDrAG/view?usp=sharing) is a timelapse-like video, where I have smartly exploited the Fusion Timeline. I'm glad Fusion is parametric.

Well, in this one single day, I did so much (at least for me) due to my dedication and curiosity. I really hope this pays of well.

**Total time spent: 7h 22m**

---

# Day 4 — 13.04.2026: The CAD Failure Day

Today I planned to ignore everything that was frustrating. I decided to do something else than the linear rails. I decided to add motions by adding As-Built Joints. First, everything was going by well, but after adding the joints in the X and Y leg, there was a lot of mess! Just look at the mess, there are joints everywhere, but everything is messed up like crazy.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/492c4516-e10d-4c0a-946f-2e5b47b9d086" />

But I then thought of dropping this, and I instead scaled the tripteron up by 1.5x. The rail is still 500 mm. I did this because I want to keep the Meca500 at the original size. I also noticed that the two sides of the tripteron were asymmetric, so I used split body and deleted things fom one side, then scaled them

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/93acdf6c-3b9c-457f-8c5d-3f718d41657e" />

You can see that the tripteron barely has any space to move. I know this is really bad, so I am now thinking of making the rail 600 mm. I hope that it would not escalate the costs much. So, I went and actually checked that by making a completely new BOM from scratch on a paper, which took a lot of time.

Now, I again added motions to the legs one by one for each leg, which was quicker than the previous step at arm-to-arm joints, but to the slider, the joints did not make any sense. So, I had to go back the timeline and I had to find at which exact step I scaled the things, then, I also scaled the slider, but that just increased my problems more. After adding more motions to the remaining newly scaled parts, the robot moved as expected. This was probably the only time so far I feel like I did something that actually works.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/667bc22a-e696-4321-8b5e-c26f8a8732b1" />

Continuing my frustrating design journey, I:

* Made the tool head of the tripteron bigger so that the base of the Meca500 fits perfectly on the top, for about 10 minutes
* Scaled everything down again due to motion conflicts and again scaled up by 1.25 times, then edited the timeline to make it 1.5 times, for about 1.5 hours
* Tried to make the carraige slider length shorter to ensure that the robot has place to move, for about 40 minutes.

Problems I faced due to the previous actions:

* Tripteron looks bulky and disproportionate, and in other words, ugly.
* Got frustrated and bored out of my mind at the same time.
* Found out that the tripteron motions no longer make sense, and I messed up, again!

To fix that, I completely overcame the changes, except the scaling. I deleted all the joints, and I decided to start fresh again. My plan doesn't make any sense anymore at all.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/183ff45a-b18b-4c35-99e1-2a7a8030f256" />
<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3c7e5950-0ebe-4217-807d-f8d1e3b2d580" />

Now I literally feel like quitting. I have not yet got any response on my pitch. I don't know if this would be approved, but still I am working so much, and even before getting started, I feel like quitting.

I don't know what now, but I guess I will just wait for the pitch review.

**Total time spent: 5h 40m**

---

# Day 5 — 14.04.2026: Post-Pitch-Review CAD & Research

I got my first [response](https://hackclub.slack.com/archives/C0AQG3VPQDD/p1776140495172719?thread_ts=1775931663.812209&cid=C0AQG3VPQDD). The reviewer did not actually point out any problem in my project, just very randomly suggested something obvious. But he gave a really good suggestion with the driver and the site selection for ordering. His suggestions helped me think in a different approach.

Nontheless, I am thinking of chaning my plan a lot. What if...

* I used 1 metre rail instead of 500 mm rail?
* I kept the robotic arm at the original size of Meca500?
* I made the tripteron 1.75 times bigger than the original design on [Rowan](https://www.youtube.com/@NoEngineerHere)?

It might seem like I am either living in a dream or increasing my budge to like $1200, but actually, I am just trying a different approach. Firstly, I spend absoluetely about an hour and half on scaling up and down my model, trying with different length rails and different linear guides. I imported many models in Fusion and tried each on the robot.

I manually calculated the rough torue needs for my project, and I can conclude that about 1.1 Nm of torque could do the job. I can either use the best NEMA 17 motors, or the the most decent NEMA 23 motors. JLCMC has a lot of options to choose from, so I did my majority research on JLCMC. I also read some datasheets.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c2d27b79-ea12-4ee8-9492-0111a22336d0" />

To be specific, I added 42CM08 motor model to Fusion to check if I can even fit in two seperate motors on the carraige itself, according to my original plan. I failed horribly. I was horribly wrong. The motors will take up a lot of space, and make the carraige a lot bulkier making my project expensive. I tried placing it where both Rudmin and Rowan did, and only this felt right. I also tested with 600 mm 4040 t-slot rail from JLCMC, but that too felt small for my plan.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/927c9935-bbf2-4ddb-8740-0aa628d0fd2a" />

So, seperate from my previous two BOMs, I made another to make new estimates. The numbers were going up so fast, I paused and thought og trying a completely different approach.


Today, I decided to only do research on the market price of the tings I need, instead of just researching on what I need.

I researched on the following:

* Linear Guides: I found out that to avoid customs, you got to use local brands or companies with branch in India. So, I chose HIWIN for my linear guides and linear rail blocks on MISUMI India, Igus India and HIWIN India. But [Robu.in](https://robu.in/product/mgn15h-linear-guide-rail-1m-2) also offers a really good option.

<img width="1365" height="644" alt="image" src="https://github.com/user-attachments/assets/e1b173d1-539e-4f4c-ae64-032af907a4cf" />
  
* Ball Screw: This one was confusing, as all sites showed very high price. I have researched mostly in [JLCMC](https://jlcmc.com/product/s/B04/BSAF-C7-15/rolled-ball-screw-with-sfar-nut-shaft-diameter-15mm-lead-5-10-16-20mm), and [Robu.in](https://robu.in/?s=ball+screw&post_type=product&dgwt_wcas=1) Anyways, for the ball screws, I am choosing Novo3D or MISUMI.

<img width="1365" height="643" alt="image" src="https://github.com/user-attachments/assets/94d822a2-227d-4ba3-9b91-b816021f0f6d" />
  
* 4040 extrusions: For the [extrusions](https://robokits.co.in/mechanical-parts/aluminium-profile-accessories/astro-anodized-heavy-duty-industrial-grade-aluminium-4040-t-slot-profile?srsltid=AfmBOoqKFxp7iACSQkkYpdlSToUPKQh1cB2N3_JJ_hqWzN5CCDY8bWU9) I am choosing Robokits, as it is really cheap. But the problem is that I am not sure if their drawing is correct.

<img width="1365" height="575" alt="image" src="https://github.com/user-attachments/assets/2846e072-1fa1-45e1-99d3-64ca3d49b956" />

I started working on my BOM, again. This time, I made two rough seperate BOM. One for parts I am sourcing from India, and other where I am sourcing parts from JLCMC. Then, I added in the shipping costs and estimated customs charges. The result was that I have to source parts only from India.

For instance, here is my JLC cart for only three items:

<img width="802" height="586" alt="image" src="https://github.com/user-attachments/assets/55236b4e-1783-4af0-b474-7656325379a4" />

Just look at the prices of even the cheapest shipping. And then there is additional 35 to 50% customs. I am not doing this from JLCMC.

<img width="252" height="393" alt="image" src="https://github.com/user-attachments/assets/9330b45f-b0b7-40d3-b304-788b8fe47754" />

I used the same BOM I made today for re-pitching my idea at Forge on 30th April, 2026.

**Total time spent: 4h 45m**

---

# Day 6 — 30.04.2026: The Final Pitch

Today, I [pitched](https://hackclub.slack.com/archives/C0AQG3VPQDD/p1777518863427759?thread_ts=1775931663.812209&cid=C0AQG3VPQDD) my project PATRA for the final time in Forge channel. To do this, I kept the description same as the previous pitch, made very minor changes overall. But the most significant change was with the BOM.

I don't know if this is my fifth or sixth BOM, if I ignore those BOMs I wrote on paper out of frustrtion. Majorly, I chose to keep the rail 600 mmm usable travel. I had to do very less research this time. I researched about 40 minutes on the internet to find the components, and I improved the previous BOM. Now, even at this moment, I am not finalizing the sources from where I will buy, but just for an estimate, I have given example sources. This is just a rough assumption based on the mean prices. So, here's what's finalised for the pitch:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d54c1631-461d-43ca-88dc-c4519b394e03" />

Ball Screw & Supports
SFU1605 Ball Screw (650 mm) + Nut (C7) – ≈ $70 USD
Example reference (international, similar spec):
https://www.vxb.com/products/sfu1605-ball-screw-650mm-cnc-kit
BK12 + BF12 Ball Screw Support Set – ≈ $20 USD
Example support units:
[Link](https://robokits.co.in/mechanical-parts/ball-screw-accessories/bk-bf-support-blocks)

Linear Motion
MGN12 Linear Rail – 500 mm (2 pcs) – ≈ $45 USD total
Example rails sold in India:
[Link](https://www.amazon.in/ReliaBot-Linear-Carriage-Printer-Machine/dp/B07VCLN7KM)
MGN12 Carriage Block (4 pcs) – ≈ $40 USD total
Same Indian rail listing provides blocks.

Belt Drive (Light Axes)
GT2 / HTD 5M Belt (15 mm width, 3 m) – ≈ $25 USD
HTD belt example (Indian marketplace or Amazon):
[Link](https://www.amazon.in/Timing-Belt-Gear-Pulley-Printer/dp/B07W4J5PGF)
HTD 20T Aluminum Pulleys (4 pcs) – ≈ $20 USD
Example pulleys:
https://www.amazon.in/Timing-Pulley-Bore-6mm/dp/B08CXZ7VMH

Frame + Structure
4080 + 4040 Aluminum Extrusion (cut locally) – ≈ $170 USD (combined)
Sources for Indian extrusion retailers with custom lengths:
Search on India marketplaces like Indiamart for:
“2040 T-slot aluminium extrusion all lengths”
“4040 T-slot aluminium extrusion custom cut”
Example extrusion supplier:
https://www.indiamart.com/proddetail/aluminium-t-slot-extrusion-6762050720.html
Aluminum Plate ~10–12 mm (Custom CNC cut) – ≈ $70 USD
Local metal supplier or shop near you can cut to size.

Motors
NEMA 23 Stepper Motor (2 pcs) – ≈ $80 USD
Example NEMA23 listings in India:
https://robomart.com/product/stepper-motor-nema23-10kgcm-torque-with-pulley
NEMA 17 Stepper Motor (3 pcs) – ≈ $60 USD
Example affordable NEMA17 bundles:
https://www.amazon.in/Stepper-Motor-17HS19-1684S/dp/B07Q5QDLFK

Drivers & Power
TB6600 Stepper Drivers (2 pcs) – ≈ $30 USD
TB6600 driver example:
https://www.amazon.in/2-Axis-Stepper-Motor-Driver/dp/B01MTOYCRA
TMC2209 Drivers (3 pcs) – ≈ $30 USD
TMC2209 driver example (widely in Indian hobby stores):
https://dc3d.in/shop/voron-v2-4-parts/bigtreetech-tmc2209-v1-3-stepper-motor-driver
24V 10A Power Supply – ≈ $30 USD
Example PSU (India):
https://www.amazon.in/Antratek-Switched-Mode-Power-Supply/dp/B08BWGRYT4

Controller / I/O
Controller Board (STM32 / GRBL / 32-bit board) – ≈ $30 USD
Affordable motion control board:
https://www.amazon.in/NCStudio-Controller-Mach3-USB-Port/dp/B08CHY7CC8
Limit Switch Set – ≈ $10 USD
Mechanical limit switches:
https://www.amazon.in/20-Pack-Micro-Limit-Switch/dp/B08VRWCC5C

Miscellaneous
Flexible Shaft Couplers (Pack) – ≈ $15 USD
Example flexible coupler:
https://www.amazon.in/Flexible-Coupling-Shaft-Connector-12mm/dp/B07D3DB5NJ
Fasteners, Bearings, Wiring, Cable Ties, Misc Hardware – ≈ $40 USD
Local hardware store — widely available

Estimated Total
SectionEst. CostBall Screw & Support~$90Linear Motion Rails & Blocks~$85Belt Drive Components~$45Frame & Plates~$240Motors~$140Drivers & Power~$90Controller + I/O~$40Misc Hardware~$40Total≈ $700 USD

**Total time spent: 1h 05m**

---
