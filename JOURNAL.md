---
**Title:** PATRA (Parallel Axis TriTeron Robotic Arm)  
**Author:** Sunrit Hazra  
**Description:** A Hybrid robot architecture of a kinematically linear 3 DOF parallel axis triteron system and a 6 DOF serial robotic arm.  
**Created on:** 2026-05-02  
**Progress (%): 25%**
---

# Day 0: Flashback

A Random Day in December, 2025, I was scrolling through my YouTube feed. I came across this [video](https://www.youtube.com/shorts/74T0LF2l5Ck) with TriTeron Robot concept. The mechanics were immediately impressive — a clean parallel axis system with a movement profile I hadn't seen in a hobbyist build before. The logical extension was obvious: mount a robotic arm on the head, and you get something that combines the workspace coverage of a gantry with the dexterity of a serial arm. I thought that is really cool.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ff8585a7-c18c-4249-9e0b-f1dbca4265bf" />

**Total time spent: 0h 1m**

---

# Day 11 — 08.05.2026: Kinematic Base Module (KBM) Progress — Part 1

I began by making some changes to my existing model, as I came accross some problems while continuing my modelling. For making the changes I had to search a lot, in many websites, and download a lot of stuff to import and see it would work. Anyways, the changes are as follows:

1. I replaced model of [E-BMN15H-2-L1000-ZF-C-E20](https://jlcmc.com/product/s/B03/E-BMN/economical-linear-guide-mini-standard-type-7-9-12-15?k=E-BMN15H-2-L1000-ZF-C-E20&productModelNumber=E-BMN15H-2-L%5B70~1800%2F1%5D-ZF-C-E%5B0~39%2F0.5%5D) from JLCMC with [MGN15H](https://www.traceparts.com/en/product/hiwin-technologies-corp-mgn15h?Product=90-07042020-029729) from TraceParts, as I saw that the rail was a little different from what I am buying from Robu.in.

2. I replaced [NEMA23 PR57HS51](https://robu.in/product/nema23-pr57hs51-2804-10-1kg-cm-stepper-motor-round-type-shaft) with [NEMA23 PR57HS76](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft) as I realized I needed more torque.

This ensures that my model is accurate and the robot is stronger and more stiffer. The first motor provided 10 Nm torque, but the new one provides 18.9 Nm torque.

I then took a lot of inspiration from the LC4O family specifically, [LC40B-KM02](https://www.zaber.com/products/linear-stages/LC40B-KM02/specs?part=LC40B1000-KM02&srsltid=AfmBOootwqUCUVAZim0fLhepMvoiqAwhXvtNfsj9dF_MdNFuC1e7YDq7)] for my linear rails. I continued with updating my model with the aforementioned changes, and then I added As-built Slider joints and grounded components to parents.

I then started finding the model of NEMA 23 motor which matches length of 76 mm, and after a few minutes of searching, I found [this](https://grabcad.com/library/nema-23-stepper-76mm-1), which matches my needs exactly.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/09f7862c-0b30-4d3f-b97b-9d546d787af9" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7ebeb4bd-72df-41c9-9a42-41edee29db31" />

**Total time spent: 3h 35m**

---

# Day 12 — 09.05.2026: Kinematic Base Module (KBM) Progress — Part 2

I continued working on the first stage. Previosly the motors were not aligned. So, thsis time I imported [NEMA23 mounting bracket aluminum](https://grabcad.com/library/nema-23-stepper-motor-mounting-bracket-1) and added it to the assembly. Then I added joints and then I duplicated it with joints, and made it symmetrical.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1be429f0-4029-4d24-aed7-e011c30ab6b9" />

I continued working on the first stage from the point where I had finally fixed the motor alignment issue. Previously, the motors were floating in space without a true structural reference. This time, I decided to anchor everything properly. I imported the [NEMA23 mounting bracket aluminum](https://grabcad.com/library/nema-23-stepper-motor-mounting-bracket-1) and placed it onto the 4040 extrusion. Once positioned, I constrained it fully using rigid joints, then duplicated the entire bracket assembly along with its joints and mirrored it to maintain symmetry. That symmetry mattered.

After locking down the brackets, I moved toward the belt architecture. I made a deliberate decision here: instead of an offset belt system, I wanted a stacked belt configuration. That means the belt would pass directly above the linear rail, and specifically above the linear block. Much like the design architecture of Rudmin.

Next I started making sketch for the belt path. I wanted to make a stacked belt architecture rather than an offset belt architecture, which meant that I had to make the belt directly go above the linear rail, above the linear block.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e21f17be-be3d-4bf3-b5af-a4351a50c4ba" />

To calculate the radius needed for the sketch, I calculated the height of the belt from the upper face of 4040 extrusion. So I began calculating the stacked height from the top face of the 4040 extrusion.

The linear rail selected is MGN15H mounted directly on the extrusion. From datasheets and model measurements:

4040 extrusion height: 40 mm
MGN15 rail height: ~10 mm
MGN15H carriage block height above rail: ~16 mm

This places the top of the carriage approximately 26 mm above the top face of the extrusion. Since I wanted at least 1.5 mm clearance between the belt and the carriage body, I set the belt centerline at 27.5 mm above the extrusion surface. That dimension became critical. It defines pulley mounting height, motor shaft alignment, and idler spacing.

With a 20T HTD 5M pulley:

Pitch = 5 mm
Teeth = 20
Pitch diameter ≈ 31.83 mm
Effective radius ≈ 15.9 mm

That means the motor shaft center must sit approximately 27.5 mm above the extrusion to maintain belt alignment. The bracket placement now isn’t arbitrary — it’s dictated by pulley geometry. This cascades into spacer requirements between the bracket and extrusion, and potentially washer stacks or a custom motor riser plate.

The return path of the belt is still unresolved. In stacked architecture, the return must pass either:

Below the carriage plate
Or through a recessed idler channel

In my first attempt, the return belt passes through the extrusion, as you can see, which is not possible.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/06d7271c-2b51-42ac-9e56-7a48c3481b45" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8dc7c24e-bc87-4dfd-af5a-108549bc5b21" />

Thus I redrew the sketch and brought it lower, and things improved a bit.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3717f365-194a-48fe-87bc-de2f4361b503" />

It still operlaps. I guess this is all for today, next day I will continue this.

**Total time spent: 3h 30m**

---

# Day 13 — 10.05.2026: Kinematic Base Module (KBM) Progress — Part 3

I picked up exactly where I left off yesterday. The return belt was overlapping with the 4040 extrusion geometry, which was not okay. It meant that I had to continue on one or more than one of the following paths:

1. I eradicate the NEMA23 mounting bracket and make my own mounting bracket, for 3D printing it
2. I keep the NEMA23 mounting bracket but position it below the 4040 extrusion, making the architecture prone to more bending and atress
3. I use a pulley with a bigger and possibly unnatural diameter, that must be sourced from either big stores or custom made
4. I add two more pulleys to position the return belt to the bottom, making the system contain more moving parts
5. I replace the 4040 t-slot extrusion with 4040 double t-slot extrusion, that has a hollow inside but is more expensive

I first tried path 2 and 5.

* For path 2: I tried repositioning the brackets after supressing the joints, the system seemed to work till I realize that it has become too fragile to take the mass of PATRA, so I dropped it.

* For path 5: I first surfed the internet to look at the prices. After looking at 6 to 7 different websites, I has already realised it is more expensive. [This](https://www.3dprintronics.com/products/t-slot-aluminium-extrusion-4040-6mm?srsltid=AfmBOopm2YIEr6eGFaIxCXIP6218Ygof1mdUS4i0Hx8fKVX-2w-9lQBm) one from 3DPrintonics for example costs 3200 INR per metre, [this](https://www.indiamart.com/proddetail/machifit-4040-double-t-slot-aluminum-extrusion-40x40mm-aluminum-profile-extrusion-frame-based-on-2020-for-cnc-25967776433.html?srsltid=AfmBOoq9RSyFu8JxcKxos3uZti6KXIaZwqFABJFlg8DoPGHpWxLGqibd) from IndiaMART costs 20272 per piece, and [this](https://novo3d.in/aluminium-profile-4040/) from Novo3D costs 2399 INR. Since this was reaching almost double the cost, I had to drop this.

Then I chose path 1 and 3, where I did the following:

Firstly, I removed the [NEMA23 mounting bracket aluminum](https://grabcad.com/library/nema-23-stepper-motor-mounting-bracket-1) and then started sketching my Motor Mount/Case, and extruded out components, for path 1. The goal was to reduce unnecessary thickness and directly control the stacked height.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6b605459-58ce-43a1-9f27-4eda4eea2bff" />

Then I extruded 5 mm from the sketch and checked if it looked like an aliminium bracket, and yes it most certainly did. It actually looks nice. Five millimetres gives enough wall strength for prototype testing, especially since I will print at 100% infill.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7b8a2753-0217-4d92-8411-f706a8ac02f6" />

Next I copied the wall on the other side and added walls to make it an enclosure. This enclosure now supports both the pulley and the idler region while also acting as structural reinforcement.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/061a2c0c-059f-4b4a-94ee-1a83cfb2d6ba" />

I mirrored the component on the other end of the system for the idler.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/760eb93a-cd02-47ef-aa43-ea68cba2b583" />

This made a nice looking enclosure than can house beth the idler and the pulley, completing the whole system.

Secondly, I surfed the internet (for a long time) to find the pulley I needed. After checking in both [JLCMC](https://jlcmc.com/product/C03/timing-belt-pulleys) and [MISUMI India](https://in.misumi-ec.com/vona2/mech/M1000000000/M1002000000/M1002030000/), and I realised that MISUMI is more expensive than JLCMC, but when we add shipping and customs, MISUMI is the cheaper and smarter choice. Additionally, MISUMI has a lot of configurations available with 3D model, just like JLCMC.

I chose [this](https://in.misumi-ec.com/vona2/detail/110310532889/?CategorySpec=00000005784%3A%3Aak%2C&list=PageCategory) pulley from MISUMI that costs 1,064.73 INR for now. But there is a problem: The minimum bore diameter available is 10 mm, but I need 6.35 mm, as NEMA23 PR57HS76 has 6.35 mm bore. I will see what I can do make this structurally correct. Anyways, I added it to the BOM, and downloaded the STEP files. I need two of them.

Next, for the idler I am choosing [this](https://in.misumi-ec.com/vona2/detail/110310533069/?CategorySpec=00000005784%3A%3Aak%2C&list=PageCategory) from MISUMI that costs 1,621.82 INR each. I added it to the BOM, and downloaded the STEP files. I need two of them.

I updated the BOM with the nescessary changes.

But after I imported the components in Fusion, I noticed that the diameters are too small for the belt, which meant that the belt could either brush against the linear guides, lower face of the 4040 extrusion, or even worse, that is both. The pitch diameter of HTD5M pulley increases with tooth count, so I kept increasing teeth count to raise the belt path vertically.

So, I kept experimenting with higher and higher teeth count pulleys and idlers, until I was tired.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b769cea5-9b0b-4c1e-9a57-bbd19f94de39" />

Everytime I deleted the older ones so that everything stays organised. I even updated the BOM almost everytime.

The next logical thing was to try something else. So I did. I looked for the belt. And after surfing the internet a little and then JLCMC, I found the perfect component from MISUMI, which is [this](https://in.misumi-ec.com/vona2/detail/110310527489?HissuCode=C-HTBN2350H5M-150). It costs 1667 INR, and has MOQ of 2, and I do need two of them.

I immediately added it to the BOM and imported the model in Fusion, only to realise that it was completely useless to import the belt in Fusion. The belt geometry is better controlled parametrically through pulley pitch diameter and center distance rather than solid modelling the flexible body.

**Total time spent: 5h 05m**

---

# Day 14 — 11.05.2026: Kinematic Base Module (KBM) Progress — Part 4

I picked up exctly where I left off yesterday out of tiredness. I thus continued with 30T for the pulley and 28T for the Idler. It didn't fit. The pitch diameter difference caused uneven belt alignment and clearance issues.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7843fda2-afc5-4a4e-9d00-11b9f5b18972" />

Then I tried with 32T for both, and that was the biggest configuration possible in MISUMI. Increasing tooth count increased pitch diameter and therefore belt elevation above the extrusion.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7843fda2-afc5-4a4e-9d00-11b9f5b18972" />

It did work better, but I am not completely satisfied. But I guess that is okay enough. With 32T HTD 5M, pitch diameter is roughly (32 × 5) / π ≈ 50.9 mm, which gives noticeably better clearance than 28T or 30T.

Next I added motions and assembled everything cleanly and strategically. The system was almost ready. Only the enclosure for the pullies and idlers don't have a hole passing through them that will allow the belt the move. That slot needs to be dimensioned carefully to prevent belt rubbing while maintaining enclosure stiffness.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d6919113-ca2d-4851-8f12-f6a25b61f894" />

I then mirrored the whole system. At this point, the first stage belt-driven axis is structurally defined: 1 metre 4040 extrusion, dual MGN15H rails, stacked belt architecture, symmetric pulley housings, and increasing tooth count to solve geometric interference rather than compromising stiffness.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/23017fbc-4351-45dc-b2bf-39eed43d4a6b" />

The system is beginning to look like a machine instead of an experiment, I guess.

Next I updated the BOM with all the nescessary changes for the following confirmed components:

* [Pulley C-HTPA32H5M150-A-N10](https://in.misumi-ec.com/vona2/detail/110310532889?HissuCode=C-HTPA32H5M150-A-N10)
* [Idler C-AHTFW32-H5M150-12](https://in.misumi-ec.com/vona2/detail/110310533069?HissuCode=C-AHTFW32-H5M150-12)
* [Belt C-HTBN2350H5M-150](https://in.misumi-ec.com/vona2/detail/110310527489?HissuCode=C-HTBN2350H5M-150)

Next I made a financially smart move. Since the components were getting a lot expensive, I thought of looking for aluminium extrusions from MISUMI, just in case they were cheap.

And yes, they were cheaper than my previous sources. For instance:

* The previous 4040 extrusion was 1060 INR each, but [this](https://in.misumi-ec.com/vona2/detail/110310647549?HissuCode=LCF8-4040-1000) from MISUMI is 840 INR.
* The previous 2020 extrusion was 469 INR, but [this](https://in.misumi-ec.com/vona2/detail/110311047509?HissuCode=LCF6-2020-1000) from MISUMI is 270 INR.

I made all the nescessary changes to my BOM.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/520b13aa-1c0d-40bf-8948-abd0dd6bfb1a" />

<img width="2558" height="177" alt="image" src="https://github.com/user-attachments/assets/3b9d02b1-f401-42bd-8245-92cd46964f41" />

**Total time spent: 4h 10m**

---

# Day 15 — 12.05.2026: Kinematic Base Module (KBM) Progress — Part 5

It was now time to add the holes to the pulley and idler mount so that I can make the belt pass through and clamp, thus completing the tensioning system.

I first made a sketch on the face of the Pulley Mount then, added some clearence. Then I extruded the shape to make the hole in both Pulley and Idler Mounts. It was looking like this after the changes made.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/37b08a2a-0b90-4dc1-ba34-86576ad714a9" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/85ae9d22-ca44-41ac-b40b-6ec78bc119ce" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9277f371-8e86-4bfc-9a9e-6571b7188e84" />

Next I moved to the Linear Block Carraige system that was supposed to be the base of the legs of the robot and also secure the ends of the linear belts. First I made holes in both the Carraige and the belt. I reaised that it is a very poor choice as it will damage the tensioning system.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6f9b8aba-2a50-417b-9652-3d1fb08ed518" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/07d7dbfc-0ad4-4e05-b15f-d4697945e52d" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8b60f254-fc23-45ab-925b-4cdd2400e97a" />

Then I surfed the internet to find a blet clamp for HTD 5M 15 mmm width belt. I found [this](https://www.traceparts.com/en/product/madler-gmbh-fixing-plate-for-timing-belts-made-from-aluminium-profile-htd5m-for-belt-width-15-mm?CatalogPath=MADLER%3AMADLER_NEU.3.3&Product=90-14112023-038068&PartNumber=17339900) from TraceParts, and then I imported it.

**Total time spent: 0h 55m**

---

# Day 16 — 14.05.2026: Kinematic Base Module (KBM) Progress — Part 6

This time I started by looking for the belt clamps. I searched in the internet and found nothing from India. I had high hopes on MISMI, but even though they had other types of Blet Clamps, they did not have HTD 5M belt clamps.

I had the change strategy, so I decided to 3D print the clamp along with the carraigeS. Thus I modified the 3D model I imported the previous day, and positioned it perfectly on top of the MGN15H linear block first. Then I continued shaping it using extrusions and alignments.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c3553f60-bc46-418e-a176-68216480589d" />

I made the holes for screws, it started to look like this. Now next step was to add the upper carraige that was modeled before. I jst need to make some little adjustments to the existing model.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/306069be-f0e5-4b1c-9f2e-b32633772a40" />

This is how it looks with the belt:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7868781e-554a-4602-b6be-3970036fc104" />

But unfortunately, I came across a really annoying problem. The thing was that the numbers related to the positions and the dimensions were not round numbers, but off my ±0.002 mm and even ±0.0005 mm. If you look at the image bellow carefully, you can see the numbers don't make any sense. Additionally, the pulley and idler cases were off by ±0.02 mm. Furthermore the belt profile was ±0.319 mm off.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0fe15352-3f96-408b-b2ae-da1c584ee614" />

But I even put my hands on it in the first place because I use the project tool on new sketches. And when I noticed that the extrusions based on the projected faces were not symmetrical, I knew I had to fix it.

The fact that the numbers were round, and the non-sensible numbers on top, made my head scratch. I realised that Fusion rounds off numbers beyond ±0.000X.

I did get it over with.

Once the profiles and the facail projections were fixed in the sketches, I continued with modifying the carraige. I first positioned it properly, then joined them, after adding holes of the screws.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/161bbe9e-ee2a-43b0-8717-3f21daf11665" />

Next using Cut feature, I integrated the lower belt clamp with the carraige, and joined them.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a0296509-dc15-43cc-b936-eee526fb45e8" />

Next up I copied the carraige to another linear block and then I removed the belt clamp and added clearence for the belt to pass through any interference. This will be one of the Z axis carraiges, and it will be controlled by the central belt system which I am yet to model.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e9dd7fd5-8a76-4d97-b121-9d8107260298" />

Followed by that, I mirrored my components to see how the system looks, though I know that this has to updated soon afterwards.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a9d7cc34-31dc-461f-8708-ded7da177162" />

Then I made some more changes to the name and hiecarchial structure of the components before signing off.

**Total time spent: 3h 05m**

---

# Day 17 — 15.05.2026: Kinematic Base Module (KBM) Progress — Part 7

I had to know work on the motions that will enable me to see how the system actally works. So I started with adding motions to the tensioning system, after I watched [this](https://www.youtube.com/watch?v=_inMtaRoYMw) video.

But after that I realised that I actually don't need that. So, instead I switched focus to somehting more useful. That was continuing with the the Z axis tensioning system. The X and Y axis tensioning system was completed already.

For the system I first extruded out the 2020 aluminium extrusion by 15 mm and then continued by moving the Pulley System.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4b2cd11c-3054-4da1-a89f-d006ab2fe5bc" />

Next I can not use 32 toothed this time, instead I need a smaller diamter pulley because of the following reasons:

1. The height has to be lower than the x and Y belts.
2. The return belt must be closer to the extrusion.

I made one small adjustments mid-way, which was to position the 2020 extrusion vertically centered to the 4040 extrusion. Then I drew a sketch based on my intuitions, and extruded it to make a belt which can be updated later from the sketch.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d8bbe37d-7e83-4c93-ad7e-de5ae203bb6a" />

Followed by that, I searched for pulleys and idlers from MISUMI. I found [this](https://in.misumi-ec.com/vona2/detail/110310532889?HissuCode=C-HTPA14H5M150-A-N8) pulley which has 14 teeth. But the problem came when I searched for an equivalent idler which has 14 teeth, and I found none. So, I used this in the belt just to see.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/da01ae3b-6a1f-44d9-b7ff-e0825ea1db69" />

I had tried 20T, 22T but then I also saw there was MOQ of 2, and it was really expensive. After several changes to the confugarations, I chose to use I decided to source my parts from JLCMC instead, which I will do later on.

Bored of what I was doing I started drawing a sketch based on my previous belt that I extruded from the sketch. I tried with 20T as well and even 22T. My attempts were not random but actually structured, based on HTD 5M pulleys:

| Teeth | Pitch Diameter (mm) |
| ----- | ------------------: |
| 14    |            22.28 mm |
| 15    |            23.87 mm |
| 16    |            25.46 mm |
| 18    |            28.65 mm |
| 20    |            31.83 mm |
| 22    |            35.01 mm |
| 24    |            38.20 mm |
| 25    |            39.79 mm |
| 28    |            44.56 mm |
| 30    |            47.75 mm |
| 32    |            50.93 mm |

I had to change the sketch several times by changing the center-to-center slot several times based on the table above. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/470e2050-4b8f-4a0a-99ba-16d01980fe5b" />

**Total time spent: 2h 00m**

---

# Day 18 — 16.05.2026: Kinematic Base Module (KBM) Progress — Part 8

I started exactly on the point I ignored the previous day: sourcing the pulleys and idlers from JLCMC. I first began by searching for the exact same parts that I had chosen in MISUMI, and here's what I found:

* For the [Pulley C-HTPA32H5M150-A-N10](https://in.misumi-ec.com/vona2/detail/110310532889?HissuCode=C-HTPA32H5M150-A-N10) I found [CBYL-AH1-5GT150-32-A-N-d22](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-32-A-N-d22&productModelNumber=CBYL-AH1-5GT150-32-A-N-d22) from JLCMC.

* For the [Idler C-AHTFW32-H5M150-12](https://in.misumi-ec.com/vona2/detail/110310533069?HissuCode=C-AHTFW32-H5M150-12) I found [CBYL-AH1-5GT150-32-A-H-d22](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-32-A-N-d22&productModelNumber=CBYL-AH1-5GT150-32-A-N-d22) also from JLCMC. I was unable to find idler with teeth, so I am choosing this, with double 625ZZ bearings.

* For the Z axis pulley and idler, from JLCMC I found [CBYL-AH1-5GT150-18-A-H-d6.35](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d6.35&productModelNumber=CBYL-AH1-5GT150-18-A-H-d6.35) and [CBYL-AH1-5GT150-18-A-H-d16](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d16&productModelNumber=CBYL-AH1-5GT150-18-A-H-d16), respectively.

But soon I realised that the parts I had sourced are not HTD 5M compatible. This meant that I had to use different belts and probably even different belt clamps. I tried searching for HTD 5M pullyes from JLCMC, but I found none.

Since I was buying from JLCMC, there was a very high chance that I needed to pay customs. If I am ordering only the pulleys, I can choose E-POST and pay about $20 in Shipping and probably $10 more on customs. But still, this option is a lot cheaper than buying pulleys from MISUMI.

I then went on to research about the differences in HTD 5M and GT5 belt. I went through [this](https://www.apexdyna.nl/en/news/the-right-timing-belt) article and I found out that it actually didn't matter too much, but GT5 is actually better for my system as they are smoother. I am even finding cheap pulley for GT5, which means that it is the best option for at least now.

Next I updated the BOM

<img width="2383" height="121" alt="image" src="https://github.com/user-attachments/assets/cd373d89-e0e0-4beb-8f2b-500bea65d69f" />

**Total time spent: 3h 15m**

---

# Day 19 — 20.05.2026: Kinematic Base Module (KBM) Progress — Part 9

Now it was the time to import the the pulleyes I had selected, into Fusion.

I started by creating a new sketch for the belt. I had the estimate for diameter needed for the pulley and idler, which was 27.5 mm. I initially thought of making the case smaller than the existing ones for the X and Y tensioning systems. So small if fact that it will be directly above and below the 2020 aluminium extrusion.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b76e0e58-a223-4293-b7c8-ecc51d1bf8a5" />

I then extruded the belt profile symmetrically to have the width of 15 mm (7.5 mm both sides). Followed by that, I inserted the 32 teeth pulley and idlers to replace the existing ones and used align and joints to position them properly. in the tensioning system. I now had a rough visualisation of how to the belt would look like in the system. I made sure that I am able to later edit the sketch in case I am using different size pulleyes and idelrs.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1f74a469-235d-4991-95c8-8ab82079a3c4" />

Part of the tensioning system was completed. Next step was to updade the aluminum extrusions as I had to find a way to reinforce the pully and idler cases with the aluminium extrusion profiles.

Note that the 2020 extrusion will be 1150 mm in length, not 1000 mm. I will update that part later on, after I confirm the length.

Thus, I replaced the existing **TXCL-H7-4040E-L1000 (model from JLCMC)** with **LCF8-4040-1000 (model from MISUMI)** and the **TXCL-H7-2020E-L100 (model from JLCMC)** with **LCF6-2020-1000 (model from MISUMI)**, to ensure that I am following the exact profile that I will be buying and physically expecting.

I had previously thought that even though 4040 t slots are generic, there will be differences in profile, varying from manufacturer to manufacturer. Just as I thought, after I imported the updated 4040 and 2020 extusions, I saw that the profiles had noticable differences that coul've caused manufaturing and assembly issues.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/86ccabac-1fa1-4483-996a-58795552bf0f" />

Next I gave emphasis on reinforcing the existing pulley and idler cases to the aluminium extrusion, without using just screws. Since I got access to the correct profile, I tried to extrude certain part of the profile to have them seamlessly connected to the aluminium extrusion without relying much on screws.

About adding serews, the major problem was that the case was split in such a direction that it is hard to add screws; the minor problem being that tapping the profiles both sides from MISUMI was quite expensive. I can consider that later on. For now, I am just extruding out some part of the case.

This is how the extrusion looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1d96865c-0d6d-41f8-9a7c-bdda6a567f4d" />

I then arranged the components in the Browser and added proper materials for the appearence, and updated the BOM.

<img width="2383" height="197" alt="image" src="https://github.com/user-attachments/assets/72599af8-f03e-496e-a313-fe883cf7219f" />

**Total time spent: 4h 15m**

---

# Day 20 — 21.05.2026: Kinematic Base Module (KBM) Progress — Part 10

Previously the bare bones tensioning system involving the following:

* [Pulley CBYL-AH1-5GT150-18-A-H-d6.35 (Z)](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d6.35&productModelNumber=CBYL-AH1-5GT150-18-A-H-d6.35): This is the pulley I had selected previously. I changed it to [CBYL-AH1-5GT150-20-A-N-d12](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12) to ensure that I can extend the short motor shaft.

* [Idler CBYL-AH1-5GT150-18-A-H-d16 (Z)](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d16&productModelNumber=CBYL-AH1-5GT150-18-A-H-d16): I have not changed this.

* [Belt E-GBN26005GT-150 (Z)](https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN26005GT-150): The length is just an estimate, but the belt itself is finalised so far and compatible with the system.

After that, I realised that there was something wrong with the motor shaft couplings. Thy were overlapping with both the pulley and motor shaft geometry. So, I first fixed that by face offsets and extrusions. I made it compatible with the N-type hole of [CBYL-AH1-5GT150-20-A-N-d12](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12), making it look like this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/aadc0fc7-3f9d-492e-887d-75954a79576d" />

After having fixed the Tensioning System X, I mirrored the component to create the Tensioning System Y that is updated.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/faa72841-2548-4188-9ec2-a290a7c6eee3" />

Next I dived into modelling the pulley and idler case, for which I first went through the sketch and edited some parts. I found out that I had to raise the Tensioning System Z a little up to ensure that I can use similar sized case for the pulley and idler as the other tensioning systems. I then also added the [NEMA23 PR57HS76](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft) and placed it correctly.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d918ab38-b825-4a4b-9525-4abf49ddd6fb" />

But then I saw that the return belt of the Z axis was completely overlapping with the 2020 extrusion, so I moved it a little up and placed it between the belt of the z axis.

I can now confirm that the tensioning system was completed more than just the bare bones.

Thus, next I moved to making the case for pulley and idler, starting with a solid block, and then making it hollow from the sketch. Then I used split it divide it in two parts, for assembly.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e957f3c6-3d3f-46b4-a132-743e3393771a" />

I repeated this step for the idler as well using the mirror tool, and then arranged the components in the browser.

Next step was to add GT5 belt lock so that the system can drive the Z axis. I searched first in TraceParts, then in Printables, then MISUMI, then JLCMC, but didn't find exactly what I was looking for. After a while I found [this](https://grabcad.com/library/gt5-belt-lock-1) in GrabCAD.

I thought that it was okay, and I imported it in Fusion only to realise that it too small for the GT5 belt profile (as if shrunk), and that time was over for today's session.

**Total time spent: 3h 55m**

---

# Day 21 — 22.05.2026: Kinematic Base Module (KBM) Progress — Part 11

This session was all about adding the final touches to the tensioning systems to ensure that they function properly. I did a lot of stuff today. The first 20 minutes I was going through my BOM, checking compatability of components. Then I started [this](https://lapse.hackclub.com/timelapse/LMIzn1To8zm3) lapse and after it ended, I fixed some overlapping components.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4b605071-5c56-4343-b12e-89baed85f349" />

The First stage is almost complete after all this.

**Total time spent: 5h 52m**

---

# Day 22 — 23.05.2026: TriTeron Robot Module (TRM) Progress — Part 1

[Lapse 1](https://lapse.hackclub.com/timelapse/DfNLfUEVeITT)
[Lapse 2](https://lapse.hackclub.com/timelapse/8V5IIaFo7r2J)

**Total time spent: 3h 50m**

---

# Day 23 — 24.05.2026: TriTeron Robot Module (TRM) Progress — Part 2

I picked up exatcly where I left off yesterday. As the leg was complete, it was now time to implement that into the assembly.

There are going to be 4 legs in total, each with two connected legs.

* There will be one X axis leg consisting one upper and lower leg
* There will be one Y axis leg consisting one upper and lower leg
* There will be two Z axis legs consisting one upper and lower leg, each

[Lapse](https://lapse.hackclub.com/timelapse/vCOvL9YC8t7R)

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/710049cc-3663-446c-ba62-2b513a17f71d" />

**Total time spent: 2h 30m**

---

# Day 24 — 26.05.2026: TriTeron Robot Module (TRM) Progress — Part 3

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/33c1c2a2-e56b-4d25-aaaf-d6e44f021965" />

**Total time spent: 1h 30m**

---

# Day 25 — 27.05.2026: TriTeron Robot Module (TRM) Progress — Part 4

[lapse 1](https://lapse.hackclub.com/timelapse/XQaZ_Rl9L285)
[lapse 2](https://lapse.hackclub.com/timelapse/zi7MiJX0X9Cf)

**Total time spent: 3h 20m**

---

# Day 26 — 28.05.2026: TriTeron Robot Module (TRM) Progress — Part 5

[lapse](https://lapse.hackclub.com/timelapse/oC5sY39XrQ18)

**Total time spent: 1h 45m**

---

# Day 27 — 30.05.2026: TriTeron Robot Module (TRM) Progress — Part 6

[lapse](https://lapse.hackclub.com/timelapse/srgx05NYIPdJ)

**Total time spent: 1h 05m**

---

# Day 28 — 31.05.2026: TriTeron Robot Module (TRM) Progress — Part 7

[lapse](https://lapse.hackclub.com/timelapse/AqGtmyhMh9QV)

**Total time spent: 0h 17m**

---

# Day 29 — 01.06.2026: TriTeron Robot Module (TRM) Progress — Part 8

[lapse](https://lapse.hackclub.com/timelapse/ltNZ51iqS6UI)

**Total time spent: 1h 50m**

---

# Day 30 — 02.06.2026: TriTeron Robot Module (TRM) Progress — Part 9

[lapse](https://lapse.hackclub.com/timelapse/_aOokRs_SLGK)

**Total time spent: 1h 02m**

---

# Day 31 — 03.06.2026: TriTeron Robot Module (TRM) Progress — Part 10

[lapse](https://lapse.hackclub.com/timelapse/cPrT8Rbqh_sX)

**Total time spent: 4h 20m**

---

# Day 32 — 04.06.2026: TriTeron Robot Module (TRM) Progress — Part 11

Today, before I sat down to work on my project, I updated Fusion. After updating when I opened my file I saw that some of yesterday's progress was gone. I was quite astonished at the scene but had nothing to do.

Based on the experience of the previous day, I decided to go with the screw assembly. But here's what I did before the assembly:

1. I first went to Fusion Teams on Chrome and then I deleted old files that were not necessary in the design. It makes sure that all my stuff are updated and old unnecessary designs are excluded.

2. Then I went to model the washer again, just like yesterday. I first made a sketch and then I extruded it with the correct dimensions, which I received from the [OnlyScrews data sheet](https://onlyscrews.in/products/m8-washer-ss304). I then duplicaed it to total 28 screws using rectangular pattern.

3. Next imported the [EDLP-S1-B-d8-L30 screw](https://jlcmc.com/product/s/E02/EDLP/iso-7379-gb-t-5281-hex-socket-shoulder-screw-(set-screw)?k=EDLP-S1-B-d8-L35&productModelNumber=EDLP-S1-B-d8-L35) which I had downloaded yesterday. I then duplicaed it to total 12 screws using rectangular pattern.

4. Then I looked for the nut for the screw. I chose this [EMLC-S1-N-M8](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M8&productModelNumber=EMLC-S1-N-M8) from yesterday and duplicated it to total 12 screws using rectangular pattern.

Then I was about to enter into assembling.

1. I first added a rigid joint for the washer.
2. Then I added the screw.
3. And then I added the second washer.
4. Next I added rigid joint for the nut.

This is how it looked.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0dcea9fe-db0c-4654-aa25-50b81b9fa382" />

5. Using the combine tool, I made a hole so that the nut can fit in the z-axis mount.
6. Made some extrusions using sketch and added clearence for installing the nut.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/dc5c7303-ead8-401c-8cd4-355c339bbd26" />

But looking at the assembly, it seemed that the scews are not that sturdy, as not all faces that asre supposed to be tight are making contact. The length of the thread and the extent of it is also concerning. But why was that so. It was because of the following reasons:

* There was a huge gap between the screw head and the smooth shoulder.
* The shoulder neck was narrow, which could've caused the washer to loosened.
* The thread length was shorter than the thread length of the nut.
* There was a concerning amount of gap and narrowing at the threaded neck

So I made the desicion of chaning the very shoulder screw for which I spent so long to assemble. I got no choice.

I started surfing JLCMC and after looking at several configurations of screws, I could not find something desirable for the assembly.

But then I found this [MSB8-30](https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30) screw that seemed perfect for the assembly, since it had no narrow points and a decent thread length. I briefly went through the data sheet.

<img width="900" height="1271" alt="image" src="https://github.com/user-attachments/assets/4344263f-def7-4784-a7aa-cfeb2aa381a7" />

But there was one problem. The the length of the smooth shoulder was exactly 30 mm, which mean that the washer to waher max distance was also supposed to be 30 mm, for a perfect fit. The washer is 1.5 mm thick and the 608 bearing is 7 mm thick. But currently, this was 1.5 + 7 + x + 7 + 1.5 = 32 mm, where X is the TriTrron leg's gap between the bearings, which was 15 mm. This meant that I had to reduce the X from both sides by 1 mm, to make the total 30 mm.

Thus, I made the adjustments to all the 24 bearing hubs in the legs, using extrusions and facial offsets. Then I deleted the old rigid joints of the bearings and reassembled them correctly.

This made sure that there is 27 mm of gap between the washers, and since the washers were 1.5 mm thick, the distance between the extreme faces of the wo washers is 30 mm.

This is how it looks now.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0470ebae-430b-425c-98ed-8ca5e5f1259c" />

The problem was fixed, and the screw was supposed to be a perfect fit.

I added rigid joint for the first washer (after struggling to delete the pre-existing joint), and then for the second, and then the nut.

Yes, it was a perfect fit, but before I could proceed, time was over for today's session.

Here's the lapse of today's session: [PATRA-LPS-11-D32](https://lapse.hackclub.com/timelapse/0scjCOx6vKE7)

**Total time spent: 3h 30m**

---
