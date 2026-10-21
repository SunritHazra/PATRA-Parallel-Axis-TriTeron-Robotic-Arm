---

Title: Parallel Axis TriTeron Robotic Arm (PATRA)
Author: Sunrit Hazra
Description: An open-source nine-degrees-of-freedom hybrid robot architecture of a kinematically linear three-degrees-of-freedom triple-axis manipulator system and a six-degrees-of-freedom serial robotic arm.
Created on: 02-05-2026
Started on: 10-04-2026
Kinematic Base Module (KBM) Progress: "95%"
TriTeron Robot Module (TRM) Progress: "62%"
Robotic Arm Module (RAM) Progress: "1%"
Electronic Components Progress: "10%"
Overall Progress: "42%"
PC (Laptop) Used: "ASUS Vivobook 15 X540UAR"
Potential Sponsors: "Hack Club Forge, JLCPCB/EasyEDA, Emergent Ventures"
Helped by: "Dan Rudmin (Zaber Technologies Inc., Canada), Rowan Hunt (Not An Engineer, Australia), Zisheng Li (Anvol, USA)"

---

# Day 0: Flashback

On a random day in December of 2025, I was scrolling through my YouTube feed when I came across [this](https://www.youtube.com/shorts/74T0LF2l5Ck) video with a TriTeron Robot concept. The mechanics were immediately impressive: a clean parallel axis system with a movement profile I hadn't seen in a hobbyist build before. The logical extension was obvious: mount a robotic arm on the head, and you get something that combines the workspace coverage of a gantry with the dexterity of a serial arm, which is really cool.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ff8585a7-c18c-4249-9e0b-f1dbca4265bf" />

**Total time spent: 0h 1m**

---

# Day 1 — 10.04.2026: Planning & Studying

Ever since I was a member of Hack Club, I wanted to make a TriTeron robot. Originally, I thought of doing this project in **Blueprint** as two separate modular projects: **TriTeron Robot** for $400 and **Robotic Arm** for $400. But Blueprint ended even before I could start. So, I chose Fallout. I didn't start there either, partly due to running Construct and Stasis in parallel, and partly because the scope wasn't clearly defined enough.

This is the Tipteron Robot built by Dan Rudmin from Zaber Technologies:

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1e31c116-bfa6-4f96-a2c2-00662f581cc6" />

The right opportunity came with Forge. The Tier 1 has an unlimited budget, but I capped the budget at $700, which is was tight but workable.

Here's what shaped my thinking and inspired me:

* [This](https://www.youtube.com/shorts/74T0LF2l5Ck) is the video that first sparked my interest.

* [This](https://www.youtube.com/watch?v=6EtXycVGJg4) video by Rudmin introduced the original concept.

* [This](https://www.youtube.com/watch?v=io4S9amExNM) video by [Not An Engineer](https://www.youtube.com/@NoEngineerHere) introduces the carriage system. I watched this multiple times specifically to understand how the X and Y axes are driven independently on the carriage.

* [This](https://www.youtube.com/watch?v=3fbmguBgVPA) pushed me toward adding a robotic arm and gave me a rough idea of what style of robotic arm I could add.

* [This](https://www.youtube.com/watch?v=MeRaYVntxMk) is a solid breakdown of the differences between serial and parallel systems. PATRA essentially combines both, which is why understanding this distinction matters.

To get started, I did focused research on the following (only this time is counted):

* **Kinematics:** Beyond just the general definition, I read articles and watched detailed videos specifically on parallel axis kinematics and kinematically linear systems. I also explicitly read [this](https://en.wikipedia.org/wiki/Kinematics) Wikipedia page and watched [this](https://www.youtube.com/watch?v=3fbmguBgVPA).

* **Robotic Arms:** I did a deep dive into 5 DOF and 6 DOF robotic arms, studying their structure, joint arrangements, and torque requirements. I also carefully studied the Meca500 robotic arm as a size and precision reference.

* **Linear Belts:** Although I was already familiar with them, I studied motor selection, torque transmission, belt pitch types, and tensioning systems in more detail.

* **Ball Screws:** This was a completely new concept for me. I learned that ball screws offer higher precision and better load handling compared to belts, but at the cost of speed and higher complexity.

* **Aluminium Extrusions:** I knew nothing beyond 2020 and 4040 aluminium extrusion. So, for the sake of this project, I made a deep dive into JLCMC's Aluminium Extrusion Profiles, and I read their [datasheets](https://drive.google.com/file/d/1X2043j8HutSmY2QTKigUobWLhu9sI9k2/view?usp=sharing).

* **Zaber LC40:** Rudmin used the [LC40 family](https://www.zaber.com/products/families/LC40) for the TriTeron, which is configurable, belt-drive, T-slot profile linear stages. Prices were mostly in the $2000–$3000 range, which is consistent with industrial-grade configurable stages.

I learned the foundational concepts needed to make this project. Here's what I could faintly comprehend after I completed day 1:

* How ball screws work internally (recirculating ball mechanism and lead mechanics)
* Differences between NEMA motor sizes and torque ratings
* Trade-offs between belt drives and screw drives
* The structure of linear actuators
* The mechanical difference between serial and parallel robotic systems
* Why rigidity and repeatability matter more than just "cool movement"
* How can I make my robotic arm modular
* A little about the LC40 family

**Summary of today's session (Day 1):**

1. Revisited the origins of the TriTeron concept and reviewed key reference projects and videos.
2. Selected Forge as the platform for developing PATRA after earlier plans did not materialize.
3. Conducted focused research on kinematics, robotic arms, belts, ball screws, and aluminium extrusions.
4. Studied industrial systems such as the Zaber LC40 family to understand professional design approaches.
5. Built a stronger technical foundation by learning about drive systems, torque requirements, modularity, and parallel robotics.

**Total time spent: 6h 00m**

---

# Day 2 — 11.04.2026: The First Pitch

Time for the first pitch. I had a rough plan for the architecture in mind.

There will be a base made using ball screws, and the tripteron will have a carriage system, where I will attach motors to the moving platform.

So I sketched it out on paper, and then spent several hours researching parts on different sites like JLCMC. I also used AI for searching, primarily as a search tool, to find parts on sites I wouldn't have otherwise located. From that, I assembled a rough BOM with an initial target of $500 for the TriTeron and $500 for the 6 DOF arm. Total, making the budget reach $1000, not $700, as I got a reality check on the prices.

The honest problem at this stage was that without any CAD done, the plan was still too abstract. I drew seven different versions of the thing before settling on what to pitch, which tells how much I was still working it out. Still, the goal was to get external feedback early rather than spend weeks refining a plan in isolation. There was also a possibility that the pitch would get rejected, so I wasn't able to convince myself to commit many hours.

After writing the draft and building the BOM manually, I pitched in the #forgery channel in Hack Club Slack

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/afd7d77b-3889-44e8-b776-08f510aa0ad4" />

The most frustrating part of this phase was the overwhelming number of choices. Linear guides alone had dozens of variants across multiple vendors, with no clear basis for choosing one over another without more context. That changed gradually as I got deeper into datasheets. I read a lot of datasheets, as I knew almost nothing about linear guides and how they worked.

I honestly did not understand most of the things I am working on. I spent a lot of time studying new things about linear robotics

**Summary of today's session (Day 2):**

1. Developed the first formal pitch for PATRA based on preliminary planning and research.
2. Created multiple design sketches and evaluated different architectural possibilities.
3. Assembled an initial bill of materials with separate budgets for the TriTeron and robotic arm.
4. Performed extensive component sourcing and feasibility analysis.
5. Submitted the project for external review to gather technical feedback and validation.

**Total time spent: 5h 00m**

---

# Day 3 — 12.04.2026: Starting to Model

I started today's session by rewatching [Rowan's video](https://www.youtube.com/watch?v=io4S9amExNM&t=1s) from start to finish, this time specifically tracing the carriage assembly; how it moves, how the X and Y axis legs are attached, and where the belts actually run. He has a Patreon with the Fusion file, which I downloaded and used as a structural reference. Not copied wholesale, just as a baseline to understand what I'd be modifying and to use it as an inspiration.

I then created the project in Fusion and imported the relevant reference geometry.

The plan at this point: follow Rowan's carriage approach (independently driven X and Y axes), but substitute a ball screw for the main axis, on a 1 metre rail.

I started with the 4040 T-slot aluminium extrusions. I re-read the [datasheets](https://drive.google.com/file/d/1X2043j8HutSmY2QTKigUobWLhu9sI9k2/view?usp=sharing) and downloaded the STEP files for [TXCL-H7-4040E-L1000](https://jlcmc.com/product/s/T01/TXCL/extruded-aluminum-t-slot-40-series(eu)-8mm-slot-width?k=TXCL-H7-4040E-L1000&productModelNumber=TXCL-H7-4040E-L%5B50~6000%2F0.1%5D) from JLCMC costing $8.99 each. Added two to cart.

Then the Ball Screw. After reading the datasheet, I settled on BSUF-C7-20-5-L640-F30-P12, added it to the cart, and downloaded the STEP file.

Same process for the linear guides: chose E-BMN15H-2-L1000-ZF-C-E20, added two of them to the cart, and downloaded.

As a sizing reference, I downloaded the [Meca500 CAD model](https://www.3dfindit.com/en/digitaltwin/meca500-assembled?path=mecademic%2Findustrial20robotic20arms%2Fmeca50020six axis20robot20arm%2Fmeca50020assembled.prj&mident=%7Bmecademic%2Findustrial20robotic20arms%2Fmeca50020six axis20robot20arm%2Fmeca50020assembled.prj%7D%2C013+%7BLINEID%3D10%7D++%7BNB%3DMeca500+Assembly+simple%7D%2C%7BORDERNO%3DMeca500+Assembly+simple%7D%2C%7BMOUNTING%3Dany+orientation%7D%2C%7BPAYLOAD%3D0.5+kg+rated+%28max.+1+kg%29%7D%2C%7BREACH%3D260+mm+%28see+diagram+below%29%7D%2C%7BWEIGHT%3D4.5+kg%7D%2C%7BNAME%3DMeca500+Assembly+simple%7D%2C%7BSOURCEURL%3Dhttps%3A%2F%2Fwww.mecademic.com%2Fen%2Fdownloads%7D) from 3Dfindit, and skimmed the [official documentation](https://resources.mecademic.com/en/doc/MC-OM-MECA500/11.1/mc-om-meca500.pdf). This wasn't for replication — it was just useful to have accurate geometry in the assembly to check proportions.

After roughly half an hour of assembly, this was the result:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ae1e4371-f2ac-4b45-ac44-78ecef0699c0" />

Then came the cost check. Shipping from JLCMC alone was over $200 even on the cheapest option, before customs. At 35–50% customs on top, this approach was clearly unworkable for the budget. Deleted the cart, noted the lesson: source locally wherever possible.

Dropping the 1 metre rail brought its own constraints. With 500 mm usable travel, the TriTeron needed to be scaled up to preserve the arm's proportions — and that scaling introduced two problems. First, the robot looked disproportionate. Second, the available travel was now borderline inadequate for the scaled frame.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/19ec1236-b435-48a9-bfb8-c7fb5c37ef8a" />

I spent another three hours iterating, trying smaller JLCMC variants, adjusting the usable length to keep costs down:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/51f2d2e0-dca3-43d2-9c9e-54db52e20baf" />

The proportions weren't working. I took a step back and reconsidered the carriage architecture itself. Instead of following Rowan's design where the motors are remote and belt-driven to the carriage, I tried making the carriage self-contained with motors mounted directly on it, freeing up the rail geometry. This meant extending the carriage base using extrusions on the front face and rethinking the drive path.

After more hours of iteration:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/28d18e54-e5e2-471f-a430-8d8cc5a90f1b" />

For a rough picture of how I did the CAD throughout today, [here](https://drive.google.com/file/d/17hyzQvfrPkSDDIoYjY-ttWvvfYUGDrAG/view?usp=sharing) is a timelapse-like video, exploiting the Fusion Timeline. Fusion being parametric saved a lot of time here.

**Summary of today's session (Day 3):**

1. Began CAD development by studying Rowan's carriage-based TriTeron architecture.
2. Imported reference models and established the Fusion 360 project environment.
3. Planned a hybrid architecture combining carriage mechanisms with ball-screw actuation.
4. Started modelling the primary structural framework using aluminium extrusions.
5. Used existing designs as educational references while preparing for future modifications.

**Total time spent: 8h 10m**

---

# Day 4 — 13.04.2026: The CAD Failure Day

The plan today was to ignore the rail sourcing problem entirely and focus on adding motion using As-Built Joints on Rowan's tripteron, in order to understand the working mechanism better. The X and Y leg joints went in initially without issue, but the assembly quickly became inconsistent as components were referencing incorrect parent frames and the motion wasn't physically meaningful.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/492c4516-e10d-4c0a-946f-2e5b47b9d086" />

I dropped the joint work and instead scaled the TriTeron up by 1.5x to better fit the Meca500 at the original size. In doing so, I also noticed the two sides of the frame were asymmetric. I fixed that with a split body approach, deleting one side and mirroring.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/93acdf6c-3b9c-457f-8c5d-3f718d41657e" />

At this scale, the travel envelope was clearly insufficient. 600 mm started to look necessary, so I did a rough BOM check on paper to see how much that would push the cost — which took more time than expected.

I re-added the joints one leg at a time. This was faster than the first attempt, but the slider joint didn't resolve correctly. I traced the issue back to the scale step in the timeline, found the relevant operation, and scaled the slider to match, which introduced further downstream problems. After fixing those and completing the joint set, the motion was at least physically plausible for the first time.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/667bc22a-e696-4321-8b5e-c26f8a8732b1" />

From there, I made a sequence of smaller adjustments:

* Made the tool head larger so the Meca500 base seats correctly
* Went back and forth between 1.25x and 1.5x scaling, editing the timeline directly, trying to balance proportions against motion clearance
* Attempted to shorten the carriage slider to give the robot more room to move

But even after doing all of that, I met with disproportionate geometry and motion joints that had drifted out of the correct configuration again. The scaling changes had accumulated too many dependencies in the timeline. So the decision was to delete all joints, reset the motion setup, and re-examine the underlying plan before continuing.

This is how the thing looks from the right side:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/183ff45a-b18b-4c35-99e1-2a7a8030f256" />

This is how the thing looks from the left side:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3c7e5950-0ebe-4217-807d-f8d1e3b2d580" />

About the pitch, no pitch response yet. So I waited on that before making any major structural decisions on the build.

**Summary of today's session (Day 4):**

1. Experimented with Fusion 360 joints and assembly constraints for motion simulation.
2. Encountered challenges in achieving correct kinematic relationships between components.
3. Shifted focus toward refining the structural design rather than motion studies.
4. Rescaled the mechanism to better fit the intended robotic arm dimensions.
5. Improved frame symmetry by rebuilding and mirroring major structural elements.

**Total time spent: 5h 50m**

---

# Day 5 — 14.04.2026: Post-Pitch-Review CAD & Research

First [pitch response](https://hackclub.slack.com/archives/C0AQG3VPQDD/p1776140495172719?thread_ts=1775931663.812209&cid=C0AQG3VPQDD) came in. The reviewer didn't flag issues with the project concept itself, but pointed out a better driver and an alternative sourcing approach. Both were actually useful as the driver suggestion changed how I was thinking about the control architecture, and the sourcing direction helped clarify what was realistic within budget constraints of $1000.

That led me to reconsider the overall scale of the build:

* Use a 1 metre rail instead of 500 mm?
* Keep the robotic arm at original Meca500 size?
* Scale the TriTeron to 1.75x the original Rowan design?

These changes don't necessarily blow the budget as the question is whether the rail length and proportions can be made to work within the $1000 ceiling with Indian-sourced parts. I spent about an hour and a half testing different rail lengths and linear guide models in Fusion, importing actual STEP files to check fit rather than guessing.

I also did a rough manual torque calculation for the main axis, which came out to approximately 1.1 Nm. This estimate was not accurate but it seemed near-correct to me. 1.1 Nm of torque sits in the range where the best NEMA 17s are marginal and a mid-tier NEMA 23 is more appropriate. JLCMC had a wide selection, so most of the motor research was done there alongside their datasheets. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c2d27b79-ea12-4ee8-9492-0111a22336d0" />

I imported the 42CM08 motor model into Fusion to check spatial feasibility for my original plan, which was motors mounted directly on the carriage. The result was clear: two NEMA motors on the carriage make it significantly bulkier, and the placement geometry doesn't work cleanly. The approach that both Rudmin and Rowan use, mounting motors off the carriage and transmitting via belt, makes more sense mechanically. Testing with a 600 mm 4040 extrusion also confirmed that it's too short for the scaled design.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/927c9935-bbf2-4ddb-8740-0aa628d0fd2a" />

I started yet another BOM. This time separating Indian-sourced components from JLCMC components, and adding shipping and customs estimates to each. The conclusion was unambiguous: JLCMC isn't viable for this project given the import costs. Everything needs to come from Indian vendors.

Evidence from the JLCMC cart, three items only:

<img width="802" height="586" alt="image" src="https://github.com/user-attachments/assets/55236b4e-1783-4af0-b474-7656325379a4" />

Cheapest shipping already makes it unworkable, and that's before 35–50% customs:

<img width="252" height="393" alt="image" src="https://github.com/user-attachments/assets/9330b45f-b0b7-40d3-b304-788b8fe47754" />

I also did targeted research on the Indian market for the three main structural components:

* **Linear Guides:** HIWIN is available through MISUMI India and HIWIN India. [Robu.in](https://robu.in/product/mgn15h-linear-guide-rail-1m-2) also has a solid option.

<img width="1365" height="644" alt="image" src="https://github.com/user-attachments/assets/e1b173d1-539e-4f4c-ae64-032af907a4cf" />

* **Ball Screw:** Pricing was high across all platforms. Best candidates were Novo3D and MISUMI India, with [JLCMC](https://jlcmc.com/product/s/B04/BSAF-C7-15/rolled-ball-screw-with-sfar-nut-shaft-diameter-15mm-lead-5-10-16-20mm) and [Robu.in](https://robu.in/?s=ball+screw&post_type=product&dgwt_wcas=1) as reference points for price comparison.

<img width="1365" height="643" alt="image" src="https://github.com/user-attachments/assets/94d822a2-227d-4ba3-9b91-b816021f0f6d" />

* **4040 Extrusions:** [Robokits](https://robokits.co.in/mechanical-parts/aluminium-profile-accessories/astro-anodized-heavy-duty-industrial-grade-aluminium-4040-t-slot-profile?srsltid=AfmBOoqKFxp7iACSQkkYpdlSToUPKQh1cB2N3_JJ_hqWzN5CCDY8bWU9) is the cheapest option available, though I still need to verify their dimensional drawings against the datasheet before committing.

<img width="1365" height="575" alt="image" src="https://github.com/user-attachments/assets/2846e072-1fa1-45e1-99d3-64ca3d49b956" />

The BOM from today was used directly as the basis for the re-pitch on 30th April.

**Summary of today's session (Day 5):**

1. Reviewed project feedback and reassessed several major design decisions.
2. Calculated motor torque requirements for the intended payload and motion system.
3. Evaluated different motor placement strategies and selected remote mounting.
4. Compared sourcing options from domestic and international suppliers.
5. Optimized the design around realistic budget and procurement constraints.
   
**Total time spent: 4h 55m**

---

# Day 6 — 30.04.2026: The Final Pitch

I [re-pitched](https://hackclub.slack.com/archives/C0AQG3VPQDD/p1777518863427759?thread_ts=1775931663.812209&cid=C0AQG3VPQDD) PATRA in the Forge channel. 

The project description stayed mostly the same; the significant change was the BOM. Having my budget capped at $700, which was before, $1000, I used Excel to list all the things and then refined the whole thing multiple times using GPT-5. Rail length was fixed at 600 mm usable travel. About 40 minutes of additional research went into tightening the component list and price estimates.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d54c1631-461d-43ca-88dc-c4519b394e03" />

Here's the BOM:

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
The same Indian rail listing provides blocks.

Belt Drive (Light Axes)
GT2 / HTD 5M Belt (15 mm width, 3 m) – ≈ $25 USD
HTD belt example (Indian marketplace or Amazon):
[Link](https://www.amazon.in/Timing-Belt-Gear-Pulley-Printer/dp/B07W4J5PGF)
HTD 20T Aluminum Pulleys (4 pcs) – ≈ $20 USD
Example pulleys:
[Link](https://www.amazon.in/Timing-Pulley-Bore-6mm/dp/B08CXZ7VMH)

Frame + Structure
4080 + 4040 Aluminum Extrusion (cut locally) – ≈ $170 USD (combined)
Sources for Indian extrusion retailers with custom lengths:
Search on Indian marketplaces like India Mart for:
"2040 T-slot aluminum extrusion all lengths"
"4040 T-slot aluminum extrusion custom cut"
Example extrusion supplier:
[Link](https://www.indiamart.com/proddetail/aluminium-t-slot-extrusion-6762050720.html)
Aluminum Plate ~10–12 mm (Custom CNC cut) – ≈ $70 USD
A local metal supplier or shop near you can cut to size.

Motors
NEMA 23 Stepper Motor (2 pcs) – ≈ $80 USD
Example NEMA23 listings in India:
[Link](https://robomart.com/product/stepper-motor-nema23-10kgcm-torque-with-pulley)
NEMA 17 Stepper Motor (3 pcs) – ≈ $60 USD
Example affordable NEMA17 bundles:
[Link](https://www.amazon.in/Stepper-Motor-17HS19-1684S/dp/B07Q5QDLFK)

Drivers & Power
TB6600 Stepper Drivers (2 pcs) – ≈ $30 USD
TB6600 driver example:
[Link](https://www.amazon.in/2 axis-Stepper-Motor-Driver/dp/B01MTOYCRA)
TMC2209 Drivers (3 pcs) – ≈ $30 USD
TMC2209 driver example (widely in Indian hobby stores):
[Link](https://dc3d.in/shop/voron-v2-4-parts/bigtreetech-tmc2209-v1-3-stepper-motor-driver)
24V 10A Power Supply – ≈ $30 USD
Example PSU (India):
[Link](https://www.amazon.in/Antratek-Switched-Mode-Power-Supply/dp/B08BWGRYT4)

Controller / I/O
Controller Board (STM32 / GRBL / 32-bit board) – ≈ $30 USD
Affordable motion control board:
[Link](https://www.amazon.in/NCStudio-Controller-Mach3-USB-Port/dp/B08CHY7CC8)
Limit Switch Set – ≈ $10 USD
Mechanical limit switches:
[Link](https://www.amazon.in/20-Pack-Micro-Limit-Switch/dp/B08VRWCC5C)

Miscellaneous
Flexible Shaft Couplers (Pack) – ≈ $15 USD
Example flexible coupler:
[Link](https://www.amazon.in/Flexible-Coupling-Shaft-Connector-12mm/dp/B07D3DB5NJ)
Fasteners, Bearings, Wiring, Cable Ties, Misc Hardware – ≈ $40 USD
Local hardware store — widely available

Estimated Total
≈ $700 USD

>	[!Important note]
>	The sources listed below are indicative, not finalized, as they establish a price baseline using mean market values. The actual sourcing will be determined after approval. Many are very cheap, but the estimated cost is set high.

**Summary of today's session (Day 6):**

1. Investigated CNC manufacturing options for custom robot components.
2. Requested and compared quotations from multiple fabrication services.
3. Analyzed manufacturing costs against overall project budget limitations.
4. Evaluated the practicality of CNC machining versus additive manufacturing.
5. Decided to prioritize 3D printing for most custom structural components.

**Total time spent: 3h 55m**

---

# Day 7 — 01.05.2026: The Research for Sanity

Yesterday I pitched the project again. The BOM was assembled from placeholder sources to establish price ranges. Today the goal was to actually commit to real components, working from the structural base upward.

Going back to first principles, I re-watched the [original TriTeron video](https://www.youtube.com/shorts/74T0LF2l5Ck) by Rudmin to re-anchor the architecture.

But there is something I should have been completely honest about: the reason I had switched to [Rowan's carriage approach](https://www.youtube.com/watch?v=io4S9amExNM&t=1s) in the first place was that I hadn't correctly understood [Rudmin's drive system](https://www.youtube.com/watch?v=6EtXycVGJg4). Specifically, I missed that there are two independent outputs on a single rail. Which meant that I never noticed or understood how one belt controlled two linear blocks independently. I also didn't notice the third belt, which was in between.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/43b30add-53ae-4e89-a968-f8cbf16d96b9" />

Looking at it again: the front two Z axis legs are controlled by a belt running through the centre. There are three belts total, and once I spotted the middle one, the whole system clicked. The two outputs on a single rail aren't separated by physical distance; instead, they're driven by independent belt loops running in the same channel.

With that understood, the simpler Rudmin architecture is clearly preferable. The changes this implies:

* Ball screws for the main rail, as originally planned.
* Carriage eliminated entirely.
* 1 metre aluminium extrusions, targeting approximately 900–950 mm usable travel.

The main benefit here is cost reduction: fewer custom parts, simpler assembly, and less material overall.

I rebuilt the BOM from scratch with Indian sources:

* [4040 T-slot aluminium extrusions](https://robokits.co.in/mechanical-parts/aluminium-profile-accessories/astro-anodized-heavy-duty-industrial-grade-aluminium-4040-t-slot-profile) — Robokits.
* [MGN15H Rail](https://robu.in/product/sliding-block-for-mgn15h-linear-guide-rail) — Robu.in.
* [MGN15H Sliding Block](https://robu.in/product/sliding-block-for-mgn15h-linear-guide-rail) — Robu.in.
* [SFU1610 Ball Screw 1000mm](https://novo3d.in/ball-screw-sfu1610/) — Novo3D, with supports.
* [TB6600 Stepper Motor Driver](https://robu.in/product/tb6600-stepper-motor-driver-controller-4a-942v-ttl-16-micro-step-cnc-1 axis-upgraded-version-425786-stepper-motor?gclid=CjwKCAjwntHPBhAaEiwA_Xp6RtwUATtWsr6ENAJnefCDD7A_hFCG6G0U4FvI7KcqhoYZApcELbKBxhoCF8cQAvD_BwE&gad_source=1&gbraid=0AAAAADvLFWeX0A7E-QWDpuYY72tUYPPuB&gad_campaignid=20381096599) — Robu.in.
* [NEMA23 PR57HS51](https://robu.in/product/nema23-pr57hs51-2804-10-1kg-cm-stepper-motor-round-type-shaft) — Robu.in.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1db26124-16e5-458f-995f-0c8feac88678" />

The BOM hit $288 before accounting for the arm, fasteners, or electronics. With that rate of growth, staying under $700 total isn't feasible if ball screws stay in. The precision advantage of ball screws over belts is real, but it's not justified for this use case — the arm payload is modest, and positioning repeatability isn't the limiting factor at this stage.

Decision: drop ball screws, switch to belts.

For belt selection, I went through the JLCMC [timing belt datasheets](https://jlcmc.com/product/s/C02/CDTM/timing-belts-2gt) and checked a few options. The arm adds meaningful mass to the head, and under load a GT2 belt will stretch and lose accuracy. HTD 5M (5 mm pitch, 15 or 20 mm width) gives better load capacity and is more appropriate for this application.

Removing ball screws from the BOM brought the running total down to approximately $160.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f2467ea2-3b5d-42df-a6ee-9e2d4bbf6254" />

One sourcing gap: HTD 5M belts don't appear to be stocked by any Indian e-commerce site I found. IndiaMart has listings, but they require direct vendor contact. Will need to follow up on that.

**Summary of today's session (Day 7):**

1. Revisited the original TriTeron mechanism to improve understanding of its operation.
2. Discovered how multiple belt loops independently drive different axes.
3. Corrected earlier misconceptions regarding carriage-based motion systems.
4. Simplified the architecture by moving away from unnecessarily complex mechanisms.
5. Updated the bill of materials based on the revised design approach.

**Total time spent: 4h 55m**

---

# Day 8 — 02.05.2026: The Post-Pitch-Approval Research

Today the pitch was finally approved. Now I am finally sure that I can continue working on this project. Thanks a lot, to Souptik Samantha for the pitch approval! I decided to adopt a strategy this time, not random guesses.

I made the following finalised decisions:

* I will make the usable rail length 900 to 950 mm.
* I am absolutely eradicating ball screws from my project, for linear belts.
* I will keep the arm size at the size of Meca500.

I now finally had everything necessary to start modelling my PATRA again, with a clear goal in my mind. But looking at my BOM, and clicking those links, I saw that not a single source I have selected has a 3D model attached with them. That changed the direction of the entire day. Up until this point, sourcing was a cost problem. Now it became a CAD problem. Every link I had carefully collected — Robu, Robokits, Novo3D, Amazon listings — had images, basic specs, sometimes even dimensional drawings. But no STEP files.

And this matters more than it sounds.

So, why didn't I use the part name and download the model from somewhere else? It is because every time I visit a site, even though the thing is the same, I see in the drawings that they are a little different and inconsistent, which is unprofessional and intolerable because I don't want to risk the assembly by ordering the wrong parts. Even pulley hub thickness varies between sellers.

But the Indian hobby market behaves differently than industrial suppliers: Most sites sell parts. Very few provide CAD. Even fewer provide verified manufacturer datasheets. Many are resellers of unnamed OEM parts.

So I was stuck between two worlds:

Industrial-grade suppliers  
→ Reliable: OK, fine  
→ CAD models: Yes!  
→ Datasheets: Awesome!  
→ Expensive: Not fine  

Hobby-market suppliers  
→ Affordable: Only this matters  
→ Available locally: Important!  
→ No CAD: Why?  
→ Ambiguous tolerances: Very unprofessional  

So, this is what I did: I started from the very foundation and worked my way up till I completed the Kinematic Base Module (KBM). Instead of abandoning the plan, I tried systematic verification.

1. **4040 Aluminium Extrusion** from Robokits 4040 T-Slot (Astro Industrial grade): I checked slot width (8 mm vs 10 mm variants), core wall thickness, center bore diameter, and outer corner radius. There is only a 2D drawing image provided. No tolerance specifications. No downloadable 3D model. So, I chose [this](https://www.3dprintronics.com/products/t-slot-aluminium-extrusion-4040-8mm?srsltid=AfmBOorlrQFAR1Xrt53eLpePYovKiCMCeYb2kc3UqxQDkFEoahj_P2o4YdA) from 3DPrintronics, instead.

2. **MGN15H Rail & Block** — Candidate: Robu MGN15H Sliding Block. I checked rail height (H dimension), block width (W), mounting hole pitch (C dimension), and mounting hole diameter. Only basic specifications are listed. No full dimensional drawing is available. The official HIWIN datasheet shows precise tolerances and preload classes, but Indian sellers do not specify the actual manufacturer. “MGN15H” is a size class, not a brand guarantee. So, I trusted Robu and decided to use a model from JLCMC.

3. **NEMA23 PR57HS51** — Candidate: Robu NEMA23 PR57HS51. Torque is approximately 1.0–1.2 Nm. Body length varies by torque variant. I compared body length, shaft diameter, shaft length, and mounting face standard (47.14 mm square pattern). The mounting pattern is standardized. The body length is not. So, I am also trusting this.

Okay, now this is the BOM for the Foundation Structure, for now:

<img width="2340" height="132" alt="image" src="https://github.com/user-attachments/assets/52d7d490-c39b-4479-955c-b229921b5a04" />

I will continue with this for the next day and start modelling again.

**Summary of today's session (Day 8):**

1. Received approval to continue development and refine the project further.
2. Finalized important design parameters such as rail dimensions and workspace.
3. Permanently removed ball screws from the system architecture.
4. Investigated CAD model availability for selected commercial components.
5. Began rebuilding the project around verified and practical hardware selections.

**Total time spent: 3h 55m**

---

# Day 9 — 03.05.2026: Modelling Based on New Plan

Today I started modelling PATRA again from scratch based on the components that were finalised for the first stage yesterday. I wanted to start fresh. I had my parts listed, so I simply went for the 3d models one by one.

1. **[4040 Aluminium Extrusion](https://www.3dprintronics.com/products/t-slot-aluminium-extrusion-4040-8mm?srsltid=AfmBOorlrQFAR1Xrt53eLpePYovKiCMCeYb2kc3UqxQDkFEoahj_P2o4YdA) from 3DPrintonics:** For the model, I went to JLCMC and chose [TXCL-H7-4040E-L1000](https://jlcmc.com/product/s/T01/TXCL/extruded-aluminum-t-slot-40-series(eu)-8mm-slot-width?k=TXCL-H7-4040E-L1000&productModelNumber=TXCL-H7-4040E-L%5B50~6000%2F0.1%5D), and made sure that the exterior of the profiles match, wven thought the interior dosen't.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e7cef8d2-06e1-49ae-8467-1d2626996399" />

2. **[2020 Aluminium Extrusion](https://robu.in/product/easymech-20x20-t-slot-aluminium-extrusion-profile-1000-mm) from Robu:** For the model, I again went to JLCMC and I chose [TXCJ-H7-2020-L1000](https://jlcmc.com/product/s/T01/TXCJ/extruded-aluminum-t-slot-20-series(eu)?k=TXCJ-H7-2020-L1000&productModelNumber=TXCJ-H7-2020-L%5B50~6000%2F0.1%5D) for the model.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f1a07dde-2669-431b-9970-775c29f5b4a0" />

3. **[Linear Rail](https://robu.in/product/mgn15h-linear-guide-rail-1m-2) from Robu:** I sourced the model from JLCMC. I used [E-BMN15H-2-L1000-ZF-C-E20](https://jlcmc.com/product/s/B03/E-BMN/economical-linear-guide-mini-standard-type-7-9-12-15?k=E-BMN15H-2-L1000-ZF-C-E20&productModelNumber=E-BMN15H-2-L%5B70~1800%2F1%5D-ZF-C-E%5B0~39%2F0.5%5D) for reference.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6bf120ce-1bd0-4ff0-b6dc-b1268900974d" />

5. **[Linear Guides](https://robu.in/product/sliding-block-for-mgn15h-linear-guide-rail) from Robu:** I sourced the model from JLCMC. I used [E-BMN15H-2-L1000-ZF-C-E20](https://jlcmc.com/product/s/B03/E-BMN/economical-linear-guide-mini-standard-type-7-9-12-15?k=E-BMN15H-2-L1000-ZF-C-E20&productModelNumber=E-BMN15H-2-L%5B70~1800%2F1%5D-ZF-C-E%5B0~39%2F0.5%5D) for reference.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/edb5886a-23ee-43a3-bb78-ea120d2b0e70" />

Then I went back to researching motors I could potentially use, and I tried to gather estimates of my producable torque from PATRA.

Here is what I found:

Moving mass per axis	~5 kg
Static torque requirement	~0.49 N·m
Dynamic/stiff torque requirement	~1.5–1.8 N·m
Your old motor running torque	~0.7–0.8 N·m
Recommended motor torque	≥ 1.5–2.0 N·m
Good motor choice	~18.9 kg·cm (~1.85 N·m)
Great motor choice	~30.6 kg·cm (~3.0 N·m)

Some important points to be noted:

* I took some help from Claude AI to teach me how to even calculate this
* And also for some research on the constraints, like estimating the moving mass based on a real Meca500 with maximum payload.
* Then, I myself made some estimates, got it checked through AI again, understood the maths and mistakes
* Then again tried and then made the final estimates.
* The Good motor choice is based on [NEMA23 PR57HS76](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft).
* The Great motor choice is based on [NEMA23 PR57HS112](https://robu.in/product/pro-range-nema23-pr57hs112-3004-03-30-61-kg-cm-hybrid-bipolar-stepper-motor-round-type-shaft).

**Summary of today's session (Day 9):**

1. Restarted CAD development using finalized hardware specifications.
2. Imported accurate models of rails, extrusions, bearings, and structural parts.
3. Verified compatibility between sourced components and CAD references.
4. Constructed a more realistic digital representation of the robot platform.
5. Established a solid foundation for future mechanical integration work.

**Total time spent: 3h 30m**

---

# Day 10 — 04.05.2026: Research on Linear Rail CNC Estimates

I did some research on the MGN15H I am choosing, and after comparing models, I found out that the profile I sourced from JLCMC and the profile avaiable in HIWIN do not match exactly. The dimensions are a little different as well. I went to Robu.in to check the dimensions, but they didn't match exactly.

This meant that I had to choose my 3D model of the MGN15H rail from TraceParts HIWIN.

I found [this](https://www.traceparts.com/en/product/hiwin-technologies-corp-mgn15h?Product=90-07042020-029729) from TraceParts, and I downloaded it. I will use it in my model the next day.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3ec1d41c-ce74-4d99-8577-02b12531358d" />

I then dived into a little foreseeing the future. I know that CNC machining is really pivotal to give a robotic look to my PATRA, and no kind of 3D printing could match that feeling. But CNC is very expensive. I exported a random leg of Rowan's tirpteron to use it for an instant quote. I started searching for cheap CNC services in India.

1. **[Igus](https://iglidur-cnc-designer.igus.tools/result/drawing):** The first one I tried was from Igus. I first thought that since they have a branch in India, I could expect their machined parts without any customs, cheaply. But I was astonished to see the amount in Pound Sterling. The cost was 3,139.83 GBP. Looking at the amount, I realized beforehand that this is too much. Just as I converted the 3,139.83 GBP to INR, it came to literally 4,04,245.26 INR, which is completely crazy.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/8c17b34f-da34-4bf3-8174-de8b505bc730" />

2. **[JLCCNC](https://jlccnc.com/cnc-machining-quote):** I have experience from JLCMC. Both ordering and paying customs, so there was no way I was going to source my parts from JLCMC. But just to see how much it costs, out of curiosity, I uploaded the same model here to see the price. And, as I expected, it was a lot cheaper, yet still expensive for me. The price was quoted at $54.16.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c11e0e9b-6d01-4784-905c-fd6a0f7b36f5" />

3. **[PCBWay](https://www.pcbway.com/rapid-prototyping/manufacture/?type=1&reffercode=W):** Again, as I expected, the prices were much higher compared to JLCMC. The cheapest possible option with Aluminium 6061 was quoted at $329.46, which is way too expensive for an arm.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/dbc4f73a-2304-47a2-9749-9d6cf7e5e4e5" />

I then made the hard decision to choose only 3D printing for all the parts of my project. I would either print in my future printer, or I would choose MJF or SLA printing from local sources if possible.

**Summary of today's session (Day 10):**

1. Investigated dimensional discrepancies among linear rail suppliers.
2. Adopted verified HIWIN references to improve modelling accuracy.
3. Continued evaluating fabrication methods for custom robot parts.
4. Compared manufacturing services and their pricing structures.
5. Improved confidence in future fabrication planning and component selection.

**Total time spent: 3h 50m**

---

# Day 11 — 08.05.2026: Kinematic Base Module (KBM) Progress — Part 1

I began by making some changes to my existing model, as I came across some problems while continuing my modelling. To make the changes, I had to search a lot on many websites and download a lot of stuff to import and see if it would work. Anyways, the changes are as follows:

1. I replaced model of [E-BMN15H-2-L1000-ZF-C-E20](https://jlcmc.com/product/s/B03/E-BMN/economical-linear-guide-mini-standard-type-7-9-12-15?k=E-BMN15H-2-L1000-ZF-C-E20&productModelNumber=E-BMN15H-2-L%5B70~1800%2F1%5D-ZF-C-E%5B0~39%2F0.5%5D) from JLCMC with [MGN15H](https://www.traceparts.com/en/product/hiwin-technologies-corp-mgn15h?Product=90-07042020-029729) from TraceParts, as I saw that the rail was a little different from what I am buying from Robu.in.

2. I replaced [NEMA23 PR57HS51](https://robu.in/product/nema23-pr57hs51-2804-10-1kg-cm-stepper-motor-round-type-shaft) with [NEMA23 PR57HS76](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft) as I realized I needed more torque.

This ensures that my model is accurate and the robot is stronger and stiffer. The first motor provided 10 Nm of torque, but the new one provides 18.9 Nm of torque.

I then took a lot of inspiration from the LC4O family, specifically [LC40B-KM02](https://www.zaber.com/products/linear-stages/LC40B-KM02/specs?part=LC40B1000-KM02&srsltid=AfmBOootwqUCUVAZim0fLhepMvoiqAwhXvtNfsj9dF_MdNFuC1e7YDq7)] for my linear rails. I continued updating my model with the aforementioned changes, and then I added As-built Slider joints and grounded components to parents.

I then started finding the model of a NEMA 23 motor that matches the length of 76 mm, and after a few minutes of searching, I found [this](https://grabcad.com/library/nema-23-stepper-76mm-1), which matches my needs exactly.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/09f7862c-0b30-4d3f-b97b-9d546d787af9" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7ebeb4bd-72df-41c9-9a42-41edee29db31" />

**Total time spent: 3h 35m**

---

# Day 12 — 09.05.2026: Kinematic Base Module (KBM) Progress — Part 2

I continued working on the first stage. Previously, the motors were not aligned. So, this time I imported [NEMA23 mounting bracket aluminum](https://grabcad.com/library/nema-23-stepper-motor-mounting-bracket-1) and added it to the assembly. Then I added joints and then I duplicated it with joints, and made it symmetrical.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1be429f0-4029-4d24-aed7-e011c30ab6b9" />

I continued working on the first stage from the point where I had finally fixed the motor alignment issue. Previously, the motors were floating in space without a true structural reference. This time, I decided to anchor everything properly. I imported the [NEMA23 mounting bracket aluminum](https://grabcad.com/library/nema-23-stepper-motor-mounting-bracket-1) and placed it onto the 4040 extrusion. Once positioned, I constrained it fully using rigid joints, then duplicated the entire bracket assembly along with its joints and mirrored it to maintain symmetry. That symmetry mattered.

After locking down the brackets, I moved toward the belt architecture. I made a deliberate decision here: instead of an offset belt system, I wanted a stacked belt configuration. That means the belt would pass directly above the linear rail, and specifically above the linear block. Much like the design architecture of Rudmin.

Next, I started making a sketch for the belt path. I wanted to make a stacked belt architecture rather than an offset belt architecture, which meant that I had to make the belt go directly above the linear rail, above the linear block.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e21f17be-be3d-4bf3-b5af-a4351a50c4ba" />

To calculate the radius needed for the sketch, I calculated the height of the belt from the upper face of the 4040 extrusion. So I began calculating the stacked height from the top face of the 4040 extrusion.

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

Thus, I redrew the sketch and brought it lower, and things improved a bit.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3717f365-194a-48fe-87bc-de2f4361b503" />

It still overlaps. I guess this is all for today; tomorrow I will continue this.

**Total time spent: 4h 30m**

---

# Day 13 — 10.05.2026: Kinematic Base Module (KBM) Progress — Part 3

I picked up exactly where I left off yesterday. The return belt was overlapping with the 4040 extrusion geometry, which was not okay. It meant that I had to continue on one or more of the following paths:

1. I eradicate the NEMA23 mounting bracket and make my own mounting bracket for 3D printing it
2. I keep the NEMA23 mounting bracket but position it below the 4040 extrusion, making the architecture prone to more bending and stress
3. I use a pulley with a bigger and possibly unnatural diameter, which must be sourced from either big stores or custom-made
4. I add two more pulleys to position the return belt to the bottom, making the system contain more moving parts
5. I replace the 4040 T-slot extrusion with 4040 double T-slot extrusion, which has a hollow inside but is more expensive

I first tried paths 2 and 5.

* For path 2: I tried repositioning the brackets after suppressing the joints; the system seemed to work till I realized that it had become too fragile to take the mass of PATRA, so I dropped it.

* For path 5: I first surfed the internet to look at the prices. After looking at 6 to 7 different websites, I had already realised it is more expensive. [This](https://www.3dprintronics.com/products/t-slot-aluminium-extrusion-4040-6mm?srsltid=AfmBOopm2YIEr6eGFaIxCXIP6218Ygof1mdUS4i0Hx8fKVX-2w-9lQBm) one from 3DPrintonics for example costs 3200 INR per metre, [this](https://www.indiamart.com/proddetail/machifit-4040-double-t-slot-aluminum-extrusion-40x40mm-aluminum-profile-extrusion-frame-based-on-2020-for-cnc-25967776433.html?srsltid=AfmBOoq9RSyFu8JxcKxos3uZti6KXIaZwqFABJFlg8DoPGHpWxLGqibd) from IndiaMART costs 20272 per piece, and [this](https://novo3d.in/aluminium-profile-4040/) from Novo3D costs 2399 INR. Since this was reaching almost double the cost, I had to drop this.

Then I chose path 1 and 3, where I did the following:

Firstly, I removed the [NEMA23 mounting bracket aluminum](https://grabcad.com/library/nema-23-stepper-motor-mounting-bracket-1) and then started sketching my Motor Mount/Case, and extruded out components for path 1. The goal was to reduce unnecessary thickness and directly control the stacked height.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6b605459-58ce-43a1-9f27-4eda4eea2bff" />

Then I extruded 5 mm from the sketch and checked if it looked like an aluminum bracket, and yes, it most certainly did. It actually looks nice. Five millimetres gives enough wall strength for prototype testing, especially since I will print at 100% infill.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7b8a2753-0217-4d92-8411-f706a8ac02f6" />

Next, I copied the wall on the other side and added walls to make it an enclosure. This enclosure now supports both the pulley and the idler region while also acting as structural reinforcement.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/061a2c0c-059f-4b4a-94ee-1a83cfb2d6ba" />

I mirrored the component on the other end of the system for the idler.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/760eb93a-cd02-47ef-aa43-ea68cba2b583" />

This made a nice-looking enclosure that can house both the idler and the pulley, completing the whole system.

Secondly, I surfed the internet (for a long time) to find the pulley I needed. After checking both [JLCMC](https://jlcmc.com/product/C03/timing-belt-pulleys) and [MISUMI India](https://in.misumi-ec.com/vona2/mech/M1000000000/M1002000000/M1002030000/), I realised that MISUMI is more expensive than JLCMC, but when we add shipping and customs, MISUMI is the cheaper and smarter choice. Additionally, MISUMI has a lot of configurations available with a 3D model, just like JLCMC.

I chose [this](https://in.misumi-ec.com/vona2/detail/110310532889/?CategorySpec=00000005784%3A%3Aak%2C&list=PageCategory) pulley from MISUMI that costs 1,064.73 INR for now. But there is a problem: The minimum bore diameter available is 10 mm, but I need 6.35 mm, as the NEMA 23 PR57HS76 has a 6.35 mm bore. I will see what I can do to make this structurally correct. Anyways, I added it to the BOM, and downloaded the STEP files. I need two of them.

Next, for the idler, I am choosing [this](https://in.misumi-ec.com/vona2/detail/110310533069/?CategorySpec=00000005784%3A%3Aak%2C&list=PageCategory) from MISUMI that costs 1,621.82 INR each. I added it to the BOM, and downloaded the STEP files. I need two of them.

I updated the BOM with the necessary changes.

But after I imported the components in Fusion, I noticed that the diameters are too small for the belt, which meant that the belt could either brush against the linear guides, lower face of the 4040 extrusion, or even worse, that is both. The pitch diameter of the HTD 5M pulley increases with tooth count, so I kept increasing the tooth count to raise the belt path vertically.

So, I kept experimenting with higher and higher teeth count pulleys and idlers, until I was tired.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b769cea5-9b0b-4c1e-9a57-bbd19f94de39" />

Every time, I deleted the older ones so that everything stays organised. I even updated the BOM almost every time.

The next logical thing was to try something else. So I did. I looked for the belt. And after surfing the internet a little and then JLCMC, I found the perfect component from MISUMI, which is [this](https://in.misumi-ec.com/vona2/detail/110310527489?HissuCode=C-HTBN2350H5M-150). It costs 1667 INR, has an MOQ of 2, and I do need two of them.

I immediately added it to the BOM and imported the model into Fusion, only to realise that it was completely useless to import the belt into Fusion. The belt geometry is better controlled parametrically through pulley pitch diameter and center distance rather than solid modelling the flexible body.

**Total time spent: 5h 05m**

---

# Day 14 — 11.05.2026: Kinematic Base Module (KBM) Progress — Part 4

I picked up exactly where I left off yesterday, out of tiredness. I thus continued with 30T for the pulley and 28T for the Idler. It didn't fit. The pitch diameter difference caused uneven belt alignment and clearance issues.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7843fda2-afc5-4a4e-9d00-11b9f5b18972" />

Then I tried 32T for both, and that was the biggest configuration possible in MISUMI. Increasing tooth count increased pitch diameter and therefore belt elevation above the extrusion.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7843fda2-afc5-4a4e-9d00-11b9f5b18972" />

It did work better, but I am not completely satisfied. But I guess that is okay enough. With 32T HTD 5M, pitch diameter is roughly (32 × 5) / π ≈ 50.9 mm, which gives noticeably better clearance than 28T or 30T.

Next, I added motions and assembled everything cleanly and strategically. The system was almost ready. Only the enclosure for the pulleys and idlers doesn't have a hole passing through it that will allow the belt to move. That slot needs to be dimensioned carefully to prevent belt rubbing while maintaining enclosure stiffness.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d6919113-ca2d-4851-8f12-f6a25b61f894" />

I then mirrored the whole system. At this point, the first stage belt-driven axis is structurally defined: 1 metre 4040 extrusion, dual MGN15H rails, stacked belt architecture, symmetric pulley housings, and increasing tooth count to solve geometric interference rather than compromising stiffness.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/23017fbc-4351-45dc-b2bf-39eed43d4a6b" />

The system is beginning to look like a machine instead of an experiment, I guess.

Next, I updated the BOM with all the necessary changes for the following confirmed components:

* [Pulley C-HTPA32H5M150-A-N10](https://in.misumi-ec.com/vona2/detail/110310532889?HissuCode=C-HTPA32H5M150-A-N10)
* [Idler C-AHTFW32-H5M150-12](https://in.misumi-ec.com/vona2/detail/110310533069?HissuCode=C-AHTFW32-H5M150-12)
* [Belt C-HTBN2350H5M-150](https://in.misumi-ec.com/vona2/detail/110310527489?HissuCode=C-HTBN2350H5M-150)

Next, I made a financially smart move. Since the components were getting a lot more expensive, I thought of looking for aluminium extrusions from MISUMI, just in case they were cheap.

And yes, they were cheaper than my previous sources. For instance:

* The previous 4040 extrusion was 1060 INR each, but [this](https://in.misumi-ec.com/vona2/detail/110310647549?HissuCode=LCF8-4040-1000) from MISUMI is 840 INR.
* The previous 2020 extrusion was 469 INR, but [this](https://in.misumi-ec.com/vona2/detail/110311047509?HissuCode=LCF6-2020-1000) from MISUMI is 270 INR.

I made all the necessary changes to my BOM.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/520b13aa-1c0d-40bf-8948-abd0dd6bfb1a" />

<img width="2558" height="177" alt="image" src="https://github.com/user-attachments/assets/3b9d02b1-f401-42bd-8245-92cd46964f41" />

**Total time spent: 4h 10m**

---

# Day 15 — 12.05.2026: Kinematic Base Module (KBM) Progress — Part 5

It was now time to add the holes to the pulley and idler mount so that I could make the belt pass through and clamp, thus completing the tensioning system.

I first made a sketch on the face of the Pulley Mount, then added some clearance. Then I extruded the shape to make the hole in both the Pulley and Idler Mounts. It looked like this after the changes were made.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/37b08a2a-0b90-4dc1-ba34-86576ad714a9" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/85ae9d22-ca44-41ac-b40b-6ec78bc119ce" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9277f371-8e86-4bfc-9a9e-6571b7188e84" />

Next, I moved to the Linear Block Carriage system that was supposed to be the base of the legs of the robot and also secure the ends of the linear belts. First, I made holes in both the carriage and the belt. I realized that it is a very poor choice, as it will damage the tensioning system.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6f9b8aba-2a50-417b-9652-3d1fb08ed518" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/07d7dbfc-0ad4-4e05-b15f-d4697945e52d" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8b60f254-fc23-45ab-925b-4cdd2400e97a" />

Then I surfed the internet to find a belt clamp for an HTD 5M 15 mmm width belt. I found [this](https://www.traceparts.com/en/product/madler-gmbh-fixing-plate-for-timing-belts-made-from-aluminium-profile-htd5m-for-belt-width-15-mm?CatalogPath=MADLER%3AMADLER_NEU.3.3&Product=90-14112023-038068&PartNumber=17339900) from TraceParts, and then I imported it.

**Total time spent: 0h 55m**

---

# Day 16 — 14.05.2026: Kinematic Base Module (KBM) Progress — Part 6

This time I started by looking for the belt clamps. I searched on the internet and found nothing from India. I had high hopes for MISMI, but even though they had other types of Blet Clamps, they did not have HTD 5M belt clamps.

I had a change of strategy, so I decided to 3D print the clamp along with the carriages. Thus, I modified the 3D model I imported the previous day and positioned it perfectly on top of the MGN15H linear block first. Then I continued shaping it using extrusions and alignments.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c3553f60-bc46-418e-a176-68216480589d" />

I made the holes for screws; it started to look like this. Now the next step was to add the upper carriage that was modeled before. I just needed to make some little adjustments to the existing model.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/306069be-f0e5-4b1c-9f2e-b32633772a40" />

This is how it looks with the belt:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7868781e-554a-4602-b6be-3970036fc104" />

But unfortunately, I came across a really annoying problem. The thing was that the numbers related to the positions and the dimensions were not round numbers, but off my ±0.002 mm and even ±0.0005 mm. If you look at the image bellow carefully, you can see the numbers don't make any sense. Additionally, the pulley and idler cases were off by ±0.02 mm. Furthermore, the belt profile was ±0.319 mm off.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0fe15352-3f96-408b-b2ae-da1c584ee614" />

But I even put my hands on it in the first place because I use the project tool on new sketches. And when I noticed that the extrusions based on the projected faces were not symmetrical, I knew I had to fix it.

The fact that the numbers were round, and the nonsensical numbers on top, made my head scratch. I realised that Fusion rounds off numbers beyond ±0.000X.

I did get it over with.

Once the profiles and the facial projections were fixed in the sketches, I continued with modifying the carriage. I first positioned it properly, then joined them after adding holes for the screws.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/161bbe9e-ee2a-43b0-8717-3f21daf11665" />

Next, using the Cut feature, I integrated the lower belt clamp with the carriage and joined them.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a0296509-dc15-43cc-b936-eee526fb45e8" />

Next up, I copied the carriage to another linear block, and then I removed the belt clamp and added clearance for the belt to pass through any interference. This will be one of the Z axis carriages, and it will be controlled by the central belt system, which I am yet to model.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e9dd7fd5-8a76-4d97-b121-9d8107260298" />

Followed by that, I mirrored my components to see how the system looks, though I know that this has to be updated soon afterwards.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a9d7cc34-31dc-461f-8708-ded7da177162" />

Then I made some more changes to the name and hierarchical structure of the components before signing off.

**Total time spent: 3h 25m**

---

# Day 17 — 15.05.2026: Kinematic Base Module (KBM) Progress — Part 7

I had to work on the motions that will enable me to see how the system actually works. So I started by adding motions to the tensioning system after I watched [this](https://www.youtube.com/watch?v=_inMtaRoYMw) video.

But after that I realised that I actually don't need that. So, instead, I switched focus to something more useful. That was continuing with the the Z axis tensioning system. The X and Y axis tensioning system was completed already.

For the system, I first extruded the 2020 aluminium extrusion by 15 mm and then continued by moving the Pulley System.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4b2cd11c-3054-4da1-a89f-d006ab2fe5bc" />

Next, I can not use a 32-tooth pulley this time; instead, I need a smaller diameter pulley for the following reasons:

1. The height has to be lower than the X and Y belts.
2. The return belt must be closer to the extrusion.

I made one small adjustment midway, which was to position the 2020 extrusion vertically centered to the 4040 extrusion. Then I drew a sketch based on my intuition and extruded it to make a belt that can be updated later from the sketch.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d8bbe37d-7e83-4c93-ad7e-de5ae203bb6a" />

After that, I searched for pulleys and idlers from MISUMI. I found [this](https://in.misumi-ec.com/vona2/detail/110310532889?HissuCode=C-HTPA14H5M150-A-N8) pulley, which has 14 teeth. But the problem came when I searched for an equivalent idler which has 14 teeth, and I found none. So, I used this in the belt just to see.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/da01ae3b-6a1f-44d9-b7ff-e0825ea1db69" />

I had tried 20T, 22T, but then I also saw there was an MOQ of 2, and it was really expensive. After several changes to the confugarations, I chose to use I decided to source my parts from JLCMC instead, which I will do later on.

Bored of what I was doing, I started drawing a sketch based on my previous belt that I extruded from the sketch. I tried 20T as well and even 22T. My attempts were not random but actually structured, based on HTD 5M pulleys:

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

* For the [Idler C-AHTFW32-H5M150-12](https://in.misumi-ec.com/vona2/detail/110310533069?HissuCode=C-AHTFW32-H5M150-12) I found [CBYL-AH1-5GT150-32-A-H-d22](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-32-A-N-d22&productModelNumber=CBYL-AH1-5GT150-32-A-N-d22) also from JLCMC. I was unable to find an idler with teeth, so I am choosing this with double 625ZZ bearings.

* For the Z axis pulley and idler, from JLCMC I found [CBYL-AH1-5GT150-18-A-H-d6.35](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d6.35&productModelNumber=CBYL-AH1-5GT150-18-A-H-d6.35) and [CBYL-AH1-5GT150-18-A-H-d16](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d16&productModelNumber=CBYL-AH1-5GT150-18-A-H-d16), respectively.

But soon I realised that the parts I had sourced were not HTD 5M compatible. This meant that I had to use different belts and probably even different belt clamps. I tried searching for HTD 5M pulleys from JLCMC, but I found none.

Since I was buying from JLCMC, there was a very high chance that I needed to pay customs. If I am ordering only the pulleys, I can choose E-POST and pay about $20 in Shipping and probably $10 more in customs. But still, this option is a lot cheaper than buying pulleys from MISUMI.

I then went on to research the differences between HTD 5M and GT5 belts. I went through [this](https://www.apexdyna.nl/en/news/the-right-timing-belt) article and I found out that it actually didn't matter too much, but GT5 is actually better for my system as they are smoother. I am even finding a cheap pulley for GT5, which means that it is the best option for at least now.

Next, I updated the BOM

<img width="2383" height="121" alt="image" src="https://github.com/user-attachments/assets/cd373d89-e0e0-4beb-8f2b-500bea65d69f" />

**Total time spent: 3h 15m**

---

# Day 19 — 20.05.2026: Kinematic Base Module (KBM) Progress — Part 9

Now it was time to import the pulleys I had selected into Fusion.

I started by creating a new sketch for the belt. I had an estimate for the diameter needed for the pulley and idler, which was 27.5 mm. I initially thought of making the case smaller than the existing ones for the X and Y tensioning systems. So small, in fact, that it will be directly above and below the 2020 aluminium extrusion.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b76e0e58-a223-4293-b7c8-ecc51d1bf8a5" />

I then extruded the belt profile symmetrically to have a width of 15 mm (7.5 mm on both sides). Following that, I inserted the 32 teeth pulley and idlers to replace the existing ones and used align and joints to position them properly. In the tensioning system. I now had a rough visualisation of what the belt would look like in the system. I made sure that I am able to later edit the sketch in case I am using different size pulleys and idlers.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1f74a469-235d-4991-95c8-8ab82079a3c4" />

Part of the tensioning system was completed. The next step was to update the aluminum extrusions, as I had to find a way to reinforce the pulley and idler cases with the aluminium extrusion profiles.

Note that the 2020 extrusion will be 1150 mm in length, not 1000 mm. I will update that part later on, after I confirm the length.

Thus, I replaced the existing **TXCL-H7-4040E-L1000 (model from JLCMC)** with **LCF8-4040-1000 (model from MISUMI)** and the **TXCL-H7-2020E-L100 (model from JLCMC)** with **LCF6-2020-1000 (model from MISUMI)**, to ensure that I am following the exact profile that I will be buying and physically expecting.

I had previously thought that even though 4040 T-slots are generic, there would be differences in profile, varying from manufacturer to manufacturer. Just as I thought, after I imported the updated 4040 and 2020 extrusions, I saw that the profiles had noticeable differences that could've caused manufacturing and assembly issues.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/86ccabac-1fa1-4483-996a-58795552bf0f" />

Next, I gave emphasis on reinforcing the existing pulley and idler cases to the aluminium extrusion, without using just screws. Since I got access to the correct profile, I tried to extrude certain parts of the profile to have them seamlessly connected to the aluminium extrusion without relying much on screws.

About adding serews, the major problem was that the case was split in such a direction that it is hard to add screws; the minor problem being that tapping the profiles on both sides from MISUMI was quite expensive. I can consider that later on. For now, I am just extruding out some part of the case.

This is how the extrusion looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1d96865c-0d6d-41f8-9a7c-bdda6a567f4d" />

I then arranged the components in the Browser, added proper materials for the appearance, and updated the BOM.

<img width="2383" height="197" alt="image" src="https://github.com/user-attachments/assets/72599af8-f03e-496e-a313-fe883cf7219f" />

**Total time spent: 4h 15m**

---

# Day 20 — 21.05.2026: Kinematic Base Module (KBM) Progress — Part 10

Previously, the bare-bones tensioning system involved the following:

* [Pulley CBYL-AH1-5GT150-18-A-H-d6.35 (Z)](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d6.35&productModelNumber=CBYL-AH1-5GT150-18-A-H-d6.35): This is the pulley I had selected previously. I changed it to [CBYL-AH1-5GT150-20-A-N-d12](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12) to ensure that I can extend the short motor shaft.

* [Idler CBYL-AH1-5GT150-18-A-H-d16 (Z)](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d16&productModelNumber=CBYL-AH1-5GT150-18-A-H-d16): I have not changed this.

* [Belt E-GBN26005GT-150 (Z)](https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN26005GT-150): The length is just an estimate, but the belt itself is finalised so far and compatible with the system.

After that, I realised that there was something wrong with the motor shaft couplings. They were overlapping with both the pulley and motor shaft geometry. So, I first fixed that by face offsets and extrusions. I made it compatible with the N-type hole of [CBYL-AH1-5GT150-20-A-N-d12](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12), making it look like this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/aadc0fc7-3f9d-492e-887d-75954a79576d" />

After having fixed the Tensioning System X, I mirrored the component to create the Tensioning System Y that is updated.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/faa72841-2548-4188-9ec2-a290a7c6eee3" />

Next I dived into modelling the pulley and idler case, for which I first went through the sketch and edited some parts. I found out that I had to raise the Tensioning System Z a little to ensure that I could use a similar-sized case for the pulley and idler as the other tensioning systems. I then also added the [NEMA23 PR57HS76](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft) and placed it correctly.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d918ab38-b825-4a4b-9525-4abf49ddd6fb" />

But then I saw that the return belt of the Z axis was completely overlapping with the 2020 extrusion, so I moved it a little up and placed it between the belt of the Z axis.

I can now confirm that the tensioning system was completed beyond just the bare bones.

Thus, next I moved to making the case for the pulley and idler, starting with a solid block, and then making it hollow from the sketch. Then I used split it divide it in two parts, for assembly.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e957f3c6-3d3f-46b4-a132-743e3393771a" />

I repeated this step for the idler as well using the mirror tool, and then arranged the components in the browser.

The next step was to add a GT5 belt lock so that the system can drive the Z axis. I searched first in TraceParts, then in Printables, then MISUMI, then JLCMC, but didn't find exactly what I was looking for. After a while, I found [this](https://grabcad.com/library/gt5-belt-lock-1) in GrabCAD.

I thought that it was okay, and I imported it into Fusion only to realise that it was too small for the GT5 belt profile (as if shrunk), and that time was over for today's session.

**Total time spent: 3h 55m**

---

# Day 21 — 22.05.2026: Kinematic Base Module (KBM) Progress — Part 11

I started by downloading the [Pulley CBYL-AH1-5GT150-20-A-N-d12 (Z)](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12) and [Idler CBYL-AH1-5GT150-18-A-H-d16 (Z)](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d16&productModelNumber=CBYL-AH1-5GT150-18-A-H-d16) from JLCMC, which were the components paired with the [Belt E-GBN26005GT-150 (Z)
](https://in.misumi-ec.com/vona2/detail/110411276379/?HissuCode=E-GBN26005GT-150) that I had finalized for the Z axis tensioning system. Then I updated the assembly by replacing the components.

Since I had replaced the pulleys and idlers, it meant that I had to make sure that the belt fits perfectly with the new components, instead of adapting. So, I visited [this](https://in.misumi-ec.com/vona2/detail/110411276379/) datasheet of the GT5 belt from MISUMI and had a brief look at the dimensions, so that I could match my existing one with it. I had a look at the 3D preview, but it honestly made no conclusion, so I downloaded the STEP file.

<img width="447" height="163" alt="image" src="https://github.com/user-attachments/assets/7c7fc1eb-e7e2-476b-a30e-eed67d72015a" />

I imported the model into my workspace and positioned it just above that one belt lock, which I imported from GrabCAD yesterday. To be specific, it is this one: [GT5 belt lock](https://grabcad.com/library/gt5-belt-lock-1). My eyes kept telling me since yesterday that it was no way GT5. I confirmed it now. Maybe I did make a mistake while choosing the file to download. Anyways, it seemed like I could make my own timing belt. I proceeded to take measurements of the imported model and confirmed if the dimensions actually match the datasheet.

Once I confirmed that each tooth was absolutely perfect, I used the pattern tool to duplicate a single tooth across the whole belt. I kept the spacing, or pitch, at 5mm. Of course, the last one was not perfectly distanced from the first tooth, but it didn't matter.

The reason I am doing this is because of the following reasons:

* I wanted to carve out my own timing belt lock, instead of relying on other models from the internet.
* I wanted to see how the whole belt would look with all the teeth.
* I wanted to see how well the teeth would line up with the idler and pulley.

I then shifted focus away from the belt, pulleys, and idlers of the tensioning system, and instead focused on the pulley case, idler case, and the extrusion. So I fixed the length of the 2020 aluminium extrusion to prevent overlapping and the radii of the point of intersection between the NEMA23 and the pulley and idler case.

Then it was time to fix the X and Y belt locks, because they were still HTD 5M compatible, not GT5 compatible. For that, here is the workflow I adopted:

1. I used an extrusion to cut down the belt clamp to half of its width, making sure I could directly look into the teeth grooves.
2. I positioned the 8 teeth (with 5 mm pitch) properly by moving it 0.1 mm, since it was off by that margin.
3. I created a sketch for the profiles that were in excess in the cross-section, and then extruded them in and joined them.
4. I mirrored the corrected part and then combined them.

I then fixed the ceiling of the part above to make sure it tightly clamps the belt in place. With this, the clamping system for both the X and Y tensioning systems was fixed. Now it was time for the Z axis tensioning system that will sit in the middle of the two Z linear blocks.

For that, I duplicated the clamp, then positioned it to perfectly align with the belt path of the Z axis tensioning system. But during that, I found some weird problems with the faces of the belt clamp. So, I had to fix it by making it a solid body extrusion, then using the 8 teeth to cut out the shape of the GT5 tooth. It produced a cleaner and more accurate customized clamping belt that is more reliable. Then I replaced the old messy GT5 clamp with the new clamp for both the X and Y axis, while keeping the part with the mounting screw hubs almost untouched.

Next part was about to model the part that actually connects the floating belt clamp to the two Z linear blocks. This step was not very strict in terms of design, so I made it look as good as possible. For that, I added little fins on either side of the linear block ends. I copied the design to the X and Y linear blocks as well.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/18da3741-9f52-4d04-862a-2d8d56af0993" />

Since the motor of the Z axis was running two linear blocks, I decided to use [NEMA23 PR57HS112-4204-01 31kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs112-4204-01-31kg-cm-stepper-motor-round-type-shaft/) instead of [NEMA23 PR57HS76-2804-05 18.9kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft/).

With this much progress done today on the parts, it was now time to update the BOM. And so I did.

<img width="2559" height="297" alt="image" src="https://github.com/user-attachments/assets/718dc784-ccae-405c-a248-e06c685a839d" />

But when I paused my lapse and then came back, I forgot to resume it. I had made more changes to the BOM and fixed some overlapping components, troublesome downstream features, and timeline errors. The First stage is almost complete after all this.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4b605071-5c56-4343-b12e-89baed85f349" />

Here's the lapse of today's session: [PATRA-LPS-1-D21](https://lapse.hackclub.com/timelapse/LMIzn1To8zm3)

**Total time spent: 5h 55m**

---

# Day 22 — 23.05.2026: TriTeron Robot Module (TRM) Progress — Part 1

With the Tensioning System mostly done, it was time to start working on the TriTeron. As discussed earlier, I will be following Rudmin's design combined with Rowan's. For the Kinematic Base Module (KBM), I followed Rudmin's design, and for the TriTeron I will be following Rowan's design with slight changes in the leg position.

Before I dived into the TriTeron part, I thought of first improving certain design features of the Linear Block, using chamfers and drafts. Once it seemed like it looked better than before, it came to me that if I am adding something on the top of the Linear Block Unifier, I had to use flat-head screws.

For that, I went to OnlyScrews and started searching for the right screw. I found the perfect screw type needed. For the adjustments, I added chamfers to house the screw heads.

With the thought of starting easy, I chose to work on the front two legs, which are supposed to be the Z axis legs. They will be connected via Z Axis Mount. Thus, I started modelling the Z axis mount, which was supposed to have an angle of 45 degrees at the face where the front two Z axis legs were supposed to be attached. For this step, I looked at Rowan's model and Rudmin's video several times.

Once the Z axis mount was roughly done, I shifted focus to the X and Y axis mounts. I was confused about the angles of the joints, so I relied mostly on the exact angles provided in the model of Rowan's tri-pteron. For getting the angles right, I even imported the Bearing Mount of Rowan's design in my workspace. But they made almost no sense to me. So I followed Fusion's measurement tool's data about the angles, and I made a circular body that I could use in the future for joining the legs.

Next, I thought of modelling the legs, for which I will be following Rowan's design, not Rudmin's. So, first I made holes in the Z axis mount that was supposed to mount the lower part of the two front Z axis legs.

Then, I made a new design, where I started to model the leg by drawing a sketch. Here's how I did it:

1. I made a center-to-center slot of 150 mm and 30 mm diameter.
2. Then I made circles of 15 mm and 25 mm on either center point of the slot.
3. I drew a line 7.5 mm away from the slot's central line and made it connect to the circles.
4. I made some adjustments to manage to add fillets to the point of intersection between the line and the circles.

After the sketch was done, here's how it looked:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/478bc880-ab3f-469c-811a-9e9f799a4f07" />

The next step was to extrude the sketch to achieve the shape needed. Here's how I did it:

1. I first extruded the full sketch, creating a solid body.
2. I made the 15 mm holes using an extrusion cut.
3. I made the 25 mm diameter, 7.5 mm deep hubs for the bearing for the bottom part.
4. I made the 25 mm diameter, 7.5 mm deep hubs for the bearing for the top part.

After this step, here's how it looked:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/caf97c09-089a-4fc3-a060-ef940fc1c394" />

The next step was to create a sketch along the outer flat face of the leg to add design:

1. I drew a shape where one circle of the extruded slot had only half of its height, and added fillets.
2. I used offsets to achieve a shape similar to the face itself.
3. I extended the corners to form triangular points.
4. I added fillets in the corners to make it look better.

Here's how the sketch looks after completion:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/cd156669-c61c-47e5-819d-57a95f0afc3b" />

After I made the extrusion only for the design part, here's how it looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5868b29e-e968-491b-8cf3-084f0069687e" />

Next, I needed to set up a face that was located along the length of the slot. For this, I copied the component, named it "midref," and extruded a specific part from the last sketch, achieving this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/eeef17e7-e2cd-49db-b783-c39f10407753" />

On that face of the midref, I made this sketch:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/65ad18c3-2c2f-4b7d-886c-6947e29b667a" />

Using the revolve tool, I revolved the sketch and achieved the shape I wanted. Then I made a little extrusion to make the face above the bearing hub flat, which would be in contact with other legs. And I also adjusted the bearing hubs' positions using nothing but extrusions.

Here's what I achieved:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c27b5ead-c0aa-4bfb-b9b9-2533e48c4258" />

The leg was complete. It was then time to integrate that into the assembly. So, I imported two of them and used revolute joints to place them exactly over the hubs, which I made in the Z axis mount. I will later mirror them after one side is finalized. That was all for today. Here's how it looked:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2c66b2a1-0610-49ad-af57-415c9bb4c596" />

Here are the lapses of today's session: [PATRA-LPS-2-D22-1](https://lapse.hackclub.com/timelapse/DfNLfUEVeITT) and [PATRA-LPS-2-D22-2](https://lapse.hackclub.com/timelapse/8V5IIaFo7r2J) (the third lapse showed error and was deleted)

**Total time spent: 3h 50m**

---

# Day 23 — 24.05.2026: TriTeron Robot Module (TRM) Progress — Part 2

I picked up exactly where I left off yesterday. As the leg was complete and imported into the assembly, I can continue with positioning it properly.

There are going to be 4 legs in total, each with two connected legs.

* There will be one X axis leg consisting of one upper and one lower leg
* There will be one Y axis leg consisting of one upper and one lower leg
* There will be two Z axis legs consisting of one upper and one lower leg, each

But due to some errors, I went back in the timeline and then restarted from the part where I had just imported the leg into the assembly. After that, I created new components and duplicated the Leg 4 times in one way and 4 more times mirrored. But due to some chaos, I deleted them and instead imported the design as bodies, not components, and copied them like that.

I started with the assembly of the front two legs of the Z axis, and used joints to position them into the correct place. And for the angles, I followed the exact angles of Rowan's design provided in the design. For one, it felt like I had to learn 3d kinematics algebra. I was actually quite excited for this, but I had a better idea, for the time being.

The plan was to import Rowan's design's legs into the model only to get the angles and align components in place, not to actually use the model.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/be227750-5b7d-4c37-8e2f-d9bb3357811c" />

Once I adjusted the positions and angles, I made sure that the legs followed the position of Rowan's designed legs as closely as possible.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/858f9eeb-bb7b-45b2-87cf-bb1a1215d179" />

I followed the same sequence for the back legs as well.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ffb5eb4a-4766-4c40-ab22-352ee177ec5c" />

Then I mirrored them.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2c5ec4a8-b8c3-4424-ae79-7cdba3d60a74" />

I was not completely sure about the X and Y legs, but the front two Z axis legs were mostly done. Here's how it looked:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/710049cc-3663-446c-ba62-2b513a17f71d" />

Here are the lapses of today's session: [PATRA-LPS-3-D23](https://lapse.hackclub.com/timelapse/vCOvL9YC8t7R)

**Total time spent: 2h 30m**

---

# Day 24 — 26.05.2026: TriTeron Robot Module (TRM) Progress — Part 3

I was done with the positioning of the front two Z axis legs. Now was the time to fix the position of the Z and Y axis legs.

By fixing, this is what I mean:

* The lower end of the X and Y axis legs do not overlap or touch the linear block.
* The elbow of the X and Y legs does not extend much farther out or much in.
* The elbow height matches the elbow height of the front legs of the Z axis.
* The back legs are positioned similarly to [Rudmin's design](https://www.youtube.com/watch?v=6EtXycVGJg4).

Using rotations and movements, I positioned the X and Y legs properly.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/33c1c2a2-e56b-4d25-aaaf-d6e44f021965" />

Then it was time to work on the X and Y axis mounts, which was quite tricky due to the angles, but with some extrusions I was able to come up with this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/88e2584d-1f0c-46fe-834a-50ec65aee4c2" />

With that done, I started writing past incomplete journals from older days and added a summary for journals of days #1 to #10, simply because I was tired.

Here's the lapse of today's session: [PATRA-LPS-4-D24]()

**Total time spent: 1h 30m**

---

# Day 25 — 27.05.2026: TriTeron Robot Module (TRM) Progress — Part 4

Today's session achieved almost nothing except the sketch I made at last. But I am still writing this all up for the sake of appreciating failures.

I was not starting from scratch this time, because I had this body which I don't know what to call or even what exactly to do with. This is what I am talking about:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0ad9b52f-ca36-4bef-aab7-7935601e8f79" />

I wanted to achieve a carved-out geometry that could enclose the losai of the legs. I used the lower leg geometry to cut out a part of the shape, and I wanted to make something from it, which I wasn't quite sure of.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ba754a84-7fec-481f-aee6-735917bc60dc" />

But this design was not very promising. Then, I wanted to have a body with a chamfered vertex that would be the same angle as the X and Y lower legs' last joint's angle. For that approach, I deleted that part, and I achieved this.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/80a13c4f-c5f1-4fb9-a050-361de76cbd6d" />

But this was also seemingly strange and structurally weak. 

I continued working on the X axis leg mount, but I was not coming up with any ideas about how to connect the legs to the linear blocks. That's when I had a look into Rudmin's design, and then I found out exactly what to do.

I made this sketch that will have an extruded out diagonal body that will have a hole to connect the lower part of the back legs.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/25f28af6-ed21-44ad-ba67-ad4a61c93ca2" />

The sketch was for creating a body that intersects with the extended midpoint of the lower leg when viewed from the top and the linear block's vertical center of mass when viewed from the top as well. There was an angle of 56.105 between the linear path and the angle of the lower leg when projected on the floor.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/55de0995-3577-456e-812f-851f899dd5cd" />

I had some problems with positioning the sketch correctly. At times it was 1.5 mm off, and the sketch between the lower leg and the linear block didn't line up. But while fixing that, my time was over.

Here are the lapses of today's session: [PATRA-LPS-5-D25-1](https://lapse.hackclub.com/timelapse/XQaZ_Rl9L285) and [PATRA-LPS-5-D25-2](https://lapse.hackclub.com/timelapse/zi7MiJX0X9Cf)

**Total time spent: 3h 20m**

---

# Day 26 — 28.05.2026: TriTeron Robot Module (TRM) Progress — Part 5

Yesterday, the sketches didn't line up. Today, after fixing the offset, there were problems with the sketch itself due to the timeline features. So, redrew the sketch again after fixing the offset of 1.5 mm.

I then confirmed whether the sketch was correct and if the points were intersecting correctly. The angles lined up, and it seemed fine. Then I followed these steps to achieve the geometry, which not only looked better but also was structurally more sturdy and ideal.

This is the sketch:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2000a1ac-f4ae-4ad1-a120-c3650d24d216" />

I first extruded a body.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/de70120c-563d-4a19-b3e6-83e6af7c3f87" />

Then I made a hole in it using extrusion from the lower leg profile.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c3b6d0aa-948c-47ef-bd13-931dd4d450ab" />

I added a chamfer to make it look better.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c4f8c16a-9a18-4f8e-86f2-ad8038503620" />

I also mirrored it and gave it an appearance.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/99717ec1-d8fb-4012-a1c0-712dee0e32f7" />

Then it was time for the Tool Head to be brought into existence. Immediately I did this:

* Started with a simple cube of 100 mm by 100 mm by 100 mm.
* I moved it up into the correct position.

But wait, I had forgotten some things:

1. Arrange the components and establish correct parent-child component relationships in the Browser. So I did that first.
2. Convert the Legs, which were bodies, to components.
3. Apply revolute joints to every point in the leg.

The first two didn't take much time, but the third one took a lot of time to achieve. This was not my first time adding revolute joints to an already-established triteron (even though the tool head was not completed); this took some more time than I had expected.

But yeah, I was indeed able to achieve normal movement in the triteron.

[PATRA-LPS-6-D26](https://lapse.hackclub.com/timelapse/oC5sY39XrQ18)

**Total time spent: 1h 45m**

---

# Day 27 — 30.05.2026: TriTeron Robot Module (TRM) Progress — Part 6

With those joints done on the previous day, I continued with modelling the Tool Head, which I was most concerned, worried, and confused about because I assumed that it would be very complex to model the tool head, since the very beginning. But I logically broke down the workflow into these simple steps in real time (not pre-planned) and achieved the correct geometry.

Here's what I did:

1. I moved the leg a little towards the front (towards the direction of the Z axis legs)

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/137222c6-7c54-441a-855f-1a3887d16f1f" />

2. Extruded the back of the cuboid 25 mm to achieve a longer body.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/86958251-43a4-488d-b2ac-5f0097d2b904" />

3. Moved it again a little towards the front.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/687e3745-9817-4db2-ac76-21e5ab78d09d" />

4. Using the Combine Cut tool, made the upper X, Y, and Z legs cut the tool head.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/dd9ddc5d-d6ac-48be-a80a-f8854f343165" />

5. Made a new sketch that extends the angle of the front Z axis legs.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3158232d-c217-490e-8d4a-95c7525071e2" />

6. Split the body by extending the highlighted face.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/07474342-290b-4002-81e1-4a62e2fdf411" />

7. Split the body by extending the highlighted face.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/581834c9-2a9c-4622-9fd6-d1e4e18b5529" />

8. Split the body by extending the highlighted face.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/290b43ef-a192-4520-ab33-ec674e93c94d" />

9. Combined the back part with the Tool Head.

    <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/99965e64-b227-49a9-8703-4cdd843f144c" />

10. Used chamfers to achieve the design.

    <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a5e7c10d-33c4-4f64-ac98-7277ba489e5f" />

Throughout the workflow, in the first steps, I was working by seeing Rowan's design, but on the later stage, it seemed like I found the path for the correct set of steps to achieve the design needed.

There is some difference between this design and the design of Rudmin and Rowan. To be specific, this is a perfect mix of both.

Let me explain Rudmin's Tool Head design:

* Rudmin's design features all the legs at the same level.
* Rudmin's design is simpler, more straightforward, and even has a hole in between.

Let me explain Rowan's Tool Head design:

* Rowan's design features the X and Y axis legs to be raised above the front Z axis legs.
* Rowan's design has lots of chamfers, fillets, extrusions, and a more detailed design.

Now, let me explain my Tool Head design:

* Just like Rudmin's design, all the legs are present at a similar level in my Tool Head Design.
* Just like Rowan's design, the Tool Head is designed in a more complex manner, with fillets, chamfers, and extrusions.

With that done, I was testing the movement of the tripteron, or more appropriately, playing with my digitally made tripteron and also checking if angles are okay, movements make sense, and if it is flexible enough to bend in different angles.

Here's the lapse of today's session: [PATRA-LPS-7-D27](https://lapse.hackclub.com/timelapse/srgx05NYIPdJ)

**Total time spent: 1h 00m**

---

# Day 28 — 31.05.2026: TriTeron Robot Module (TRM) Progress — Part 7

In today's short session, I added some design elements and started modelling a fork and clevis joint as in [Rudmin's design](https://www.youtube.com/shorts/74T0LF2l5Ck).

For the design elements, here's what I did:

1. I made fillets on 4 sharp edges under the Tool Head. So, it went from this:
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1bcce337-590e-4964-99fc-9839c2e9fd54" />
	To this:
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/cd5f307a-f0af-4e93-9159-7e22c1a98aa2" />

2. I added a pocket on each side of the Tool Head to reduce material usage and mass. This design element, which was inspired by the Tool Head of [Rowan's Tripteron](https://www.youtube.com/watch?v=io4S9amExNM&t=1s), also made the design look better than before. I also added fillets to the internal edges of the pocket to improve the design. So, it went from this:
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0baf591d-b81f-4fa3-bc55-b2e9f4af3637" />
	To this:
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/af27709b-435a-452f-80b7-07bc542075e5" />

But then, it made me wonder if Rudmin's design of for and clevis joint for legs will be better for the system. Unlike Rudmin, Rowan has used distal joints for the system. For the Z axis legs, I noticed that I can't rotate them much, as the legs easily overlap if the angle goes over 30 degrees. Thus, it seemed like I needed to use a clevis joint.

For the fork and clevis joint, here's what I did:

1. I started modelling from this mirrored geometry of the pre-existing leg.
	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/eb47c686-c2e4-443b-8419-14740291def6" />

2. I turned it into this:
	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7bda38c3-2899-46e4-8a9a-075073129543" />

It is not yet complete. I will complete this the next day.

At last, this is how the triteron looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/336a41aa-2f9b-46e7-8f2a-d78c0f5852be" />

Here's the lapse of today's session: [PATRA-LPS-8-D28](https://lapse.hackclub.com/timelapse/AqGtmyhMh9QV)

**Total time spent: 0h 45m**

---

# Day 29 — 01.06.2026: TriTeron Robot Module (TRM) Progress — Part 8

Today I continued modelling the fork of the clevis joint from the day before.

The joint has two parts:

1. Yoke: This is the U-shaped or forked body with two parallel prongs and aligned holes, which I started modelling yesterday.
2. Tang: The flat or looped mating piece that fits inside the U-shaped prongs and is secured by the pin, which I will model today.

First, I continued to model the yoke that I had started modelling yesterday. Using split body, extrusions, and facial offsets, I was able to achieve a mechanically sound fork.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/203c00ec-21d5-45c0-9e44-541810209755" />

Then it was time to model the tang. To model the tang, I used the original design of the leg that was for the distal joint.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7143e603-d600-4d8d-9c20-0eed25de1eb4" />

But when I imported them into the workspace and tested the movements, it performed even worse than the previous distal joint, and there were overlapping sections at even lower angles.

Then I got the perfect idea: I used Combine Cut to cut out a section on the upper leg, so that they don't overlap at even 40 degrees.

Here's how I did it:

1. I first drove the joints below the Tool Head to a degree where the upper and lower legs overlap.
2. Used Combine cut to delete the overlapping part from the upper leg, keeping the lower leg the same.
3. Added a 1 mm offset on the newly cut area for clearance.

[PATRA-LPS-9-D29](https://lapse.hackclub.com/timelapse/ltNZ51iqS6UI)

**Total time spent: 2h 10m**

---

# Day 30 — 02.06.2026: TriTeron Robot Module (TRM) Progress — Part 9

Due to some problems with the design, I had to delete the features of the timeline where I added the cuts on the upper Z axis legs. So, this time, I did it again, but better.

Here's how I did it.

1. I first drove the joints below the Tool Head to a degree where the upper and lower legs overlap.
2. Used Combine cut to delete the overlapping part from the upper leg, keeping the lower leg the same.
3. Added a 1 mm offset on the newly cut area for clearance.
4. Added fillets on the internal and external sharp edges of the cut area.

This is how it looks now:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/bb85a885-b030-41e7-9b40-208cd0cac308" />

I also had to see how they compare to Rowan's design. For that, I copied the legs designed by me and imported them into Rowan's design. Visually, there was indeed some difference from close up, but the mechanism that I was most worried about was fine.

The next subject of concern was the leg joints. Honestly, I still couldn't understand what joints Rowan was using. I watched parts of his video several times to figure out what he was using. Upon a Google search, I came to know that he was using thrust washer bearings for the joints, instead of normal bearings. I thought of using regular bearings instead of washer bearings, as sourcing reliable washer bearings seemed hard at the moment. Linear bearings could also work, but linear bearings were expensive. This is how a thrust washer bearing looks:

<img width="1024" height="643" alt="image" src="https://github.com/user-attachments/assets/a24ff867-e1ae-4a41-88f1-b25cbae4e7cc" />

But before I could proceed with any changes in the assembly, I noticed that the X and Y proximal joints are off-center, so I had to fix them.

For example, this distal joint on the Y axis leg was having an off-centered joint.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5e4d3b10-60aa-4763-970e-23db08884aaa" />

After fixing it, this is how it looked.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9c0b875f-8b95-4ca6-9786-7ba12d44ba97" />

[PATRA-LPS-10-D30](https://lapse.hackclub.com/timelapse/_aOokRs_SLGK)

**Total time spent: 1h 10m**

---

# Day 31 — 03.06.2026: TriTeron Robot Module (TRM) Progress — Part 10

Today's target was to fix the joints, as they were not aligned properly and were asymmetrical. Yesterday's decision was to use regular bearings, so I also worked on that.

I spent the first few minutes fighting in Fusion and aligning different parts of the assembly. There were some problems in the upstream features, especially Capture Position, that were causing a lot of problems. There were severe problems with the joints in the design. 

With the problems fixed, I was finally able to proceed with something more meaningful: the joints. For the joints, I thought of using 3 608ZZ Bearings for each leg. 

Here's what I did next to proceed and optimize my design for the bearings:

1. **Fixing the Bearing Hub Radius & Depth:** I changed the diameter of the bearing hubs from 25 mm to 22 mm, made sure the depth is 7 mm.
	Previously, the hub was 25 mm in diameter
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/bef812bc-6824-44ac-9c0b-19a24a09c962" />
	Then I made it 22 mm in diameter
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/050c8025-422d-4563-9052-1da7af97d5e8" />

2. **Imported 608ZZ Bearing from McMaster-Carr:** I went to McMaster-Carr in Fusion and then imported a bearing with size matching exactly with a 608ZZ Bearing. 
	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/122201d3-16bd-4489-bf83-bb04732db904" />

3. **Re-structuring and Renaming Browser Legs:** I noticed that in the browser, there was no hierarchy for the legs. So, I renamed and restructured them in this order: in the parent components, there will be ***X***, ***Y***, or ***Z***, followed by ***Axis Leg*** and either ***Upper*** or ***Lower***. For the Z axis, there is also ***A*** or ***B***, followed by that, depending on the side. The side of the X axis is ***A***, and the side of the Y axis is ***B***. Here is how the structure looks:  
	<img width="300" height="489" alt="image" src="https://github.com/user-attachments/assets/0b89bb6e-17a9-4161-a211-971c24b0da33" />

4. **Re-structuring and Renaming Browser Leg Joints:** For the naming and hierarchical system, I had to put the internal combustion engine of my brain through a hard time. But I somehow came up with this: There will be three parent components: ***X***, ***Y***, or ***Z*** with ***Axis Leg Joints***. Under them, there will be ***608 Bearing*** followed by the axis letter (***X***, ***Y***, or ***Z***), upper or lower leg denoted by ***U*** or ***L***; and then a ***1*** if the bearing is on the top of the proximal joint side; ***2*** if on the bottom of the proximal joint side; and ***3*** if on the distal joint side. But for Z axis legs, after ***Z***, there was either ***A*** or ***B*** in the name to denote the side. For example, the highlighted bearing in [this](https://github.com/user-attachments/assets/70a2de85-348d-4215-bd50-a5bd40e32229) image is **608 Bearing YL1**, while [this](https://github.com/user-attachments/assets/21ddf0ea-e346-4ab6-ab8c-33ca7e392b64) is **608 Bearing ZAU3**. Here is how the structure looks:
	<img width="300" height="514" alt="image" src="https://github.com/user-attachments/assets/d9e4a896-d6a2-480c-9340-a890047156f7" />

5. **Joining Bearings:** After the bearings were named and arranged into a sequence, I used the Joint tool to assemble them in the correct places. I encountered some problems with the timeline, but it was minor, so I was able to easily fix it. This is how it looks after assembling:
	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/586ea472-45a7-41e2-af66-d996dcd74c46" />

With all that done, the next part was the fasteners: shoulder bolts, nuts, and washers. But I was not sure about the way things would come together. I even watched Rowan's tripteron assembly. Here's how I found them:

1. **Shoulder Bolt:** I started by searching in Only Screws, but I didn't find what I needed. Then I looked in JLCMC instead, and the options were better. I chose [E-GBN23005GT-150](https://jlcmc.com/product/s/E02/EDLP/iso-7379-gb-t-5281-hex-socket-shoulder-screw-(set-screw)?k=EDLP-S1-B-d8-L30&productModelNumber=EDLP-S1-B-d8-L30) for proximal joints from JLCMC and imported in the design in Fusion. And for distal joints, I chose [EDLP-S1-B-d8-L35](https://jlcmc.com/product/s/E02/EDLP/iso-7379-gb-t-5281-hex-socket-shoulder-screw-(set-screw)?k=EDLP-S1-B-d8-L35&productModelNumber=EDLP-S1-B-d8-L35).

2. **Nut:** I was not sure what size nut I needed. I first thought I needed M6, then M8, and then again M8. There was [this](https://onlyscrews.in/products/m6-nyloc-nuts-ss304) DIN982 M6 nut Only Screws. But there was no M8 nut on Only Screws. For the M8 screw, I found this [EMLC-S1-N-M8](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M8&productModelNumber=EMLC-S1-N-M8) on JLCMC. And for M6, I found [EMLC-S1-N-M6](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M6&productModelNumber=EMLC-S1-N-M6), also on JLCMC.

3. **Washer:** Finding the washer was easier than I thought. I found [SS304 M8 Washer](https://onlyscrews.in/products/m8-washer-ss304?currency=INR&country=IN&variant=49592314691897&stkn=6e84ebfba1b8&utm_source=google&utm_medium=cpc&utm_campaign=Inderans_Campaign&utm_content=Other_than_fasteners_wala_copy&gad_source=1&gad_campaignid=22229905346&gbraid=0AAAAA9sP2SS13C7O8clb3n7juN0NJicBD&gclid=Cj0KCQjwrZTRBhDSARIsAHidYff_2voIe-8RPEu9AA21EZff0GSSyk4MWjjptkDVLWuZe4Rjuu5uqCkaAtCuEALw_wcB) from Only Screws.
Here's the lapse of today's session: [PATRA-LPS-11-D31](https://lapse.hackclub.com/timelapse/cPrT8Rbqh_sX)

After that, I assembled them into a set after exporting them and importing them into Fusion. For the washer, I created a sketch in Fusion and extruded it. I also carved out geometry in the Z axis mount.

**Total time spent: 4h 20m**

---

# Day 32 — 04.06.2026: TriTeron Robot Module (TRM) Progress — Part 11

Today, before I sat down to work on my project, I updated Fusion. After updating, when I opened my file, I saw that some of yesterday's progress was gone. I was quite astonished at the scene but had nothing to do.

Based on the experience of the previous day, I decided to go with the screw assembly. But here's what I did before the assembly:

1. I first went to Fusion Teams on Chrome, and then I deleted old files that were not necessary in the design. This makes sure that all my stuff is updated and old, unnecessary designs are excluded.

2. Then I went to model the washer again, just like yesterday. I first made a sketch, and then I extruded it with the correct dimensions, which I received from the [OnlyScrews data sheet](https://onlyscrews.in/products/m8-washer-ss304). I then duplicated it to a total of 28 screws using a rectangular pattern.

3. Next imported the [EDLP-S1-B-d8-L30 screw](https://jlcmc.com/product/s/E02/EDLP/iso-7379-gb-t-5281-hex-socket-shoulder-screw-(set-screw)?k=EDLP-S1-B-d8-L35&productModelNumber=EDLP-S1-B-d8-L35) which I had downloaded yesterday. I then duplicated it to a total of 12 screws using a rectangular pattern.

4. Then I looked for the nut for the screw. I chose this [EMLC-S1-N-M8](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M8&productModelNumber=EMLC-S1-N-M8) from yesterday and duplicated it to a total of 12 screws using a rectangular pattern.

Then I was about to enter into assembling.

1. I first added a rigid joint for the washer.
2. Then I added the screw.
3. Then I added the second washer.
4. Next, I added a rigid joint for the nut.

This is how it looked.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0dcea9fe-db0c-4654-aa25-50b81b9fa382" />

5. Using the Combine tool, I made a hole so that the nut can fit in the Z axis mount.
6. Made some extrusions using Sketch and added clearance for installing the nut.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/dc5c7303-ead8-401c-8cd4-355c339bbd26" />

But looking at the assembly, it seemed that the scews are not that sturdy, as not all faces that are supposed to be tight are making contact. The length of the thread and the extent of it is also concerning. But why was that so? It was because of the following reasons:

* There was a huge gap between the screw head and the smooth shoulder.
* The shoulder neck was narrow, which could've caused the washer to loosen.
* The thread length was shorter than the thread length of the nut.
* There was a concerning amount of gap and narrowing at the threaded neck

So I made the desicion of chaning the very shoulder screw for which I spent so long to assemble. I got no choice.

I started surfing JLCMC, and after looking at several configurations of screws, I could not find something desirable for the assembly.

But then I found this [MSB8-30](https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30) screw that seemed perfect for the assembly, since it had no narrow points and a decent thread length. I briefly went through the data sheet to give it approval.

<img width="900" height="1271" alt="image" src="https://github.com/user-attachments/assets/4344263f-def7-4784-a7aa-cfeb2aa381a7" />

But there was one problem. The length of the smooth shoulder was exactly 30 mm, which means that the washer-to-washer max distance was also supposed to be 30 mm for a perfect fit. The washer is 1.5 mm thick, and the 608 bearing is 7 mm thick. But currently, this was 1.5 + 7 + x + 7 + 1.5 = 32 mm, where X is the TriTreron leg's gap between the bearings, which was 15 mm. This meant that I had to reduce the X from both sides by 1 mm to make the total 30 mm.

Thus, I made the adjustments to all 24 bearing hubs in the legs, using extrusions and facial offsets. Then I deleted the old rigid joints of the bearings and reassembled them correctly.

This made sure that there is a 27 mm gap between the washers, and since the washers were 1.5 mm thick, the distance between the extreme faces of the wo washers is 30 mm.

This is how it looks now.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0470ebae-430b-425c-98ed-8ca5e5f1259c" />

The problem was fixed, and the screw was supposed to be a perfect fit.

I added a rigid joint for the first washer (after struggling to delete the pre-existing joint), and then for the second, and then the nut.

Yes, it was a perfect fit, and the fastening system was completed. But before I could proceed, time was over for today's session.

Here's the lapse of today's session: [PATRA-LPS-12-D32](https://lapse.hackclub.com/timelapse/0scjCOx6vKE7)

**Total time spent: 3h 30m**

---

# Day 33 — 05.06.2026: TriTeron Robot Module (TRM) Progress — Part 12

I proceeded exactly from where I left off yesterday. I started today's session by solving that very bottleneck that was lurking within the whole Triteron system's foundation, which was the nut fastening the whole system itself. The fastener was simply upside down, in simple terms.

So, I flipped it, causing chaos in the whole workspace; I don't know why. The sling simply affects each of the component's copies and changes their orientation upon any change made to one of the components. In this case, it was the nut.

To start fresh, I made some adjustments back in the timeline, causing the hole to delete itself. Then I did the following:

* Used a rigid joint to properly place the nut into position.
* Used the cut tool to re-establish the hole.
* Used Sketch to extrude out the right geometry to fix things.

I then proceeded to repeat the same assembly sequence involving the [MSB8-30 screw](https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30), M8 washers, and of course the [EMLC-S1-N-M8 nut](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M8&productModelNumber=EMLC-S1-N-M8), just like yesterday.

But then I noticed a terrible mechanical flaw. The threaded part of the [EMLC-S1-N-M8 nut](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M8&productModelNumber=EMLC-S1-N-M8) was 6 mm in diameter, which meant that it was supposed to be an M6 nut. I was using M8.

So, I went to JLCMC, corrected my configuration, and downloaded this [EMLC-S1-N-M6 nut](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M6&productModelNumber=EMLC-S1-N-M6), and imported it into my design.

I then adjusted the geometry of the Z Axis mount to perfectly house the M6 nut. I also made sure that there is no friction among the rotating parts. I then split the body of the mount and then mirrored the geometry.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/837e92ed-5d3f-47dd-b31c-2ef821414f03" />

Since I had worked quite a lot on my design, there was a high chance that I was potentially making a mistake. So, I consulted with Gemini and showed it my assembly, and it pointed out the issues, and I fixed them, and I was completely reassured of my design's sanity.

I can now copy this new logic to the other mounted joints (including the tool head) and complete the triteron, except for the double joints.

Here's the lapse of today's session: [PATRA-LPS-13-D33](https://lapse.hackclub.com/timelapse/1AzmvcisTlWN)

**Total time spent: 1h 50m**

---

# Day 34 — 06.06.2026: TriTeron Robot Module (TRM) Progress — Part 13

Before I could copy the fastening logic from yesterday, I had to name the fastening components logically so that everything makes sense and is easy to navigate.

For that, I decided to make two different fastening sets:

* Fastening Set S: Here "S" means single, and they are basically the joints connected to the mount and the tool head.
* Fastening Set D: Here "D" means double, and they are basically the elbow joints, which are the joints between the legs themselves.

I believed that this was okay for the time being, and I thought of coming up with a better name later on.

Then I proceeded to follow the exact naming sequence I had used for the Bearings, exactly where the Bearings existed. Here is the logic:

* "Fastener Set" is the core name for all the fastener sets that include either "Fastener Set S" or "Fastener Set D".
* Then it is followed by either "X", "Y", or "Z" depending on the axis.
* If it is "X," then it is followed by either "U" for upper, "L" for lower, or "UL" if it is the elbow joint that falls in between.
* If it is "Y," then it is followed by either "U" for upper, "L" for lower, or "UL" if it was the elbow joint that falls in between.
* If it is "Z," then it is followed by either "A" or "B", depending on the rail their lowest joints sit on. Then it is followed by either "U" for upper, "L" for lower, or "UL" if it is the elbow joint that falls in between.
* If the joint is single and I use "U" OR "L" as suffix, then I establish Fastener Set S as the child component.
* If the joint is double and I use "UL" as suffix, then I establish Fastener Set D as the child component.

There are the following numbers of both types of joints:

* There are 8 single joints.
* There are 4 double joints.

Note that this session only involves the single joints.

The next part was about completing the **Fastener Set S**. For that, I edited the [MSB8-30 screw](https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30) by adding threads and a nice appearance, and redefined the joints as an independent system. I made sure that the washer placement, nut placement, and both placements are interdependent in Fusion assembly and are unified as a Rigid Group.

Then I duplicated the **Fastener Set S** a total of 8 times using a rectangular pattern, and placed them inside the correct component one by one. A clean logic was then established.

Here's how the X axis fasteners were named:

<img width="357" height="510" alt="image" src="https://github.com/user-attachments/assets/d3dafbea-1688-4e54-94d3-1fda8e150912" />

Here's how the Y axis fasteners were named:

<img width="357" height="510" alt="image" src="https://github.com/user-attachments/assets/d02e9428-40ae-457e-83b9-c2e561bb8d59" />

Here's how the Z axis fasteners were named:

<img width="357" height="510" alt="image" src="https://github.com/user-attachments/assets/fec31666-7f32-4a52-8084-133a2707186d" />

Followed by this, it was time to establish the cuts for the nuts to go in for the other mounts and the tool head. But I noticed asymmetry in the placement of the Tool Head and saw that it was overlapping with one of the legs. I went back in the timeline and fixed the position.

But then again, the cut in the Z Axis Mount disappeared. This was probably my fourth or fifth time modelling this part. But since I knew what to do, I got over it quickly, mirrored the logic, and moved to the Tool Head.

I extruded out a body that followed the exact geometry of the hub for the nut and the screw's thread's end part, and named it "NUTCRAKER" because I didn't want it to disappear into the other Bodies, if I just kept the default name; and also because it is supposed to crack a hole for the nuts to go in, so I think this makes sense.

I aligned NUTCRACKER in the two of the hubs of the Tool Head, and used the Combine Cut tool to carve out the geometry.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/03eb6746-b47f-4576-9a36-a07aae84c1a4" />

Then I split the body and then mirrored it to make the geometry symmetrical.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e2122bb5-3d25-4f25-b764-fb98bf3840ba" />

Then it was time to work on the X and Y Axis Mounts, which have been floating since their very existence. I used NUTCRAKER this time to align with the last nut and create geometry, not cut. I first extruded a circular profile from inside the mounts. Then I created a sketch where I made a hexagon and added fillets; then I extruded it inwards and made it a separate part which I can assemble separately. I used NUTCRACKER to crack a hole just like the other ones. I mirrored the components and had them placed correctly. I named the extrusions "Extensions".

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/45fec21d-1e35-44f9-8ed6-1d156d20a948" />

Next, I moved on to working on the double joints, but I wondered how. I did some research and found that I had to use mechanical shims between the rotating components. I did not proceed as the time for today's session was over already.

But, anyways, here's what the tripteron looks like now:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c1db48ba-c4e4-4622-8c12-8fb6650436ea" />

Here's the lapse of today's session: [PATRA-LPS-14-D34](https://lapse.hackclub.com/timelapse/nWiG3ZvdcpSs)

**Total time spent: 4h 20m**

---

# Day 35 — 07.06.2026: TriTeron Robot Module (TRM) Progress — Part 14

I started by fixing all the minor problems from yesterday, which I had ignored knowingly or unknowingly.

So, what were the problems?

* The internal diameter of NUTCRACKER surrounding the thread was randomized at a 3.84 mm radius.
* The X and Y upper legs were rubbing against the tool head, with zero clearance. I had to make it 1 mm.
* The distance between the NUTCRACKER hole's deepest point and the surface was not seen consistent.

Here's what I did to fix them:

* Went back in the timeline to make the radius from 3.84 mm to 3.5 mm.
* I took out the extrusion from the axis mount.
* Then I named it FRICTIONKILLER; you know why.
* Then I made face offsets in the tool head holes.
* Mirrored the parts and used the Combine tool.
* Took measurements to see if everything is alright.

Here's what I ended up with:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ebd91876-da58-4df6-a788-8de189a43f8f" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/162c38a3-4bda-4a03-9bec-28a4b0007b97" />

Here's the lapse of today's session: [PATRA-LPS-15-D35](https://lapse.hackclub.com/timelapse/kdLlRkzxfTa4)

**Total time spent: 3h 25m**

---

# Day 36 — 08.06.2026: TriTeron Robot Module (TRM) Progress — Part 15

Today's session aimed at transitioning the progress from the tripteron to the robotic arm, by integrating the first axis (base) of the robotic arm in the Tool Head of the TriTeron. But I didn't know how to even het started with designing a robotic arm. So it seemed obvious to search the internet for guides.

But before I went on to explore the guides, I started by fixing some structural and mechanical errors that I noticed with the depth of NUTCRACKER; that was inconsistent for the Tool Head. To fix the problem I had to go back in the timeline and change some positions and alignments of the negative space that I modeled (NUTCRACKER).

Once that was fixed, I dived into the arm. But before I could model, I had to imagine, study, and understand the whole mechanism. Here's the content I explored in sequence:

- The very first website that I found was [this](https://robotsguide.com/robots/meca500), which had an interactive model that helped me understand the mechanism better.
	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/a3042287-d1a2-44e0-bd89-cf55a0944ef7" />
	
- Next I searched up and found [this](https://milvus.io/ai-quick-reference/what-is-a-robotic-arm-and-how-does-it-function) and briefly read it.
	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e0ee3393-9906-4adb-9f42-d196eadcc129" />
	
- I searched on Google how to make the first axis of a robotic arm, but didn't find any guide.

Just then I suddenly remembered that I already had the model of Meca500 sitting in my Fusion library. I thought of studying it in 3D space to understand it better. That's when the concept of harmonic drives appeared before me, which was really fascinating. I watched a YouTube tutorial for a minute and kind of understood what I had to do.

I then tried to cut a section and hollow the tool head to fit the base of the robotic arm inside the tool head. But then again, there were upstream timeline issues, especially because of accidental Capture Positions that caused the Tool Head to be asymmetrical and off-center. I tried my best to fix it by using split body and mirror tool.

But after the problem was fixed, today's session was over.

Here's the lapse of today's session: [PATRA-LPS-16-D36](https://lapse.hackclub.com/timelapse/1kYZRIteUWKL)

**Total time spent: 1h 25m**

---

# Day 37 — 16.06.2026: Research on the Robotic Arm & Journaling

Today's session was about the research for the robotic arm prior to its development. I have never built a 6 DoF robotic arm before. So, I had a lot to learn. I honestly had no idea how or where to start. I understood how a robotic arm worked, but to make it, I had to know piece by piece where everything goes.

On the last session, I did some research on a robotic arm and even started making changes to the tool head. But honestly, I was not sure of what to do. So, I decided to look at the assembly of a robotic arm, specifically the first axis, which is the base. I asked Gemini and Google AI to suggest how to do it, and I learned from sources available on the internet. I looked at the first joint of the Mecademic Meca500 as well. 

I found this very helpful image that helped me understand what's actually inside a robotic arm, especially the J1 axis.

<img width="601" height="465" alt="image" src="https://github.com/user-attachments/assets/00982bd2-8e66-4112-83e7-e920fb8a0f73" />

This is when I came across reduction gears and their types, like harmonic drives (strain wave gears), cycloidal drives, and planetary gears. As I came across those terms, I read about them and found out that even a small 1:100 ratio harmonic reducer easily costs above $1000. This completely obliterated my $500 budget. I had no way to create a robotic arm with repeatability even as near as the Meca500, which costs nearly $17,000.

That's when I told Gemini that my budget was $500. It suggested studying open-source projects like Chris Annin's AR3/AR4, and using 3D-printed reducers. I visited [this](https://anninrobotics.com/?srsltid=AU7gw4WvadCKGb7SmFR21GSa32zT4K--aYFWro0ZE4hX9_rZg5PPhz1U) site and looked at the numbers and realised that this costs nearly $2000, which is four times my budget. I also visited [the repo](https://github.com/Annin-Robotics/ar4_ros_driver). 

<img width="1366" height="767" alt="image" src="https://github.com/user-attachments/assets/f9291aa8-7843-4582-bd6e-bec5cd72e4bf" />

Of course, I was not looking forward to buying it, but since it is an open-source project, I expected the cost to represent the actual price of making it. With customs on parts, it seemed like the cost for the arm could reach over $2800. I needed to choose a motor for the first axis. I decided to choose the equivalent of the [J1 motor 17HS15-1684D-EG10-AR4](https://www.omc-stepperonline.com/nema-17-stepper-motor-with-high-precision-gearbox-gear-ratio-10-1-magnetic-encoder-1000ppr-4000cpr-17hs15-1684d-eg10-ar4) used in the AR4. But I didn't find any equivalent that could at least give me a cost with customs included or without any. I also looked at [PAROL6](https://github.com/Source-Robotics/PAROL6-Desktop-robot-arm), which costs from $1500 for DIY parts to beyond $4200 for a fully assembled unit from [Source Robotics](https://source-robotics.com/). 

Then, without thinking too much about the cost, I decided to actually start building. So, I imported a NEMA 23 of length 76 mm and created a new design in Fusion for the robotic arm. For the harmonic reducer, I was thinking of 3D printing it. I found [this](https://cults3d.com/en/3d-model/tool/3d-printed-nema-23-strain-wave-gear-harmonic-drive?srsltid=AU7gw4Vz6yzDp2YuxYMDzJequ8GJrG8rhCzQnUTZiu4mZjdzcvdn7gwb) model that I can print for NEMA 23. But then suddenly I realised that it was a lot better to visualize how a harmonic drive works before actually working on it. I not only watched a YouTube but I also read about it in Wikipedia.

But even after all that, I felt like I knew nothing. So, I asked Gemini to make a plan for me. I never read it.

I also journaled day #21 (partly)

Day #21

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/90342024-8061-48ab-89eb-2856495c4808" />

Here are the lapses of today's session: [PATRA-LPS-17-D37-1](https://lapse.hackclub.com/timelapse/zAi2jDNiKqpI) and [PATRA-LPS-17-D37-2](https://lapse.hackclub.com/timelapse/Pgd6fTYl6KDr)

**Total time spent: 3h 15m**

---

# Day 38 — 17.06.2026: Journaling

Journaled days #21 and #22 (partly).

Day #21

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b225f8c6-459e-4f4f-8119-5c0102d72b99" />

Day #22

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/893e5a43-5e4a-4e2a-a2cb-27a4de5a7599" />

Here's the lapse of today's session: [PATRA-LPS-18-D38](https://lapse.hackclub.com/timelapse/6Sx4q91ksQql)

**Total time spent: 3h 00m**

---

# Day 39 — 18.06.2026: Journaling

Journaled the days #22 (full), #23, #24, #25 (partly), and #26 (partly).

Day #22

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6cde43d5-46a1-423a-b3e4-3a570bd38a49" />

Day #23

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/da957ffe-f0e9-4b27-bb77-de02ad8ddcc6" />

Day #24

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5cab2b1c-b6e3-4cd2-b64d-f16a70fe80ab" />

Day #25 (partly)

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b8af7074-8278-4a82-9223-4ac7f6d5f827" />

Day #26 (partly)

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c04849e2-8456-40a7-afae-205e38184f2c" />

Here are the lapses of today's session: [PATRA-LPS-19-D39-1](https://lapse.hackclub.com/timelapse/UA4UIbZiE68q), [PATRA-LPS-19-D39-2](https://lapse.hackclub.com/timelapse/aaIH03558pYh) and [PATRA-LPS-19-D39-3](https://lapse.hackclub.com/timelapse/iAgCZrQ8vZWJ)

**Total time spent: 3h 45m**

---

# Day 40 — 20.06.2026: Journaling

Journaled days #25, #26, #27, #28, and #29.

Day #25 (full)

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ecab4f52-651e-4555-a02d-88b7f0ed3c90" />

Day #26 (full)

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/27905278-d41a-458b-822c-bed72ad944e9" />

Day #27

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/769711db-570e-4386-af94-143d016dbf96" />

Day #28

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2a412fc5-98af-4c03-bd14-59c75bf7b070" />

Day #29 (partly)

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/3aaa10ea-08b0-47b0-953b-8739f1efd238" />

Here's the lapse of today's session: [PATRA-LPS-20-D40](https://lapse.hackclub.com/timelapse/s45U_LOytKdj)

**Total time spent: 3h 15m**

---

# Day 41 — 22.06.2026: Journaling

Journaled day #29

Day #29 (partly)

<img width="1365" height="731" alt="image" src="https://github.com/user-attachments/assets/4b1becd9-5eeb-44b8-8a35-9a9120d000ac" />

Here's the lapse of today's session: [PATRA-LPS-21-D41](https://lapse.hackclub.com/timelapse/CF6H7YTcu3rX)

**Total time spent: 0h 30m**

---

# Day 42 — 18.07.2026: Fixing the Broken Dimensions of the TriTeron Robot Module (TRM)

Throughout the design, there were broken dimensions. There were asymmetrical bodies, off-center midpoints, asymmetrical angles, and off-center components. I was not aware of the asymmetries in existence in the design, so I had decided to fix every dimension one by one as I discover them in real time.

1. **Asymmetrical Tool Head:** The first one I fixed was the Tool Head, which had asymmetrical dimensions and an off-center position. The width of the Tool Head was supposed to be 100 mm, but it was actually 100.09016915 mm. This made the body asymmetrical and had the potential for various issues in the future for downstream features, sketches, and modifications. In order to fix this, I first split the Tool Head body into two parts using the XZ plane as the splitting tool. Then I extruded the bigger side by the dimension, which was the average of their asymmetry, and moved the wider and thinner side to reach the XZ plane at exact coordinates. Then finally I combined them and adjusted the bodies in the Browser. This was most likely caused by accidental upstream Capture Positions after having dragged them out of position accidentally.  

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5f19d21e-3ccd-4697-8760-e6ba84fcf4d2" />
		
2. **Asymmetrical Distance between X and Y Upper Legs and Tool Head Flat Face:** Next was the distance between the Y Upper Leg and the Tool Head lower left back face. It was supposed to be exactly 1 mm, but in the design the distance is 0.93620373 mm, unlike the X Upper Leg, which had an exact 1 mm distance. To fix this, I went back in the timeline and tried to find at what point the distances were disrupted. I found the Position Capture feature, but it caused various Errors and Warnings downstream (of course). After deleting several different Capture Positions and seeing what they do, I found the culprit and fixed the problem. But even after finding the culprit, it wasn't going to solve the problem, so I decided to fix one side of the problem, which means deleting the X axis legs and duplicating the Y axis legs using the Mirror Tool to mimic the correct distance, making the whole system symmetrical. I had only deleted the X axis legs, not their joints, but I was not going to use them because the joints were not in the right position. I had to find a way to work with those and position them correctly. For that, I first removed the joints and then used joints manually to position them correctly with the mirrored legs. 

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/265e7d62-c907-48f8-8384-6bba19f9d5dc" />

3. **Off-center Distal Joints in X and Y Legs:** While working with the asymmetrical distance between the X and Y upper legs of the toolhead flat face, I noticed that the connection between the upper and lower parts of the X and Y legs was off-center. In order to fix this problem, I went back in the timeline to check when exactly it happened. When I was unsuccessful in finding out when it happened, I took the present design and then removed some joints in the lower part of the leg and X and Y axis Mount. After that, I added new joints between the parts where the problem was, and then I continued adding the joints that I had removed. 

	<img width="1364" height="733" alt="image" src="https://github.com/user-attachments/assets/a1176344-0d3b-45de-b892-72fd23411512" />

4. **Horizontal Asymmetry in the position of the X and Y Axis Mounts:** When I was fixing the opt center distal joints, in that part, there was another problem that came up, which was the asymmetrical positioning of the X and Y mounts. To fix this problem, I first tried moving it and then seeing how it affects the position of the overall TriTeron. I tried locking some parts of the TriTeron down so that only the parts that were asymmetrical would move, but it did not work. I even tried changing the angles between the joints of the TriTeron, but it did not work. After that, I used part of the solution to the first problem and the second problem, which was mirroring the correct part and deleting the old part, and then having everything fixed. 

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ecbb1d55-116f-460a-aa91-e5334fb5176a" />

5. **Asymmetrical Distance between the Two Vertical Ends of the NUTCRACKER Negative Body:** The distance between the two ends of the negative body is supposed to be exactly 9.5 mm, but I noticed that instead the distance was 9.501 mm. It felt like I could just reduce the distance by 0.001 mm, but the problem was deeper than that. The distance between the two ends of the nut itself was supposed to be 6 mm, but it was 6.001 mm, so I had to fix this. I did this by moving the faces. I had also tried to alter the geometry of the NUTCRACKER itself by going back in the timeline, but it did not work well. Also, there were unnecessary splits in the hole, which I fixed by deleting them in the Tool Head. 

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a72e7a24-f4d2-45f7-9934-36e1a29cae47" />

These five problems might seem quite small and insignificant to solve because they were only visual problems that didn't even bother to get noticed by our eyes in themselves (without actually scrolling inside and seeing the positions themselves and actually looking at the nanoscopic coordinates of the part). The reason why I fixed this was that I wanted my design to be completely flawless, to make sure no timeline errors occur in the future.

At the same time, the problems might seem quite simple as well to solve, but let me tell you, all of these five problems were solved more than once. In the process, I faced a lot of issues, and I had to repeat things and solve all the problems not separately but together. And every single time it felt like everything was falling apart, but I still managed to fix most of the things that I could manage to notice.

By the end of the day, this is how the design looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0c7d347d-5a53-4090-8d1a-cdf71db3ba13" />

Here's the lapse of today's session: [PATRA-LPS-22-D42](https://lapse.hackclub.com/timelapse/DzR0y5DWGWK2)

**Total time spent: 5h 30m**

---

# Day 43 — 01.08.2026: Making Major Decisions after Long Time No See

Today was the day I decided to visit my age-old pending project and work on it just to escape late-night **Zeigarnik effects**, as my Internal Assessment Exams were over. I had decided to first complete my other projects, and then continue this project non-stop, but I couldn't. So here I am.

Anyways, today I am noting down some of the big decisions I have made in my mind after the last working day:

1. **Fabricating the KBM & TRM:** I have decided to complete designing, simulating, and finalizing the KBM (Kinematic Base Module) and the TRM (TriTeron Robot Module) before I start modelling the RAM (Robotic Arm Module). After doing that, I will submit the project and fabricate the parts. This is because I don't have enough time left before Forge ends, and more importantly, my exams begin, which I should be concerned about. One other reason is that I want to be cautious about what I am building. If I build those two parts first, I will have a reality check before modelling the robotic arm, as I will understand the PATRA, which is in my CAD right now, better.

2. **Tool Head Modularity:** The decision in the first point raises an obvious question: How will I mount the robotic arm after completion then? To this, I have planned to use two different Tool Heads: One smooth-top-faced tool head will support just the TriTeron and not the arm; and the other will be for supporting the joint of the robotic arm, which I will model later on after designing, fabrication, and testing. In both of them, the lower part will be the same, with the change only showing in the upper face. This allows modularity, which means I can use either as per my needs. For testing and operation of the TriTeron solely, the flat head is enough. For the 6 DOF arm, the other one should be fine. This most importantly gives me enough room to think and also save time in the long run.

3. **Stepper Motor Adjustments:** First let's review the stepper motor configuration which was decided earlier: Two [NEMA23 PR57HS76-2804-05 18.9kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft) for each X & Y axes and one [NEMA23 PR57HS112-4204-01 31kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs112-4204-01-31kg-cm-stepper-motor-round-type-shaft/) for the Z axis. I then momentarily decided to go for all three [NEMA23 PR57HS112-4204-01 31kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs112-4204-01-31kg-cm-stepper-motor-round-type-shaft/) without thinking much about anything but the torque. But today, I did some research and then I decided to use closed-loop stepper motors for my system, even if it meant losing torque. I have made the decision of using Two [Rtelligent 57AM23ED 2.3 Nm Closed-loop Stepper Motor](https://robu.in/product/rtelligent-57am23ed-closed-loop-stepper-servo-motor/) for each X & Y axes and one [Rtelligent 57AM30ED 3 Nm Closed-loop Stepper Motor](https://robu.in/product/rtelligent-57am30ed-closed-loop-stepper-servo-motor/) for the Z axis. This increases the cost but ensures more precise movements.

I also decided to go through the entire process of revising the Kinematic Base Module (KBM) and model whatever is left. I knew there were a lot of things left.

The very first thing I did was study a real linear actuator's inside, because till date I was not sure how to create the tensioning system. All of the parts were just floating in the air. Looking thoroughly at the [Linear Unit GSF 8 40 R10](https://www.traceparts.com/en/product/item-industrietechnik-gmbh-linear-unit-gsf-8-40-r10?CatalogPath=ITEM%3A1001374067&Product=30-12112020-084688) opened my eyes like never before. I thoroughly studied the pulley/idler part and how it is held in position. Before today's session, I had also watched some videos about assembly of linear actuators. Both combined taught me how to make my own. I also tried to copy and model the coupler, as there was no reliable system to connect the pulley/idler case to the 4040 and 2020 extrusions.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/01b9ce06-7ac6-4cb3-ab21-0d0d49e6ee0a" />

Next, I also found the closed-loop Stepper Servo models from Traceparts:
- [Rtelligent 57AM23ED](https://www.traceparts.com/en/product/shenzhen-rtelligent-technology-coltd-stepping-servo-motor-57am23ed?CatalogPath=TRACEPARTS%3ATP09005002005002&Product=90-21102022-022115&PartNumber=57AM23ED) for the X and Y axis.
- [Rtelligent 57AM30ED](https://www.traceparts.com/en/product/shenzhen-rtelligent-technology-coltd-stepping-servo-motor-57am30ed?CatalogPath=SHENZHEN_317938087%3ARTELLIGENT.010.040&Product=90-21102022-022125&PartNumber=57AM30ED) for the Z axis.

Here's the lapse of today's session: [PATRA-LPS-23-D43](https://lapse.hackclub.com/timelapse/bNyyjAI7nMCC)

**Total time spent: 3h 10m**

---

# Day 44 — 02.08.2026: Working on the Z Axis Tensioning System

The previous session involved making major decisions involving the Kinematic Base Module (KBM). This session involves major changes specifically for the **Z Axis Tensioning System**, by making a deep dive specifically confirm all the parts of this system, which some minor but important changes to the X and Y Axis Tensioning System.

The very first thing I did was downloading the the [Rtelligent 57AM23ED](https://www.traceparts.com/en/product/shenzhen-rtelligent-technology-coltd-stepping-servo-motor-57am23ed?CatalogPath=TRACEPARTS%3ATP09005002005002&Product=90-21102022-022115&PartNumber=57AM23ED) for the X and Y axis, and [Rtelligent 57AM30ED](https://www.traceparts.com/en/product/shenzhen-rtelligent-technology-coltd-stepping-servo-motor-57am30ed?CatalogPath=SHENZHEN_317938087%3ARTELLIGENT.010.040&Product=90-21102022-022125&PartNumber=57AM30ED) for the Z axis. Then I imported them, placed them inside the design with the correct orientation, and added appearance. 

The next thing I did was, revising my decision about changing the X and Y axis motors from [NEMA23 PR57HS76-2804-05 18.9kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft) to [Rtelligent 57AM23ED](https://www.traceparts.com/en/product/shenzhen-rtelligent-technology-coltd-stepping-servo-motor-57am23ed?CatalogPath=TRACEPARTS%3ATP09005002005002&Product=90-21102022-022115&PartNumber=57AM23ED) and changing the Z axis motor from [NEMA23 PR57HS112-4204-01 31kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs112-4204-01-31kg-cm-stepper-motor-round-type-shaft/) to [Rtelligent 57AM30ED](https://www.traceparts.com/en/product/shenzhen-rtelligent-technology-coltd-stepping-servo-motor-57am30ed?CatalogPath=SHENZHEN_317938087%3ARTELLIGENT.010.040&Product=90-21102022-022125&PartNumber=57AM30ED). I knew that the former ones are open-loop and the newer ones are closed-loop, which some better holding torque. I also went through the linear guides section of [this](https://www.hepcomotion.in/wp-content/uploads/2023/03/Hepco-FPL-Linear-Actuators-01-UK_Web.pdf) product catalogue.

Previously, I had noticed that the X and Y (probably Z as well) axis clamps need more teeth grooves to grip onto the belt. There were 8 teeth on a single clamp. I increased that to 10 by adding one on both sides. After making changes to the X and Y clamps, I also fixed the Z axis clamp.

With the length of the clamp increased, this is how it looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0b4faccc-fc3b-460b-bcff-1b71eebf8d0e" />

And this is how it looks from under:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/65aebca3-7c3d-40bd-8b3c-14c42c3d984b" />

Next, I decided to choose the drivers for the motors. After searching and going through [this](https://www.rtelligentglobal.com/uploads/Rtelligent-T42ST60ST86S-Closed-Loop-Stepper-Driver-User-Manual-V4.1.pdf) datasheet and [this](https://rtelligentglobal.com/uploads/RTELLIGENT-STEPPER-PRODUCT-CATALOGUE-2024V1.0.pdf) product catalogue, I found that I had two options:

- [Rtelligent T60](https://robu.in/product/rtelligent-t60-closed-loop-stepper-driver-18-68vdc-6a-for-stepper-motors-below-nema-24/): more expensive, standard generation, looks rubbish green.
- [Rtelligent T60S](https://robu.in/product/rtelligent-t60s-closed-loop-stepper-driver/): cheaper, upgraded generation, looks fantastic black.

The choice was obvious. I chose the second one. But I knew this may change, as the design was not yet finalized. 

<img width="975" height="688" alt="image" src="https://github.com/user-attachments/assets/229f4a75-f8de-41e4-a5f0-61f43c59842a" />

With the drivers chosen, I updated the BOM:

| Component Category          | Item                                                             | Quantity | Cost     | Total Cost | Side Note | Link                                                                                                                                       |
|-----------------------------|------------------------------------------------------------------|----------|----------|------------|-----------|--------------------------------------------------------------------------------------------------------------------------------------------|
| Kinematic Base Module (KBM) | Aluminium 2020 T-Slot Profile Extrusion — 1 metre LCF6-2020-1000 | 1        |  $2.82   |  $2.82     |           | https://in.misumi-ec.com/vona2/detail/110311047509?HissuCode=LCF6-2020-1000                                                                |
|                             | Aluminium 4040 T-Slot Profile Extrusion — 1 metre LCF8-4040-1000 | 2        |  $8.78   |  $17.56    |           | https://in.misumi-ec.com/vona2/detail/110310647549?HissuCode=LCF8-4040-1000                                                                |
|                             | MGN15H Linear Guide Rail — 1 metre                               | 2        |  $21.64  |  $43.28    |           | https://robu.in/product/mgn15h-linear-guide-rail-1m-2                                                                                      |
|                             | Rtelligent 57AM23ED 2.3 Nm Closed-loop Stepper Motor (X & Y)     | 2        |  $40.74  |  $81.48    |           | https://robu.in/product/rtelligent-57am23ed-closed-loop-stepper-servo-motor/                                                               |
|                             | Rtelligent 57AM30ED 3 Nm Closed-loop Stepper Motor (Z)           | 1        |  $53.95  |  $53.95    |           | https://robu.in/product/rtelligent-57am30ed-closed-loop-stepper-servo-motor/                                                               |
|                             | MGN15H Sliding Block                                             | 4        |  $7.18   |  $28.72    |           | https://robu.in/product/sliding-block-for-mgn15h-linear-guide-rail                                                                         |
|                             | Pulley CBYL-AH1-5GT150-32-A-N-d22 (X & Y)                        | 2        |  $3.39   |  $6.78     |           | https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-32-A-N-d22&productModelNumber=CBYL-AH1-5GT150-32-A-N-d22 |
|                             | Idler CBYL-AH1-5GT150-32-A-H-d22 (X & Y)                         | 2        |  $2.91   |  $5.81     |           | https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-32-A-H-d22&productModelNumber=CBYL-AH1-5GT150-32-A-H-d22 |
|                             | Belt E-GBN23005GT-150 (X & Y)                                    | 2        |  $12.94  |  $25.88    |           | https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN23005GT-150                                                              |
|                             | Pulley CBYL-AH1-5GT150-20-A-N-d12 (Z)                            | 1        |  $2.57   |  $2.57     |           | https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12 |
|                             | Idler CBYL-AH1-5GT150-18-A-H-d16 (Z)                             | 1        |  $1.98   |  $1.98     |           | https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d16&productModelNumber=CBYL-AH1-5GT150-18-A-H-d16 |
|                             | Belt E-GBN26005GT-150 (Z)                                        | 1        |  $14.54  |  $14.54    |           | https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN26005GT-150                                                              |
|                             | Rtelligent T60S Closed-loop Stepper Motor Driver (X, Y & Z)      | 3        |  $35.48  |  $106.44   |           | https://robu.in/product/rtelligent-t60s-closed-loop-stepper-driver/                                                                        |
|                             |                                                                  |          |          |            |           |                                                                                                                                            |
|                             |                                                                  |          |          |            |           |                                                                                                                                            |
|                             |                                                                  |          |          |            |           |                                                                                                                                            |
|                             | Total                                                            |          |          |  $391.81   |           |                                                                                                                                            |

Updated BOM:

<img width="2559" height="282" alt="image" src="https://github.com/user-attachments/assets/1e14cbf6-ea91-434d-b14a-fcc6ad5999b1" />

Then, I modelled the shaft adapter of the motor, making sure the inner dimensions and shape match those of the motor shaft and the outer dimensions match the inner dimensions and shape of the pulleys and idlers.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a00e0baf-b493-455b-9580-5af2e81eac26" />

The next important thing was the motor assembly. Here's what I had versus what I had to achieve:

- **What I had**: I had nothing but pulleys and idlers floating in air, while in contact with the motors, with an 8 mm D-type to 12 mm N-type shaft adapter, asymmetrically.

- **What I had to achieve**: I had to find a way for the linear actuator to rotate on its own without the motor, if the linear blocks are manually moved. This meant that the belt could not rely on the tension of the pulley attached to it alone. I had to make a system where I could attach the motor to the system flawlessly by just fastening four screws. The system I described is a backdrivable, motor-ready, belt-driven linear actuator (or linear stage), exactly like the **Zaber LC40 Series** (specifically the belt-driven LC40B or LC40C models).

In order to achieve what I had to, I started first by rewatching what Rowan did in his tripteron, then I looked at the **LC40B1000** model which I had downloaded from Zaber earlier and **[Linear Unit GSF 8 40 R10](https://www.item24.com/en-au/linear-unit-gsf-8-40-r10-65598)** from Item24, for reference.

Then I had the idea to use pillow block bearings and attach them to the pulley/idler case walls to prevent the pulleys and idlers from floating mid-air. The bore had to be 12 mm in diameter as the outer diameterof the shaft was also 12 mm. I found [this](https://onlyscrews.in/products/kp001-inner-ball-mounted-pillow-block-insert-bearing-for-12mm-bore?utm_source=google&utm_medium=cpc&utm_campaign=Inderans_Campaign&utm_content=Other_than_fasteners_wala_copy&gad_source=1&gad_campaignid=22618541726&gbraid=0AAAAA9sP2STGNk4475GGc6HGnFMyoe5DE&gclid=CjwKCAjwoaLWBhAWEiwAnyitu1tXe_g3XHX9j7ufCCIsJ6hT4KSTcsjvFpZr54QvpEv6aLgnsiW7LxoCpXMQAvD_BwE) on OnlyScrews. 

But it didn't seem that good, and was expensive for a bearing where I could attempt to use regular ball bearings, and not pillow block ones. So, I looked for regular ball bearings in McMASTER-CARR, inside Autodesk Fusion. I found out that I can use [6001 bearings](https://onlyscrews.in/products/6001-2rs-rubber-sealed-ball-bearing-12x28x8?currency=INR&country=IN&variant=50982218662201&stkn=6e84ebfba1b8&utm_source=google&utm_medium=cpc&utm_campaign=inderans_campaign&gad_source=1&gad_campaignid=22229905346&gbraid=0AAAAA9sP2SRD-kNwjXRWwyYJwLecjvJ7G&gclid=CjwKCAjw1bvTBhBbEiwAzbP8L88XPdembQI0erqY38rix0JGeQduw_Pal1aXQlCeZCx5qRt33s1SbhoCfLoQAvD_BwE) for this, which I found on OnlyScrews.

Here's what I did next:

1. I changed the design of the pulley case to resemble the pulley case of the **Linear Unit GSF 8 40 R10**.
	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/5c09407f-d60e-4b9d-92b7-892f7e67126b" />

2. I attached the 6001 bearings along the pulley and on the extended shaft adapter. And 
	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/85d16270-7165-4503-b313-77badff3bb57" />

3. I also added walls, making sure that only the outer race of the bearings touch the walls, and the inner race doesn't rub against it. 
	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/5985cb6a-a973-4f57-9891-573d01b3ea47" />

4. Next I searched for washers in OnlyScrews and MISUMI. I needed washers with inner diameter about 13 mm, and exact thickness of 2.5 mm. There will be two washers. In MISUMI I found [WSI-SUS-M12](https://in.misumi-ec.com/vona2/detail/221000551972?HissuCode=WSI-SUS-M12), with the perfect dimensions. [This](https://github.com/user-attachments/assets/52bb06ad-70c7-4b37-b142-b6190bdb8bb7) is the datasheet.

5. The 2.5 mm thick washers were too thick to fit between the bearings and pulleys. So, I had to find thinner ones.

I then asked Google AI about my design. It said that the fact that the motor shaft hardly reaches the middle of the adapter, is a major bottleneck. To fix it I might had to use keyed adapters or shaft couplers to extend the shaft and then use the adapter.

Here's the lapse of today's session: [PATRA-LPS-24-D44](https://lapse.hackclub.com/timelapse/VxiPyruOoxIk)

**Total time spent: 7h 20m**

---

# Day 45 — 03.08.2026: Searching for Shaft Adapters & Shaft Couplers

Today's agenda was to find the right coupler or adapter or whatever, and complete the motor part of the tensioning system as soon as possible.

Previously, I came to know that I had to use shaft couplers to extend the motor's shaft. But I wanted to use something like [this](https://www.amazon.in/Stepper-Adapter-Turbine-Reducer-0-31inch/dp/B09G6GW7XF) instead. This example shown is extremely overpriced, so I tried finding something similar in MISUMI and JLCMC.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/92820174-260d-4fe5-b833-8819a7745fce" />

I looked at different linear actuators, as I was confused about what to do. I couldn't reliably connect the motor to the pulley, as the motor's shaft is too short. But to extend it, I have to use couplers or adapters. But I didn't find any such actuator. Most of them have the adapter integrated into their design. I searched, asked AI, read datasheets, surfed for products that could potentially match, but I couldn't find what I was expecting. Maybe I was just not sure enough of what I wanted to even achieve.

But after this, my brain was introduced to the world of shaft couplers, where each coupler is rated for a specific speed range (rpm), torque range, rigidity/flexibility, and, of course, a specific size and material for so many different applications. This ocean of choices added more to my preexisting confusion. But during the probably aimless surfing, here are the notable things I have found:

1. Found [this](https://robu.in/product/flexible-coupling-enclasp-metel-bellow-coupling-od25mm-x-l32mm-bore8x8mm-zrb-25x32/) in Robu.in. Can't use; max torque rating is too low (1.5 Nm)

	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f86d1014-2d7b-462f-9e45-ad8e4d2042a4" />

3. Found [this](https://jlcmc.com/product/s/C01/CXJL/stainless-steel-high-rigidity-parallel-cut-beam-coupling-screw-fixing-screw-clamping-type) in JLCMC.

	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/edb453f6-491e-43dd-aa6c-28c978d893b3" />

4. Found [this](https://in.misumi-ec.com/vona2/detail/110310701009/?KWSearch=coupling&searchFlow=results2products&list=PageSearchResult) in MISUMI for 2.3 and 3 Nm motors.

	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/000a9fd2-a8cd-4702-aafc-cc3ce3ef63f2" />

After all that crazy searching, I had had enough. I asked MISUMI AI to do the job for me. And I found out that it is crazy good. It completely obliterated my endless searching by finding exactly what I was looking for, as cheaply as possible. What I searched for hours, it found in seconds. It found [this](https://in.misumi-ec.com/vona2/detail/110310702179/?HissuCode=E-LMCPSS34-8-10) for both 3 Nm and 2.3 Nm motors.

This session achieved something very little, but was not less hard worked than most others. But it indeed was more frustrating than most of the sessions till date.

Here's the lapse of today's session: [PATRA-LPS-25-D45](https://lapse.hackclub.com/timelapse/3knULGqZZzTa)

**Total time spent: 4h 35m**

---

# Day 46 — 04.08.2026: Working on Z Tensioning System Pulley Case — Part 1

The hunt for shaft couplers continues. I came across several promising candidates for the coupler, but in the end, I couldn't settle on any.

I found [this](https://in.misumi-ec.com/vona2/detail/110310701639?HissuCode=E-LMPO40L32-8-10) in MISUMI but I couldn't think of any way how and where I could place it in the KBM. It was way too large.

This is how the design was. There was this bearing and the coupler.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1fc6b16c-b004-4e69-a8d4-8bff42b8c651" />

And the pulley goes here.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4b8ae59b-f3b1-4c51-8929-9c783716e44f" />

So, I thought of looking at linear guides with STEP files, to see how they deal with the problems I was facing. I found out that they don't use couplers, and if they do, the motor is placed further behind. Here are the linear guides I explored:

1. Found [this](https://jlcmc.com/product/s/B18/BNQ-JHB8/guide-rail-embedded-linear-actuator-base-width-82mm) on JLCMC.
2. Found [this](https://in.misumi-ec.com/vona2/detail/110310701639/) on MISUMI
3. Found [this](https://jlcmc.com/product/s/B18/BNQ-JHB8/guide-rail-embedded-linear-actuator-base-width-82mm?_t=1785849904834&spm=overseas-fa-pc.homepage.hint.1&up_spm=Jlcpcb.Loginpage.1003) on JLCMC.

I imported the [E-LMPO40L32-8-10](https://in.misumi-ec.com/vona2/detail/110310701639?HissuCode=E-LMPO40L32-8-10) into Fusion to see if I could place it somewhere.

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/8e05b063-8c3d-4471-939c-ae0fbb7c6550" />

But it was way too big to be placed anywhere without making major changes to the KBM, which I didn't want. I knew for sure that I needed a say to connect the motor's what to the highlighted part.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8507844b-2ef7-45e4-b34a-4bf21bb1d017" />

So, I decided to instead use Combine cut to use the geometry of the motor shaft. I could fabricate my own shaft as I couldn't find one. This is the cross-section view of the plan I executed.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/cb5713ef-7846-4b98-a249-dd2ae959803e" />

I needed to use thinner washers to make that design successful. I found [this](https://in.misumi-ec.com/vona2/detail/221004999084/?CategorySpec=00000230674%3A%3Amig00000001861896%2C%0900000230734%3A%3Amig00000001861547%2C%0900000230786%3A%3Amig00000001826448%2C&list=PageCategory) washer which is 0.5 mm thick, but this is quite expensive.

Then I also started modelling the Z axis pulley/idler case. Here's what I did:

- First I changed the appearance to Metal Flake (Black)

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d4d981a3-c103-4be2-a62a-5b9b10f5b5a5" />

- Then I closed all of the holes.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b8b1653d-e35c-4a7a-884e-cb847bba3cf0" />

- Next I created this sketch to check the motor alignment and create a shape similar to the pulley case of [this](https://www.traceparts.com/en/product/item-industrietechnik-gmbh-linear-unit-gsf-8-40-r10?CatalogPath=ITEM%3A1001374067&Product=30-12112020-084688) linear actuator.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ec1ed255-c311-4e9c-8e39-f2b649a92308" />

- Then I extruded the shape.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/83a9c335-4a2b-4443-b08c-f207ddff22b2" />

- Next I created this sketch, to fill up more space inside the case keeping the belt path clear.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5291591c-374c-4e23-a073-ad089ab1d8bb" />

- This is how it looks after extrusion.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f4946677-4834-4563-b1ce-bfe6f74644b8" />

- Next, I modeled the washers and carved out a section for the coupler.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6bf57ad9-e4bc-4bbd-83c3-bfc97622edb7" />

- Made some chamfers to make sure that the belt doesn't wear out.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/36f7205b-c20b-48dc-bc0b-da4ca06897b1" />

As I was feeling burned out trying to fix things, I decided to play my role as a materials engineer instead of a mechanical engineer. Specifically, I saw what material I could print my pulley/idler case with. After a bit of research, the best candidate that appeared was MJF PA12S-HP Nylon, from JLC3DP. But it was more expensive than resin printing in JLC3DP, and vastly more expensive than normal FDM printing with PLA/PETG. I read [this](https://05d34394-ee75-421b-b25c-2692ee29c572.filesusr.com/ugd/8e7ac9_372f34ece2a0447382c6164aafcd4157.pdf) data sheet for more information.

When searching things, I came across this](https://www.linearmotiontips.com/belt-driven-actuators-for-a-wide-range-of-applications/) article about applications of belt-driven linear actuators. Should I use an Omega shape to clamp my Z axis belt at the Z axis clamp?

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0b625564-ec6a-498b-89fb-23e91746da52" />

But what they have done here is different, actually.

<img width="446" height="442" alt="image" src="https://github.com/user-attachments/assets/d623e70a-64cd-409d-a40f-5bc30a5736db" />

I also read about the differences between belt-driven and pinion-driven linear actuators, [here](https://www.linearmotiontips.com/linear-actuators-belt-driven-vs-rack-and-pinion-driven/).

Here's the lapse of today's session: [PATRA-LPS-26-D46](https://lapse.hackclub.com/timelapse/grXv6KJjtiJW)

**Total time spent: 5h 15m**

---

# Day 47 — 05.08.2026: Working on Z Tensioning System Pulley Case — Part 2

I started by validating the design that I created the day before. When that was done, the next thing I had to worry about was the belt return path, especially the X and Y belt return paths. This is what the current belt return path looks like:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/361fc7d5-4c85-46fd-a16f-1ec04ccbb204" />

I really needed a workaround, as there was a high possibility of belt wear because there was not much space for the belt. The belt was supposed to travel 1000 mm inside the aluminum extrusions. That's when I considered my 4040 extrusion choices. That's when I came across [this](https://in.misumi-ec.com/vona2/detail/110302684350/?KWSearch=aluminium%20extrusions&searchFlow=results2products&list=PageSearchResult) extrusion from MISUMI, which could provide a proper return path for the belt.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e36a5e1c-e824-4ac7-b98d-dd3aed8b4998" />

But one more option that appeared was using UHMW tape on the surface where the belt could rub against. This made sure I didn't change the extrusion and end up spending way more. But looking at the prices of the tape made me realize that either way I have to spend a lot of money on this.

Moving aside from the decision fatigue, I remembered that the coupler was left to be modeled from the last day. So, I started with that next. I needed a rigid way to connect the pulley/idler case to the 4040 and 2020 aluminum extrusions.

This is what the pulley case looks like now.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9c4e8f8a-34e0-4616-9b10-222f3decfa21" />

Here's what I did next.

- I extruded part of the case to house a coupler.
- Then, from another sketch, I extruded out a coupler similar to that of the other linear guide.

Then, this is the design I achieved:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/30f91d0f-cf96-44a5-bb89-9ac6b0b3c069" />

But before I continued with the design, I thought of refining the existing design of the pulley case instead. Like this:

- I added fillets on the sharp corners inside the pulley case

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/36ade463-0247-4af3-b566-b2d240fa6a98" />

- I added a face offset on this face to make the wall 1 mm thicker

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/deaa37cc-f38d-49ff-9fe5-e109e3ea83a0" />

- Then I added fillets on the internal edges of the case.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7baf42bb-2b2f-4235-be99-dfa06d1fb38e" />

After that was done, I did a section analysis to check the design. Then I first mirrored the body to make the other half of the pulley case, and then I mirrored the full component again to make the idler case. I also copied the other components like the shaft adapter, bearings, pulley to idler, etcetera.

I will be using [this](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12&_t=1785996787271&spm=overseas-fa-pc.homepage.hint.1&up_spm=Jlcpcb.Loginpage.1003) pulley for both pulley and idler in the Z axis tensioning system.

I now had to take a similar design to the X and Y tensioning system as well. So I copied the Z pulley case to position it where the X pulley case is supposed to be.

First impressions after doing the copying: the pulley is way too big. So, I used offset to make space for the pulley.

Here's the lapse of today's session: [PATRA-LPS-27-D47](https://lapse.hackclub.com/timelapse/FEMEhu7VLqJm)

**Total time spent: 4h 30m**

---

# Day 48 — 06.08.2026: Reconsidering the X & Y Belt Path

I had to find a way to make the belt pass under the 4040 extrusion and have the pulley as small as possible. The smallest pulley diameter depends on the sum of the stack height of the linear rail, the linear block, and the depth of the return belt inside the 4040 extrusion. The distance between the bottom of the linear rail and the belt's top path was 20.30 mm. The 4040 extrusion goes under that, and the belt passes in between.

But to make the pulley smaller, I got the idea to raise the height of the pulley/idler cases. This would reduce the diameter of the pulley/idler needed significantly. I also imported [HFS5-4040-1000](https://in.misumi-ec.com/vona2/detail/110302684530?HissuCode=HFS5-4040-1000) in place of the previous 4040 extrusion for direct comparison.

To execute this plan, I created a new sketch to validate my design strategy:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/44a3637e-6cf1-4b45-89d8-9a6318bb6753" />

In this sketch:

- I made sure that the center of the pulley and idler stay at the same point, with only a change in height.
- Also, the upper part of the belt was left unchanged. As the pulley became smaller, the case's center rose higher.
- The height depended on the diameter of the pulley and idler as well.
- A 20-tooth pulley is used for Z axis tensioning system, and I used a 22-tooth pulley for the X and Y axis tensioning system.

According to this sketch, I need to move the pulley/idler case by 7.495 mm higher, I have to use 22 teeth pulley/idler, and I might need to replace the previous aluminum extrusion with [HFS5-4040-1000](https://in.misumi-ec.com/vona2/detail/110302684530?HissuCode=HFS5-4040-1000), because this has more space in between. Due to these changes, the belt return path was going directly inside the old 4040 extrusion.

This is how the pulley/idler case looks after moving it 7.495 mm higher.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/32caa474-5f12-4dbc-8806-e7989578b1fd" />

Then I used the sketch to create a new belt and added an internal face offset of 1.73 mm to exclude the belt teeth. I also made face offsets to make the internal shapes align closer to the belt path.

I also added [this](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-22-A-N-d12&productModelNumber=CBYL-AH1-5GT150-22-A-N-d12) pulley/idler to the design and placed it at the ends of the belt.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/447c9a73-6b26-4520-9e5b-2366059712d5" />

Next I had to validate the belt clearances inside the 4040 extrusion body, researched on the linear rails, extrusions and devboard I could use on this project.

After copying the new extrusion and deleting the old one, I modeled a new component called an end plate. This is how it looks now.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0e20449e-5278-46a2-8fe7-ef7fc2e82110" />

Here's the lapse of today's session: [PATRA-LPS-28-D48](https://lapse.hackclub.com/timelapse/zMbr23rqtxQw)

**Total time spent: 5h 20m**

---

# Day 49 — 07.08.2026: Refining Internal Structure of the X & Z Pulley Cases

The bare-bones structure of the pulley and idler case was already modeled in the last sessions. This session covered modeling of the internal structure of the pulley cases that was altered by the screw threads that pass through it and the belt path clearance. At almost every step, I was making the walls too thin, and I had to make sure that the walls stayed as thick as possible. Also, there is maximum thread engagement, and there is enough clearance for the belt to pass through. I wish I were a four-dimensional creature at this stage because I couldn't look into the other parts unless I was doing a sectional analysis. Every time I did a sectional analysis, I discovered that the wall is too thin to work with. 

The very first thing which I did here was the motor M5 screws, which I had to make at least 12.5 mm deep to make it reliable. Instead, I couldn't go deeper than 10 mm. Just look what happens if I make it 10 mm deep:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a57e5d77-c9cb-43b1-b5d5-07717c67d80b" />

And I already knew this, and after asking Google, this belief became stronger; the Math Rule for Plastic Threads to secure a structural component directly into 3D-printed plastic or resin without it stripping is that you must follow the standard engineering formula:

**Thread Depth = Screw Diameter x 2.5**.
	
Another depressing discovery I made, which I was fearing earlier, was the fact that my belt clearances are way too low. I had to ensure more clearance for the belt according to Google AI. The fact that the belt clearance was barely 1 mm above and beside the belt was quite alarming. According to Google AI, I had to at least make it more than 2 mm or 2.5 mm for better clearance, since my belt is more than 1 mm long.

I also had to connect the two halves of the pulley/idler case, for which I extended the screw to the very back, so that with just four M5 screws I can connect both the motors and the two halves of the pulley/idler case. 

What a weird loop I was stuck in: if I had to increase the belt clearance, I actually had to go and increase the distance between the top surface of the belt and the pulley case. But I cannot because the screw walls are way too thin. If I increase the clearance, then I could just end up eating up all the space that the screw thread needs. 

This selected section analysis proves my point:

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/3ae405b0-9e71-461f-b18b-cf368a0b586c" />

And this sectional analysis as well:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0834b834-0b6b-499e-8ccf-d689e3befd0b" />

The wall is way too thin, and I can't think of any possible way to fix this. Driving the screws 40 mm deep gives you more than enough thread engagement, but a 0.5 mm thin wall is dangerously thin for an SLA resin print. The cross-section shows that the screw threads are cutting directly into the printed material. In SLA resin, this thin wall will cause immediate mechanical failure.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a8aa32b7-6639-495c-b590-5fa4571b067e" />

But instead of assuming that this was unprintable, I actually went to JLC3Dp to check if there were any printing risks. And obviously, there were a lot of printing risks. Exactly in those parts where I mentally flagged them 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b809bd65-4f58-445f-b180-d8ff1e656f27" />

I even thought of doing something like this, where there is no thread in the bottom part of the screw, and it looks something like this:

<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/ea043567-8aaf-410d-834b-903326281f6b" />

I even thought of using threadless screws like this, where there would be no threads, and there would be no mechanical failure, even if the walls were thin. I could make the walls as thin as 0.8 mm, and yet the thing would work perfectly fine. But I don't know, actually, if this would even work, and there was a high risk of failure. 

<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/f43c6e05-884c-4ff4-8d73-16ab596b570e" />

One more option I had was using grub screws or blind screws for the internal structure of the motor, but I also dropped that idea.

Then I got the perfect idea, which I needed to fix this. I went back into the timeline when I was actually designing the internal structure of the Z axis tensioning system pulley case on day #47. Instead of making the M5 screw all the way through, I can make it go only 10 mm in and make the walls thicker by decreasing the clearance between the sides of the belt and the case. This won't be much of a problem as the pulley is flanged and this is right after the belt exits the pulley, so there will be no sag. Here're the changes I made to the design:

- Using face offsets, I extended these faces.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/73aa6f5d-0a4d-4bb2-ac34-682427b19725" />

- Extended the part where the pulley doesn't reach.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c9402a24-3134-439e-a66c-55ff461b47ed" />

- One more offset and I had this face

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7b73214d-0ed5-4819-bb57-1a21bd4053aa" />

- I repeated the same process below

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2c7933ea-432a-4a42-8c60-e3350ab74b0b" />

- Then I added fillets to all the new edges.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b5d4ff94-1883-450d-b45a-745451fc7a2f" />

- Repeated the same fillets on the top

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/483c3e0e-8852-4660-9cbe-93f603ee86b9" />

I went back and forth on the timeline like a billion times. I basically solved a problem that I thought would take me 10 minutes in hours. This is the Z axis tensioning system pulley case after I made all the changes:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ea19be39-7b6c-4282-b39f-5c6708e2ac26" /> z axis 

I repeated the same process for the X pulley case as well. This is the X axis tensioning system pulley case:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b686c1fd-7899-4146-9351-d4d98829f3cd" />

With the fixes made, the cross-section proves that the problem is now finally solved, as the walls are not very thin.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2be58f80-7e64-41ae-b32b-52e14bf7bfe3" />

Cross-section from another side:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f6675f64-2de8-449b-b7b7-3751d8c35b42" />

I uploaded the new case to JLC3DP to check printability. It was a success.

Here's the lapse of today's session: [PATRA-LPS-29-D49](https://lapse.hackclub.com/timelapse/flC0-x5OA8DZ)

**Total time spent: 4h 50m**

---

# Day 50 — 08.08.2026: Adding Screw Holes for the X Axis Tensioning System Pulley

First things first, I made some new decisions about the height of the X, Y, and Z pulley and idler cases. The decision was that I wanted to change the distance of the X and Y tensioning system pulley and idlers from 7.495 mm to 7.5 mm, just to round them off. I also decided to raise the height of the Z axis tensioning system pulley and idler from 0 to 7.5 mm to keep them at the same level and just to make things look better. Due to the changes made, I also had to raise the belt for the Z axis, as there was a much larger space under the return belt of the Z axis sensing system. Thus, I decided to add one more 2020 extrusion under it. There are now two extrusions: one that goes under the return belt of the existing system and one that goes between.

Once the height of the tensioning system was sorted, I started looking into the X and Y belts that had no teeth in them, so I added the teeth like this:

- I had previously extracted a single tooth from the Z axis belt.
- I used that tooth and replicated it using the pattern on path feature
- And then I combined the whole thing into a single body. 

I also made some changes to the design of the end plates, where I raised the parts that the tensioning system pulley and idlers were not resting on. I also added space for the 2020 extrusion that goes under.

Then I frantically started searching for a way by which I could reliably connect the X and Y axes pulley/idler cases to the 4040 extrusion. The best place to look for a solution was in MISUMI, as they had all related accessories for the 4040 extrusion. Even after a long search, I wasn't able to find something that I could integrate into the design of the pulley and idler case. I went to JLCMC to search for something like a straight-line connector that connects both 2020 extrusions and 4040 extrusions, and that's when I found [this](https://jlcmc.com/product/s/T02/TPLH/euro-20-series-connection-accessories-slotted-connector).

Though it would work quite well and it would be reliable to use, I did not actually want to source any more components from JLCPCB because I was extremely scared of the customs that could be levied on me. Forge is not going to pay any of my customs, so instead I decided to take another approach that is still reliable, at least for the 3D-printed version of this. And more importantly, the 4040 extrusion was from MISUMI, and sourcing a connector from JLCPCB would have been unreliable because the dimensions most likely wouldn't match. Due to the reasons combined, I didn't actually go into downloading the model and seeing if they would be compatible with each other.

So instead, I decided to model my own connectors with a custom screw pitch. Here's how I did that: 

- On the upper and lower rails, I created a sketch and made 4 shapes with 0.15 mm clearance from all sides.
	
	<img width="1365" height="731" alt="image" src="https://github.com/user-attachments/assets/2dd2a83a-3ef7-4ad9-bd7e-2a95fb1ae676" />
	
- I made those shapes cut into the pulley of the X axis tensioning system and the end plate as well.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ed7d0cbf-6c9e-46b7-b30a-f9b97781a242" />

- Made another sketch for holes under the end plate. I made sure that the holes that I make do not go through any other hole inside the pulley case. 

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/89afbc35-6b84-4b86-b3a8-5a7dbcd978fe" />

- I made three holes under the end plate that lined up exactly with the center of the holes I had cut through. I made sure that two holes go through connectors, and one hole goes directly through the end plate and connects to the pulley.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8bba3897-076f-4add-a5a4-7b95df473e7b" />

- I repositioned those holes, making sure that they are equidistant from each other.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/dc5017ee-f22a-4df3-a734-853f341c3663" />

There was one more issue which I encountered while making extrusions for the connectors and trying to combine them using the combine tool. I discovered that the pulley case was misplaced by 0.001 mm from the center along the X axis. I fixed that by moving the X axis pulley case 0.001 mm towards the center along the X axis.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1bd79197-d83b-4e7e-a068-7c8e7fbf4ccd" />

I even tried to see what would happen if I made the hole all the way through the pulley case, and according to the sectional analysis, it would hole through the belt.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7a6a9494-d02f-40ae-9af7-204ac8012181" />

Next, I remembered that I also had to connect the two halves of the pulley idler case. I got the idea to use screws for this. So, I created a new sketch and extruded it in.

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/412f8eaf-832b-4b58-886d-67b6f17dfb2d" />

Using several section analyses, I made sure that it doesn't hold anything critical.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7916ac7f-6412-4300-b5fc-92d59f7b234e" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ddb5e6b0-62d6-405d-a4ee-3a6208c37e6e" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e6bb26a7-d8ea-4958-b116-e3b5fc1a7ffb" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b41cdc99-9a77-4524-8584-08e6b3e8733e" />

After adding thread to the holes, things look all sorted out. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e5971a96-96c7-4558-ab30-c0359240476e" />

I also searched for the nuts that I could use for this hole, and after searching in OnlyScrews, I found [this](https://onlyscrews.in/products/m3-nut-ss-304?_pos=1&_sid=938b14185&_ss=r). Besides, I also added thread to the holes underneath. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ade5e42a-90d7-44a7-bf3e-697bb1763b66" />

I also added chamfers on the M3 holes, as I was going to use a countersunk screw.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/238e3d03-8f5a-4893-a087-4c60c9b0cd96" />

This is what the x axis pulley case looks like from different sides:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8068fe00-b347-4018-befa-4a47fa1d21d8" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e6ce7ce4-53a3-4921-aed3-7e950c5c2c58" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d9bc3257-8fb0-4cf4-8372-b8ce1014ae43" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a8e0e243-96a7-414e-8292-aa171405ce78" />

But even after all of that hard work, I was really heartbroken when I saw there was a printing risk in the model, in JLC3DP. 

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/a53a29ed-4e35-454a-87e5-e9bc8f7d3710" />

But parallel to all of this CAD that I did today, one worrying discovery I made was that M3 threads printed in 9600 Resin using SLA printing were way too unreliable. This discovery was strengthened by the fact that most of the printing risks involved in the model were related to the threads. I was instead supposed to use something called brass threaded inserts, which are not only suitable for FDM prints but also SLA prints.

Here's the lapse of today's session: [PATRA-LPS-30-D50](https://lapse.hackclub.com/timelapse/KziIqj5W50kG)

**Total time spent: 6h 10m**

---

# Day 51 — 08.08.2026: Modelling 4040 Extrusion Connectors & Fixing Nanoscopic Dimensional Errors

Today's session was one of the longest sessions out of all the days I have spent on PATRA. There might be longer days in the future, but I'm sure about the fact that this day was a lot, lot, lot more frustrating than I initially thought it would be. 

Anyways, in the last session, I had modeled the connector holes needed for the connectors. In this session, I modelled the connectors themselves. 

Here's how I did it:

- I extruded a sketch that I used to make the holes for the connectors from the last session, for both the end plate connector and the pulley/idler connector.
- For the holes, I used the sketch with which I made holes in the last session. The distance between the M3 screw holes was 29.5 mm.
- I also added threads inside the holes for both the end plate connector and the pulley/idler connector.

This is how the connector underneath looks:

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/5080f49b-3cf5-4e98-afb5-06433d2dbf71" />

This is what the connector for the pulley/idler case looks like:

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/487d7cfe-1e67-4cd2-9540-253432373743" />

Once the connector was modelled, I tried comparing it with the options available in JLCMC for straight line connectors. By looking at the model that was available in JLCMC, I realized that I had to also secure the connector to the 4040 extrusion and the end plates using that thing, but with screw threads.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/12ebc1fe-f40c-4974-97cc-419b204cd70f" />

To secure the connectors, I had to drill holes into 4040 extrusions. MISUMI offers options to drill, but I couldn't find the options to drill where I needed it. So, I was really confused about what to do with the holes. 

But while dealing with the holes that needed to be made on the 4040 extrusion for securing the connectors, I also wondered what I would do about the holes that are needed to secure the linear guide (the 1 m MG15H linear guide) to the 4040 extrusion. This was because I cannot use T-nuts for my extrusion because of its shape. I didn't know what screw size I needed, and I also didn't know what the screw pitch was, so I started looking for models since I couldn't find any model in my Fusion workspace for the MGN1H linear guide. And that's when I found [this](https://www.traceparts.com/en/product/hiwin-technologies-corp-mgn15h?Product=90-07042020-029729).

But I got a really good idea. I suddenly remembered that I had an impact drill from iBell, and without thinking much about it, I decided to drill my own holes. The only thing I knew was the fact that it was powerful enough to drill through 5 mm of aluminum. 

Alongside all of this, I also copied the X and Z pulley cases and made other pulley idler cases for X, Y, and Z axis tensioning systems. I also added clearance to the shaft adapters and various parts inside the pulle/idler cases. 

After I had dealt with the problem of drilling holes, the next thing I had to focus on was how to get rid of nanoscopic dimensional errors, which I discovered while dealing with clearances. To be specific, every shape inside the pulley/idler case was off by 0.00037878 mm. And being the perfectionist I am, I had to fix it. Not because I was worried about the fact that it would print wrong, or about the fact that I was addicted to round numbers, but because of the fact that in Fusion, even that tiny number mattered for body splits and extrusions. I had already faced these microscopic or nanoscopic errors before. That made me frustrated every single time when I couldn't get an extrusion right, and there were unnecessary face splits on a face that was supposed to be all flat in a body. And at least for the sake of this model, I wanted everything to be correct. Obviously, I knew that 3D printers are not going to face any problems due to those errors. I was not at all worried about that, nor was I worried about the CNC, but I was worried about the effects on the future design. A small error in the past becomes a big problem in the future.

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/adca2d93-e279-45ae-9ebf-0a186791fc78" />

Trying to fix all this was like a marathon of frustration. I went back in the timeline to those days when I started making the pulley case to see when exactly I made the mistake. But even the tiniest changes I made back in the timeline cause huge effects later on downstream, and I had to go back and forth again trying to undo whatever I did. I even tried moving the faces negative 0.00037878 mm.

<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/bf0c64ad-b5ce-4aae-aee7-a61f91d83466" />

And it actually seemed to work.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6f2c3f46-9dfd-4ba4-8df7-402e570deb73" />

It failed after all that, and I don't even know why. A thunderclap indeed for my patience. I had to undo everything I did, as it caused downstream errors.

Here's the lapse of today's session: [PATRA-LPS-31-D51](https://lapse.hackclub.com/timelapse/jGC2hN65Zw76)

**Total time spent: 7h 40m**

---

# Day 52 — 11.08.2026: Partitioning PATRA & Working on the X and Y Tensioning System

I always had the eternal habit of addressing what caught my attention first. For this day, the first thing that caught my attention was the unchamfered body of the Tool Head. Quite unrelated to what I was doing these days, but I was hell-bent on addressing this issue.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3ee7836a-0ec6-4df8-976c-4127d3eebfb2" />

The first thing I did was look at older versions for the same errors. This was version 14. Version 10 from 4th August, 2026 was the last version with the correct tool head. This discovery taught me something very important: The current way meant that if any problem occurred at one of the main components of PATRA, I would have to go back and forth in the older versions to fix them. For example, version 10 has Unresolved Components. I can't even use it for the newer version.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/483f9953-28d8-423a-940e-83406a47f34c" />

A better approach would be to separate PATRA into three different modules:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/98fe9023-6627-45ee-a9e8-01fb31fdb798" />

1. Kinematic Base Module (KBM)
2. TriTeron Robot Module (TRM)
3. Robotic Arm Module (RAM)

Therefore, I partitioned the project into those three dominions/modules, in Autodesk Fusion.

<img width="397" height="417" alt="image" src="https://github.com/user-attachments/assets/831186c4-2d3b-4f25-8f4f-5461c93c0f5a" />

I realised I cannot tap the aluminium extrusions using my impact drill. So I will drill a smooth hole and use a grub screw and nut to make a lock nut. Since the nut won't fit, I have to make the hole deeper. Since the screw must slide in, I have to make the hole clearance 3.4 mm.

I made the holes deeper using extrude and removed the threads.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/66ca6ff1-bda6-44b3-b026-451f0c846544" />

After I mirrored the X axis tensioning system to Y, I had completed modelling most of the tensioning systems for X and Y.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/259ca747-a503-4642-9d0a-ed9275b5686e" />

Here's the lapse of today's session: [PATRA-LPS-32-D52](https://lapse.hackclub.com/timelapse/8NUdodbSSm-M)

**Total time spent: 4h 25m**

---

# Day 53 — 12.08.2026: Working on the Z Axis Tensioning System

Yesterday, the X and Y tensioning system was done. Now, it was time for the Z axis tensioning system. So, I started with the first thing I could think of, which was incomplete.

That one thing was the coupler that I had left incomplete. Here's what I did to complete the coupler:

- I sketched the face of the existing coupler, with a projection of the 2020 extrusion. I then added clearances on 4 channels.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2724f7c5-6bd8-4b3c-b457-4683daa2af05" />

- Then I extruded the shape of the channels I modeled.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/da4c89c0-3495-4ac0-952d-a6c3cd56a753" />

- I did the same for the sketch below for the end plate.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/868ed83c-fc60-4a49-bb2a-e27b3c4b4241" />

- Then I extruded the sketch I made. I also added holes.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/05e2b40a-a2b9-4001-aa3a-3bed7be30f80" />

This is how the end plate now looks from below:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0017fedf-72e4-49a6-82d4-67a2dddbb68a" />

After copying the end plate 1 to the other end plate, and adding holes on the 2020 extrusion, and adding holes on the Z axis pulley and idler case, this is how the whole KBM without the tensioning system looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9ba2470d-61fc-4234-a897-ee242fd859f7" />

And this is how the KBM looks.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1a872747-66d8-407c-b86f-f5c171a52821" />

But now all belts are left to be fixed for their length that is causing fractional tooth. Moreover, belt clamps are left to be fixed alongside the control electronics.

Here's the lapse of today's session: [PATRA-LPS-33-D53](https://lapse.hackclub.com/timelapse/9bSi1olp-o0V)

**Total time spent: 4h 45m**

---

# Day 54 — 14.08.2026: Reconsidering Belt Slot Length & Setting up the TriTeron Robot Module (TRM)

I had worked enough on the pulley Euler cases, and now it was time to give attention to the X, Y, and Z tensioning system belts and their clamps. On the partition day, I worked on the KBM. Now, I worked on the TRM, too. But when I pressed "Compute Unresolved", things went crazy.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/55785cfb-3407-4669-96c2-12336cc40858" />

Originally, I had chosen the size of the pulley and idler cases based on the dimensions of the NEMA 23. NEMA 23 is 57 mm by 57 mm, and I kept 5 mm of space on all sides, making it 67 mm by 67 mm. Due to this, the distance between the slots of the belt is exactly 1067 mm for the X and Y axis belts. To me, those dimensions didn't matter much back then because I wasn't aware of the fact that this length could give birth to fractional teeth.

The Math Breakdown:

• Belt Pitch: 5 mm for GT5.  
• Pulley Teeth (N): 22 teeth.  
• Center Distance (C): 1067 mm.  
• Formula: N_belt = ((2 * C) / Pitch) + N.  
• Result: ((2 * 1067) / 5) + 22 = 448.8 teeth.  

This was a serious problem, as glass fiber belts can't stay stretched permanently without destroying themselves. The most clever solution that appeared to me was that I would use a length-adjustable clamp instead of a rigid one. But the question was, how. I searched on Google, obviously, and I found [this](https://www.instructables.com/Low-cost-linear-actuator/) project where a guy made his own linear actuator.

That's when I came across shaft-driven roller gantry blocks again, but this time, I actually noticed it and compared it to linear blocks. I learned that MGN15H is much more precise, but more expensive than it. Nor does MGN15H compress or flex under load. I was already at the better and more expensive option.

<img width="1365" height="736" alt="image" src="https://github.com/user-attachments/assets/1e06d191-24cf-434c-a320-f29022bd1b24" />

Without thinking much, I saved this for later and moved to focus on the things that I had the ability to address at the moment.

To bypass the compute unresolved, I used the command **LinkMgr.RemoveAll**. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c82ab49e-631b-4d99-8402-b6dd54ed7605" />

And it worked, eventually.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/04458dfa-3ff0-4b04-bfa9-6eff7aeaf744" />

After I had set up the TriTeron Robot Module (TRM) as a separate module, with all resolved components, I went for a symmetry check on the legs of the TriTeron Legs. And, I found out that the TriTeron lacks symmetry. I need to fix it after I am done with the KBM.

Here're the lapses of today's session: [PATRA-LPS-34-D54-1](https://lapse.hackclub.com/timelapse/t8QozcNFFXst) and [PATRA-LPS-34-D54-2](https://lapse.hackclub.com/timelapse/o06ITPcUajZR)

**Total time spent: 1h 45m**

---

# Day 55 — 17.08.2026: Adding Missing Nuts to the TriTeron

I started by trying to fix the asymmetry, which I discovered on the last day. Yes, I was aware of the fact that I had decided to address the KBM first, and then go for the TRM. But I wasn't able to stand asymmetry, nor was I able to think of any way I could fix the problems with the belt length in the KBM.

I compared both mass and their positions using Properties and sketches. 

<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/43322c7e-95ed-48f7-a3bf-2b3262adc384" />

During this, I noticed missing nuts on the distal joints. So, I searched for those with nylon, i.e., Nyloc nuts. I found [this](https://onlyscrews.in/products/m5-nyloc-nuts-mild-steel-with-zinc-plating-dia-5mm) on OnlyScrews. But since it had no model, I sourced my model from [this](https://fabory.partcommunity.com/3d-cad-models/sso/din-982-prevailing-torque-type-hexagon-nuts-with-non-metallic-insert-high-type-fabory?info=fabory%2F3_nuts%2Fdin_982.prj&cwid=6698) site.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b699b278-db71-4673-9aac-9c4e83ce6f30" />

Then I imported the model and added it to the distal joints, after making sure the nut is compatible with the shoulder bolts. To make sure, I went through the datasheet once.

While doing this, I also noticed that there are nuts missing inside the mounts. So, I added the nuts there as well.

I also added a little notch on the X and Y leg mounts for clearance.

<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/2a85357b-3dbb-48d8-b66a-eef9acd7b83c" />

Also added fillets to it.

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/24893e7e-c56a-4ada-a5fb-d3f884d7f76f" />

Here's the lapse of today's session: [PATRA-LPS-35-D55](https://lapse.hackclub.com/timelapse/kbW8ePVyZFrs)

**Total time spent: 2h 15m**

---

# Day 56 — 20.08.2026: Working on the Way to Connect the KBM to the TRM

Today's session was mostly about designing the transition between the X, Y, and Z linear blocks and the X, Y, and Z axis leg mounts of the TriTeron, respectively.

But firstly, I hadn't applied any clearance to the holes for the nuts in the TriTeron Leg Mounts. So, I added a clearance of 0.2 mm on all sides, as this will be printed in SLA resin.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1835e88c-096f-4942-9bb2-0a8c4dfb7453" />

Little by little, I realised that my plans weren't realistic because I thought of using threads inside the SLA prints, and I also thought of not using any clearance initially. I thought of connecting the TriTeron to the KBM using the leg mounts and countersunk screws, but now I realize that I cannot thread the linear blocks, as this will cause cross-threading. The best option here was to completely get rid of all the threads in the parts and instead use brass inserts only where it is needed. Except for that, I should use a 3.4 mm clearance hole for M3 screws. Due to this, I decided to connect the XYZ axis TriTeron leg mounts directly to the X, Y, Z clamps using longer screws.

Here's what I had before I executed the plan:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3d8f6124-655c-4c4f-a3d8-98685227275a" />

To execute this plan, here's what I did:

1. I first removed all of the chamfers on the X, Y, and Z axis linear blocks. I also made the holes 3.4 mm in diameter. Thus, the threads were all removed automatically. This will eliminate any chances of cross-threading. This is how it looked after (section analysis):

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/87814527-9410-478f-a008-f21703762987" />

	But after this, I faced the negative consequences of the partition. The linear blocks from KBM and the leg mounts from the TRM were supposed to be connected. But due to the partition, they were now completely separate files. There was a possibility that the two shapes where each one connects wouldn't match, and it was hard to check even if they matched.

	But I started with the Z axis leg mount anyway. I had both the TRM and the KBM designs open in Fusion. I checked the dimensions of each of the designs at the part where they both connect, and I saw that there are some irregularities in the connection and some dimensional errors.

2. I made a new sketch on the bottom of the Z TriTeron Leg Mount and made new holes for the mount by copying the shapes on the Z axis linear block clamp.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9618756e-4349-4346-b047-0aa33eca3c2a" />

3. Then I extruded those holes, and this is how the Z leg mount looks now. 

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3f1f842e-af4f-4d31-95b2-3fa476e4851b" />

	Next, I had to use threaded inserts for the parts. Since I was using LC3DP service for printing this in SLA 9600 Resin, I read [this](https://jlc3dp.com/blog/threaded-inserts-3d-printing) and [this](https://au.rs-online.com/web/content/discovery/ideas-and-advice/grub-screw-guide?srsltid=AfmBOopNiwtA8NfJS_XdWebTBMCbxxgH9OgqusFrMrq0L6IpBoOuXclu) to learn about using brass inserts in prints. I learned that there are two types of inserts:

	- Heat-pressed inserts for FDM prints using PLA, PETG, PA, etcetera. They need negative clearance of 0.4 mm, so we make the holes smaller.
	- Cold-pressed inserts for SLA prints using 9600 Resin, 8001 Resin, etcetera. They need positive clearance of 0.4 mm, so we make the holes bigger. 

	Heat-pressed inserts grip by melting the plastic, and cold-pressed inserts need super glue.

	I had made up my mind for doing SLA prints, so I needed to adjust my dimensions of the holes for cold-pressed inserts, by making the holes 0.2 mm bigger and using super glue.

4. With reference to the previous sketch I had made, I made a new sketch where I made holes for glass inserts with 5 outer diameter holes. The outer diameter of the hole was 5.5 mm because of [this](https://onlyscrews.in/products/m3-x-15mm-brass-threaded-inserts-copy) brass insert, with a 4.8 mm outer diameter.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/92b75b21-9e24-4c4e-b0ae-2ebd9589e8c5" />

	While doing this, I realised that I needed a 30 mm long insert for the taller side of the mount. But the tallest insert was 15 mm. I wanted to stack two of them to make it to 30 mm, it is would have caused cross-threading and would have been unreliable.

5. I then decided to use a brass insert on the top for the longer side, and I even added those. But to prevent cross-threading, I will make sure I add those after the bottom ones are well secured with glue. This is the section analysis:

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/93677313-4217-4d95-84c3-45232c049a05" />

But this is also likely to fail. So, I dropped using double inserts for a single hole on the longer side.

6. So, I then extruded the inserts and adjusted the clearances by increasing them from 5 - 4.8 = 0.2 to 0.4, so that the brass inserts actually enter and I can use super glue to secure them firmly. I have decided to use either button head hex screws or socket head screws for these. Also, I will keep the upper 15 mm of the hole empty and rely on the threads instead.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a41f0bb7-25a5-43d6-953b-78166f4f9141" />

	This is how the cross-section looks now.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/fbf552c5-fe0a-42d2-a4c4-9fd6d3f35d4e" />

7. But alas, I made another important realization. There was literally no need to use any brass inserts because there are already threaded holes inside the MGN15H linear blocks. If I used any brass inserts, it would have caused cross-threading; they are all supposed to be connected using a single screw.

But I was tired enough already to continue working on this.

Here's the lapse of today's session: [PATRA-LPS-36-D56](https://lapse.hackclub.com/timelapse/N6d0BsuXTSuq)

**Total time spent: 3h 10m**

---

# Day 57 — 21.08.2026: Working on the TRM Z Leg Mount & KBM Z Belt

Just like yesterday, today's session was about working on both the KBM and the TRM at the same time. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d482092b-f524-4793-951a-8575c80bfa2b" />

Due to the problems that I had faced yesterday, I decided to completely get rid of all brass threaded inserts in the Z leg mount. Instead, I did this:

- Using face offset, I changed the hole diameter for the brass inserts to 3.4 mm, for the long side.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/eef62c81-70b9-4428-b889-e5a39d73f87f" />

- Then, using extrude, I made the hole straight, as there was no need of any inserts, for the long side.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2beab45a-5ae4-40f1-93b1-8c2bbd84cc5b" />

- I added a 1.3 mm equal chamfer on the edges as I was going to use countersunk screws, for the long side.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/781f5b87-72d5-4452-90dc-c94b29a5d2b9" />

- Using face offset, I changed the hole diameter for the brass inserts to 3.4 mm for the short side

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5cb0d5c3-9a8f-458c-8dd3-d9391c05a68a" />

- I made the holes above the screw holes for the shorter side bigger so that there is space for the screw head. 

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/aafcf367-992f-49cf-9b9b-69f13020bf93" />

- Then I added camphor to the edges for the short side.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/48c165a1-8e2d-426b-8a5e-1160cb9db52a" />

Next, I calculated the screw length required for the long side and the short side:

* Long Side screw length: 30 mm + 15 mm. Here, 30 mm is the Z leg mount long side of the TRM, and the remaining 15 mm goes into the Z linear block of the KBM.
* Short Side screw length: 10 mm + 25 mm. Here, 10 mm is the Z leg mount short side of the TRM, and the remaining 15 mm goes into the Z linear block of the KBM.

To make the assembly more convenient, I am adding one M5 screw under the clamp that I can screw in and then screw the other countersunk screws. Here's what I did for this:

- I made a hole in the center of the old sketch below the Z leg mount that I used to make the holes before.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/62d3b096-28c3-4d10-8363-f964a1e9e6ff" />

- Then I made a 10 mm deep hole into the Z leg mount.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f06c319f-ca16-4bdc-bcf7-c7bdcbdfc61d" />

	I noticed that I had forgotten to remove the M3 brass inserts. So, I removed those.

- Then I extruded out the brass insert.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/21934f77-6649-484e-a7fb-5053e63e0cef" />

- Lastly, I added a brass appearance and threads.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/afd41b27-f286-4777-a932-377e30734ef3" />

I was then done with the Z leg mount. The next logical step was to probably work on the X and then the Y leg mount. But, I instead had one more thing to do: working on the belt length to fix fractional teeth. So, first I confirmed if I even have fractional teeth in the first place. I used the following sites to calculate belt length and other metrics:

1. [Oriental Motor](orientalmotor.com/motor-sizing/beltConveyor-sizing.html)
2. [Universal Belting](universalbelting.com/calculators/)
3. [Infinity Belting](infinitybelting.com/conveyor-system-calculators)
4. [Meiya Precision](meiyaprecision.com/timing-pulley-and-belt-calculator/)

The math breakdown of the belt calculation for the Z axis tensioning system:

• Belt Pitch: 5 mm for GT5.  
• Pulley Teeth (N): 20 teeth.  
• Center Distance (C): 1201 mm.  
• Formula: N_belt = ((2 * C) / Pitch) + N.  
• Result: ((2 * 1201) / 5) + 20 = 500.4 teeth.  

The Z belt already had modeled teeth. But I wanted to see if I give 5 mm pitch to the teeth, would they actually have a distance of 0.4 teeth between the first and the last. 0.4 teeth means 2 mm, as the pitch is 5 mm.

Expectation: If I add 500 teeth using a pattern on a path with 5 mm pitch/spacing, I will have the last tooth 2 mm from the first tooth.

What I did: I placed one tooth 2 / 2 = 1 mm from the center, and for the pattern, I needed the belt loop length. I struggled to calculate it at first, as I had rounded off pi to two digits after the decimal, instead of 8 digits, in the pulley/idler, which would have been more accurate.

Reality: My belt loop length was off; the distance didn't come to 3 mm, and thus my expectations didn't become reality.

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/77c037dc-b4a6-4da7-8314-a98aa424c4ca" />

But anyways, I kept the teeth of the belt and used the combine tool to combine the 473 teeth and the pre-existing belt body. This is how it looks now.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5f92847f-5c26-4fee-9e84-ec0c7698a984" />

Here's the lapse of today's session: [PATRA-LPS-37-D57](https://lapse.hackclub.com/timelapse/leNJNnY3fMNK)

**Total time spent: 3h 30m**

---

# Day 58 — 22.08.2026: Working on the Z Axis Clamp

I didn't get my hands on the adjustable belt clamp in the last session, which I was originally supposed to get my hands on. So, I instead worked on a non-adjustable rigid clamp, which is a mechanically sound design.

According to the math I did yesterday, I was supposed to have a 5 + 2 = 7 mm gap between the first and the last tooth in my Z belt if I cut it due to the fractional tooth problem. The most logical thing here was to actually make a clamp for that exact dimension, where there is an additional 3 mm gap between the first and the two centermost teeth. 

Here is exactly how I did that:

- First, I deleted all of the screw threads and the holes in the Z clamp. 

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/5e49093a-a894-4246-9533-0c7fb3d81060" />

- Next, I created a new sketch where I bisected the Z clamp into two parts.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/0f6f71ac-e494-4604-9d0b-39441426e88c" />

- I then excluded one half of the belt clamp.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/54bd9e77-1c93-412e-82e1-6523032e1125" />

- I use that extruded part to split the clamp body into two halves.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/7152d79b-89d0-466e-b22c-90004a740d8a" />

- Then I extruded inside and deleted the extra part.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/e58db4e1-1229-44bb-b96c-5925558f3e4f" />

- Lastly, I moved the halves 1 mm apart from each other (2 mm total).

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/28146db2-4ee7-4f00-803a-001b86c5cb4a" />

After joining the two parts using extrude, I created a new sketch to redo what I did in the last session and failed. In the sketch, I used two teeth, and I made sure that the pitch between those two teeth is exactly 7 mm. The midpoint of the distance is on the Z axis of the Fusion workspace. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e22644e8-fe95-4985-867f-94f6155f6d75" />

I found out that the outer loop length of the belt was 2513.935 mm. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/16a0c4f2-65cb-4b70-9113-d05a1d61b92d" />

For the pattern, I placed the last tooth 2513.935 - 7 mm from the first one. Due to the decimals, the pitch was not a round 5 mm. But this was not a problem, since this is only design.

<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/cee96fb9-97b5-4dc1-b42c-ad172d23e1a0" />

Next, it was time to place the belt and the clamp to see if their profiles match, using:

- Distances between each tooth profile: Matched  
- Width of the belt and the clamp: Matched  
- Distance between the last and the first tooth: Matched  
- Coordinates of the clamp and the belt: Matched  

Following this, I worked on the upper clamp of the Z axis tensioning system. Here's what I did:

1. **Adjusting Upper Clamp Height & Infill:**

	The belt has risen in height because of the increase in height of the Z axis pulley/idler case due to the end plates. As the belt rose, the clamp must too. So, I lifted the lower parts of the Z upper clamp by 8.065 mm

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/400d95e9-7827-4281-b7f9-6b626de81667" />

	There was a hole inside the upper clamp.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/51d80c79-786b-4375-beb3-9db701692e57" />

	I deleted it as it was unnecessary.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/9acb3196-66ed-4dfb-8df7-8613e53d414b" />

1. **Increasing Length of the Z Axis Upper Clamp:**

	Before day #44, there were 8 teeth on the X, Y, and Z lower clamps. On day, I increased that to 10 teeth, thus increasing the clamp length. Today, on day #58, I further added a distance of 2 mm between the 5th and 6th tooth, thus increasing the distance further. In all of this, there was no change made to the upper clamp of Z axis, so it obviously was a lot shorter than the lower one.

	I extended the two sides of the Z upper belt clamp.

	First side:

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/327edb8b-1377-4d47-b962-9d58d508e4a9" />

	Second side:

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1de3bfcb-4d8f-4fba-a241-6dadf4cb25f7" />

	In order to make the two ends symmetrical, I used extrusions, face offsets, delete faces, and split bodies.

3. **Combining the Z Linear Blocks, Z Blet Clamp Top & Linear Block Unifier:**

	Previously, there were three parts on the Z linear block:

	1. Linear Block Z 1 on the X rail
	2. Linear Block Z 2 on the Y rail
	3. Linear Block Unifier

	But for assembly convenience, I combined the upper into a single body.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4191f2f4-0108-4027-9433-88227199d99f" />

4. **Making the Combined Body Symmetrical:**

   The combined body was not symmetrical, so I drew a sketch on the upper plate and then, on the face, divided it into two parts.

   <img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/13e6c064-c87d-4464-a46e-79de6599cda9" />

   Then I extruded part of the sketch.

   <img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/14b35cc5-6ca2-427b-bbde-55ed1111286f" />

   I used the new face created to split the body into two parts.

   <img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/33c9d9d2-ae2b-4e23-b7c6-eb9413996a2a" />

   I used one side of it to mirror and then deleted the other side.

   <img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/702518ca-74cf-4b30-9de4-6a9ea8dea871" />

The upper clamp was dealt with. It was then the turn for the lower clamp. The thing that was left in the lower clamp was the clearance. There was no clearance in the clamp, and if the print was slightly larger, the belt teeth would not fit in. If you see the section analysis, you can see that there is no clearance:

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/809cead6-36df-4497-81b1-849b3c01dc97" />

I thought it would be very simple to add clearance to the teeth. I would just select the teeth, and using face offsets, I would make it bigger, but it was not as simple as I thought. When I tried doing that, it failed repeatedly, so I created a new sketch on Z axis lower clamp. I tried looking into the issue, and I found out that the geometry of the belt teeth was such that I could not simply increase the clearance for the teeth. If I did so, it would create negative geometry on the edges of the teeth. And if I did that, the object would no longer be a solid, and thus it cannot exist.

As I was unsuccessful in adding clearance to the teeth of the belt clamp, the most obvious workaround was to import a belt clamp from the internet to see how it is done. But no matter how much I searched it, I couldn't find anything that I wanted. 

But then somehow I got the perfect idea to make the belt clamp with proper clearance. Here's how I did it:

- First, I added 0.05 mm of offset on the tooth, and the shape became like this, which was the problem.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/c7dad06b-58ba-40c1-98c8-aa22714e9964" />

- Next, I extended the larger circle below the topmost small circle, and I deleted the topmost small circle.

	<img width="1365" height="730" alt="image" src="https://github.com/user-attachments/assets/f06cb5cb-353d-4e21-9c4e-b9e22736a2ba" />

- I use the Break tool to delete the unnecessary parts of the circle that I extended. 

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/99dbf5b2-0cb2-4af5-8f4d-4b9cbb55ccd4" />

And by this, a somewhat mechanically sound design of a single tooth for the belt clamp was done. I then simply copied this tooth 9 more times, making sure that there is an extra 2 mm gap (7 mm pitch) between the fifth and the sixth (the two centermost teeth). I extruded the sketch to make the new teeth, adjusted the overall length, and added screws before placing it under the Z upper clamp.

But the clearance in the belt was too small, and that is a big problem. Honestly, I really had to redesign this in the future.

Here's the lapse of today's session: [PATRA-LPS-38-D58](https://lapse.hackclub.com/timelapse/CEqqbFVMyiMs)

**Total time spent: 3h 40m**

---

# Day 59 — 23.08.2026: Fixing Nanoscopic Dimensional Errors & Eliminating Fractional Teeth in X Axis Belt

Today I time-travelled two days back. Thanks to my dear laptop.

I had picked up exactly where I left off yesterday. I had created a new sketch where I was about to project the geometry of the Z axis belt onto the sketch, and during that time, my Autodesk Fusion crashed. 

<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/c369a650-3e59-4bc9-a6f6-221a25a52420" />

I simply lost all of my progress that I had made yesterday and the day before, and I time-traveled back two days. At that time, I had two options:

1. Do exactly what I did before.
2. Focus more on the things first that will have more influence on the future.

I chose the second one instead, probably because I wasn't even sure about exactly what I did in those two days. But even though I chose the second option, I was definitely going to keep my instincts of addressing what I see with my own eyes first. Thus, I deleted the countersunk chamfers for the X, Y, and Z clamps.

But immediately after that, I noticed a huge problem. The thing was that, just out of pure curiosity, I wanted to see what the exact distance was between the two innermost points of the Z block 1 and Z block 2. I honestly don't know what that was supposed to be, but I'm pretty sure that it was not supposed to be 27.00000898 mm, which it was.

<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/2ebbdcd9-3634-4ea0-a7a6-d9f7a3194e0c" />

When I saw this, my first instinct was not to immediately go and solve this somehow. My first instinct actually was, "Why did this even happen?" Was it that Fusion was itself making some stupid errors, some nanoscopic stupid errors? Because I don't really remember myself moving a body 1 nm from one point to the other, intentionally. Or it could be that my fingers are way too sensitive, that they make nanoscopic changes, and my eyes don't even catch it.

Whatever it was, I had to fix it again, not because of 3D printing tolerances or CNC tolerances, but because of the fact that this is going to cause serious problems later on in the future. This is because Fusion sees even a 1 nm thick body as a solid and even renders the face with its own edges.

At those times, my brain and, of course, the pixels in my computer couldn't display those nanoscopic dimensions so that I could understand: "Oh, this is not a 2D object. It is actually a 3D one." It has happened many times, and again I have to fix it. 

Here is exactly how I fixed those nanoscopic dimensional errors:

Due to the existing joints, the Z axis block had only two directions to move: linearly along the linear guide, back and forth. My first instinct was to actually go and see what the position of a point on either of the Z blocks was. I had to make sure that it was a whole number and that it absolutely does not have any nanoscopic decimal.

Coordinates of a vertex on the Z Linear Block 1:

X Position: -134.80028288 mm
Y Position: 30.00 mm
Z Position: 53.00 mm

I moved the full component to achieve the position:

X Position: -135.00 mm
Y Position: 30.00 mm
Z Position: 53.00 mm

Also did the same with the other Linear Block.

But then I noticed more nanoscopically wrong dimensions, and then I decided to make a new linear block entirely, after saving a copy of the old one as a body. Here's how:

- I created a new sketch on the MGN15H linear block body, with a center rectangle of dimensions 35 mm by 58.8 mm.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/2837eb4e-2c52-48b6-a7e5-01270048b3c4" />

- I made a 19 mm-wide rectangle that passes horizontally through the center for belt clearance.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/d6475a17-e867-4a4e-a963-752b7086ad28" />

- I made 3.4 mm clearance holes in the existing projected holes of the MGN15H linear block.

	<img width="1365" height="729" alt="image" src="https://github.com/user-attachments/assets/8bdc628f-a510-4dc0-84af-e3ff2a31879c" />
		
- Then I extruded the highlighted parts of the sketch, representing the walls of the block.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/a479036b-5d9b-4e6c-9626-45273d61351d" />

- Then I made a new sketch on the wall and then extruded it.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/b5ccf90c-cf27-4f5e-aa67-88f2a158c0e5" />

With chamfers and fillets added, the body now looks exactly like the linear block I tossed into the trash can, but this one has the right dimensions.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9f1bb331-bd53-464f-b659-02d4a480b8f1" />

I then added appearance and copied it to the other linear blocks, obviously. But while doing this, I again came across the dimensional error of 0.00037878 when I was calculating the belt length for the X axis tensioning system, while checking the dimensions of the X axis lower belt clamp. That's when I got the perfect idea to completely get rid of fractional teeth.

To determine the number of teeth, we have the following variables:

• Belt Pitch
• Pulley Teeth
• Center Distance

I cannot change the pulley teeth nor the belt pitch. The only thing I could change here is the center distance. The center distance for the X- and Y axis tensioning system was exactly 1067 mm. According to the math, if I changed that to 1067.5 mm, I would have exactly 449 teeth. No more fractional teeth.

The length was determined by the following things:

1. The length of the aluminum extrusion
2. The length of the pulley
3. The length of the idler

I am absolutely not going to change the length of the aluminum extrusion. I instead chose to change the length of the pulley and the idler symmetrically. 1067.5 - 1067 = 0.5 mm. If we divide it into two, we get 0.25 mm. If we increase the length of the pulley and the idler cases by 0.25 mm towards the center of the tensioning system, they would be placed 0.25 mm each outwards. Due to this, we would have no more fractional teeth and exactly 449 teeth. 

A more detailed explanation of the same concept: 

A GT5 profile timing belt has a tooth pitch of 5.0 mm. Because both pulleys in this system are identical (22 teeth each), the belt path is perfectly symmetrical, simplifying the standard belt length formula to: Total Belt Length = (2 * Center Distance) + (Number of Pulley Teeth * Pitch).

* Initial Geometry: The layout for this specific case dictates a center-to-center distance of 1067.0 mm, derived from a 1000.0 mm aluminum extrusion plus two half-lengths of the 67.0 mm pulley/idler cases.
* Length Calculation: This design results in a total straight section length of 2134.0 mm (2 * 1067.0 mm) and a wrapped section length of 110.0 mm (22 teeth * 5.0 mm), combining for a total belt length of 2244.0 mm.
* Teeth Consequence: Dividing this total length by the 5.0 mm pitch yields a non-integer count of 448.8 teeth, which is physically impossible for a closed-loop timing belt.

As a direct consequence of adjusting the target to a physical loop of exactly 449 teeth for this specific setup, the entire physical assembly must shift to maintain proper belt tension without slack.

* Required Length: Specifying a discrete 449-tooth belt establishes a fixed, non-negotiable total belt length of 2245.0 mm (449 teeth * 5.0 mm).
* Distance Adjustment: Subtracting the constant 110.0 mm pulley wrap leaves 2135.0 mm for the straight sections, forcing the center-to-center distance to increase to 1067.5 mm (2135.0 mm / 2).
* Structural Impact: To accommodate this wider center distance while using the same 1000 mm aluminium extrusions, the pueelys/idlers must be increased in length by 0.25 mm on both sides.

Data Summary Table

| Parameter | Configuration 1 (Previous) | Configuration 2 (Current / Consequence) |
|---|---|---|
| Belt Profile & Pitch | GT5 (5.0 mm) | GT5 (5.0 mm) |
| Pulley Teeth Count | 22 teeth | 22 teeth |
| Aluminum Extrusion Length | 1000.0 mm | 1000.0 mm |
| Center-to-Center Distance | 1067.0 mm | 1067.5 mm |
| Straight Section Length | 2134.0 mm | 2135.0 mm |
| Wrapped Section Length | 110.0 mm | 110.0 mm |
| Total Belt Length | 2244.0 mm | 2245.0 mm |
| Final Belt Teeth Count | 448.8 teeth (Fractional) | 449.0 teeth (Whole) |


The math was revolutionary, and I just realized that all my efforts with the fractional teeth adjustable clamp were in vain. But then I also earned the privilege of achieving two goals with a single CAD operation. The other goal was getting rid of that 0.00037878. So, instead of moving the X axis tensioning system pulley 0.25 mm away from the center on the X axis, I moved it 0.25037878 mm (0.25 + 0.00037878).

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/bf8bc328-aa68-4814-9265-beb358e776f6" />

This eliminated the number 0.00037878 mm from the body by cancellation. I simply then moved the faces of the body -0.00037878 mm to cancel their positions out. I then also moved the pulley, washers, bearings, and the bearing cover as well that way.

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/76c7cf09-3e18-494d-874b-11db4205dfb7" />

With this, I finally got rid of the number 0.00037878.

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/e4891df9-4e4e-46ff-9a4f-3b60511f2a82" />

After that, I went on to redesign the belt clamp lower of the X axis tensioning system. But I got stuck with the thickness of the clamp. I was supposed to make it like 6 mm, but I barely had 0.5 mm thickness available. To increase the thickness, I had to increase the height of the belt by increasing the height of the end plates, and thus the entire tensioning system.

In the end, I searched for UHMW tape that I would like to apply on the linear blocks to prevent belt wear.

Here's the lapse of today's session: [PATRA-LPS-39-D59](https://lapse.hackclub.com/timelapse/ccsG_HzJn3z3)

**Total time spent: 3h 20m**

---

# Day 60 — 25.08.2026: Designing Belt Sheilds

I started with the problem I left on the table yesterday: too-thin clamp. To fix this, I had to deal with the things that are related to this. What's related to this? Literally everything in the entire tensioning system, the end plates, and the aluminum extrusions.

I've always wanted an aluminum extrusion with integrated MGN15H rails, but I never found one except on Amazon. The prices were absurd on Amazon. This is what I'm talking about. Not literally, but the concept is the same. 

<img width="1000" height="753" alt="image" src="https://github.com/user-attachments/assets/c1b4ab41-461c-459c-87e5-6d9931b7eb98" />

But neither JLCMC nor MISUMI had it or anything like it, so I had to choose other workarounds. 

I just had to increase the height of the entire tensioning system, just like I said in the last session. It was really hard to do because the higher I moved the tensioning system belts for the X and Y tensioning system, the closer the belt return path was to the 4040 extrusions' inner walls. I wanted to keep clearance, and I couldn't use UHMW tape due to its shape. Just look at the shape: it is sharp, and it would not just cause belt wear if the belt rubs against it. It would cause the belt to cut. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4219d477-ff5b-4239-9668-1c580463fbe9" />

But I believed that I could find a workaround, so to increase the thickness of the belt clamp for the X and Y tensioning system, I moved the entire belt up by 1.5 mm.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4388f5ec-5398-4d3b-bf3b-9de95aabf269" />

I can't anymore rely on clearance to prevent belt wear (or belt cut), so instead I must use something like UHMW tape. There is no surface to apply UHMW tape to, so I must use UHMW Guide Rail Shields instead. I found [this](https://in.misumi-ec.com/vona2/detail/110300140370?HissuCode=NLK-1000) on MISUMI. These can be a very good solution to my problem, but they are crazy expensive, like $100 each.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/41d0b754-5396-477b-9824-d2daf96a1f20" />

I found [this](https://www.phidgets.com/productfiles/TRM4227/TRM4227_0/Documentation/TRM4227_0Mechanical.pdf) datasheet for the GT5 15mm belt. The material is LY12 (2024-T6), which is a specific grade and temper of a high-strength, heat-treatable aluminum-copper-magnesium alloy. The thickness is about 8 mm total. I can't make my clamp even half as thick, despite the fact that I would fabricate it out of nylon.

I created a new sketch where I thought of creating some kind of belt shield to cover with UHMW tape and prevent belt wear. I was basically thinking of making my own UHMW guide rail shields instead of buying them from MISUMI.

Here's what I did next:

- I projected the belt's cross-section first

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/1aa2ffe8-fab8-477a-886d-3418f921a98e" />

- Then I created a rectangle around the return belt.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/9723ccf5-dff0-4ed0-9344-16026749b5b2" />

- To make the shape fit inside the 4040 extrusion, I made more rectangles around the center, even reaching the circles.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/6c26984d-94d7-41d8-9578-0e4ace34d982" />

- I kept only the upper part, which was necessary

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/b1f12365-f7a2-4754-b916-db740d3fb0fd" />

- Then I added clearance along the edges.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/1d423344-f97d-4d68-a95c-4a8e5aec9d9e" />

- After several back-and-forth visits in the timeline, I removed the sides, keeping the minimal shape.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/c4f03734-ace7-448c-934c-7baa52ca19ea" />

- After extruding it 500 mm, I uploaded it to JLC3DP to check printability.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/112aee38-9f86-42fa-966e-19b0e4244ed9" />

- Since the design passed without being flagged, I added two beam-like extensions to give it strength.

  	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/51d04176-30b3-4244-9d5e-4535e37c7d1a" />

Kindly note that the process that I followed was explained in a very, very straightforward and simplified way, with only the net changes. What do I mean by net changes? I mean that I did not capture myself going back and forth in the timeline, changing the variables like the height of the belt, the offsets, and the belt's shape. I only captured what was finalized. As a matter of fact, my model was flagged for printing risk twice before being successful, and I first lifted it 2.5 mm, then down 0.5 mm, then again down 0.5 mm.

As the belt shield was completed, I copied it and arranged the components in the Browser. I need 2 meters of belt shield, as there are 2 1-meter aluminum extrusions. It can be fabricated in two ways:

1. FDM in my printer: 8 250 mm belt shields
2. SLA from JLC3DP: 4 500 mm Belt Sheilds

I saved my designs in Browser as the second one. This means I made 4 500 mm belt shields: 2 for the X axis tensioning system, and the other 2 for the Y axis tensioning system.

Here's the lapse of today's session: [PATRA-LPS-40-D60](https://lapse.hackclub.com/timelapse/td59cmkmuuk6)

**Total time spent: 3h 30m**

---

# Day 61 — 26.08.2026: Lengthening Pulley/Idler Cases & Getting Rid of Nanoscopic Dimensional Errors

On day #59, I was successful in getting rid of the 0.00037878 errors, mostly. But due to the changes made in the position of the belt, which was net 1.5 mm rise in height, I also had to move the entire tensioning system up by 1.5 mm.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5c3aa9b0-75b4-4909-b76f-32e72474c9a1" />

Kindly note that the value of 1.5 mm was the net change. Before it even happened, due to the changes in the last few days, it was 1.762 mm, 1.462 mm, etcetera. The values depended on the thickness of the belt shields, clearance between the belt profile and the belt shields, and the thickness of the belt clamp.

Anyways, speaking of the displacement, which is 1.5 mm, I first moved the pulley case up by 1.5 mm, before any other part of the tensioning system.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4d775008-05b5-40d9-9bf0-9aca100c7ed7" />

I had previously moved the pulley case 0.25 mm away from the horizontal center. There was a gap of 0.25 mm due to this. Something had to fill in the space. So, I simply extended the pulley case on both sides by 0.25 mm. Previously, the length was 67 mm, and the height was also 67 mm. The length now became 67.5 mm, and the height was kept at 67 mm.

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/1854caa7-07e7-44e8-b0c2-a7c106034eeb" />

As the pulley was pushed back, the connector holes were off by 0.25 mm on the X axis and by 1.5 mm on the Z axis. Thus, I did this:

- Using Split Body, I cut off the two connectors.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/9b7ccbd2-3b06-42db-a045-b84a06ea240a" />

- I moved the connectors down by 1.5 mm.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/1c0f0d9a-3ef6-4d0e-afda-024d2468e1df" />

- Then 0.25 mm towards the center of the 4040 aluminum extrusion.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/e64e2658-925a-4eff-89ec-37f819a8862a" />

- To bridge the gap, I used an offset face and moved the face 0.25 mm away from the center.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/2b249140-2aef-421b-bfd0-8c4cc92d3c49" />

- Using the combine tool, I combined the respective connector with its respective side.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/6e298d3a-805a-4626-99b8-1797c1c1a213" />

I did all of this with the idler case as well, simultaneously.

Despite the efforts of day #59, the 0.00037878 mm dimensional errors remained.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9643e368-d5d8-45d0-bad6-48e6c7a0c321" />

To fix it, I did this:

- Moved the outer faces of the pulley case away from the center by 0.00037878 mm.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/f61d1ab6-796d-43fb-8098-2fbbeb6a1e44" />

- Moved the entire pulley case body 0.00037878 mm towards the center.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/b557e0a4-e33f-4d55-bce2-fea56b3f4fe1" />

With this, the X axis pulley is nearly complete. I mirrored the pulley to the idler, then mirrored the whole tensioning system to the Y tensioning system. And, by the way, the thickness I achieved for the X and Y belt clamp lower was 3.8 mm: much less than needed. But, since I am placing the clamp directly on top of the MGN15H linear block, the severity of the problem gets a little neutralised.

Here's the lapse of today's session: [PATRA-LPS-41-D61](https://lapse.hackclub.com/timelapse/h5Qet2HkMa8K)

**Total time spent: 2h 05m**

---

# Day 62 — 27.08.2026: Designing the Z Axis Belt Clamp

The belt shields were modeled yesterday. Today was about researching the tape needed for the belt shields and making a mechanically sound belt clamp.

But I still wasn't sure if it was smooth on its own to prevent belt wear. After asking Google, I found out it wasn't. So, I had to use some kind of anti-friction tape, like UHMW tape, as I had originally planned. After I searched for different types of tapes, here is what I learned:

| Tape Type | Friction Coeff. (μ) | Max Temp (°C) | Load Capacity | Key Strength |
| :--- | :--- | :--- | :--- | :--- |
| **Skived PTFE** | 0.05 – 0.10 | 260 | Light to Moderate | Lowest friction |
| **PTFE Glass Cloth** | 0.08 – 0.15 | 260+ | Light to Moderate | High tensile strength |
| **UHMW Polyethylene** | 0.10 – 0.20 | 88 | Moderate | Highest abrasion resistance |
| **Bronze-Filled PTFE** | 0.05 – 0.10 | 200 | High | Heavy machine tool load bearing |

But UHMW tape is very expensive. I searched in various places, like [here](https://elitetape.com/tapes-for-anti-friction-applications/), but I wasn't able to find anything cheap.

Preventing belt wear was like the agenda today. So, I added 1 mm fillets to the internal edges of the Z linear blocks.

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/655a318a-d330-4948-ac4a-8440132734df" />

Due to the progress lost on day #59, the Z axis belt was rendered teethless. I was about to give it some teeth, but that's when I noticed this:

As I had lost progress on day #59, I was supposed to remodel the Z clamp again. On day #58, I had made a clamp design that I was not satisfied with. Today, I did my best. Here's how I designed the belt clamp:

- I created a new sketch on the XZ plane, with the clamp block at a thickness of 3.8 mm.

	<img width="1365" height="736" alt="image" src="https://github.com/user-attachments/assets/261b2c4e-dcb9-4c7a-be31-cbe5cbf0d6e3" />

- I projected a single tooth on the sketch and adjusted it to the new height.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/64071cd2-18f6-4c64-bdce-1638b43f21fd" />

- Then I copied it to another tooth at a 7 mm pitch (distance).

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/1bd7914e-ff9e-41d1-aad9-7f5c61385b1f" />

- Used a rectangular pattern to duplicate one side to total 5 teeth.

	<img width="1365" height="731" alt="image" src="https://github.com/user-attachments/assets/a4d4c9d0-b14d-4588-b801-b545a50a4299" />

- Copied that to the other side, total 10 teeth, making sure there is a distance of 7 mm between the two center-most teeth.

	<img width="1365" height="731" alt="image" src="https://github.com/user-attachments/assets/3c79561b-c867-4a5b-8581-78731bdd514a" />

- Set the clamp height to 5 mm and the length to 52 mm.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/6ced230f-d136-4fea-b893-06e2f32dde09" />

The next part was applying a reasonable amount of clearance, like 0.2 mm, without destroying the geometry and the pitch alignment. Here's how I did it:

- First, I applied 0.2 mm clearance on a single tooth, excluding the upper flat part.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/eeb7131f-f6d4-454b-80a7-f132e9e0dfbd" />

- But the 0.2 mm clearance seemed too much. So, I changed it to 0.1 mm and also included the upper flat part.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/210ec7ad-706b-4ecf-ae9f-8706af2f20aa" />

- Deleted the flat lines, keeping only the offset geometry.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/b8207dfc-f56d-4e92-904d-67ca7e060f89" />

- Copied this to one side 5 times and mirrored the whole to the other side.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/4a4f6cc1-b5ac-49ab-b7d2-25181b85ab18" />

- Bridged the gaps with lines.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/e65fc65f-8877-42bd-a8bf-ee3e1542b4d8" />

- After achieving a closed shape, applied a fillet to the sharp, rounded corners.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/c1c83b60-d327-46d1-ae75-463fe256e2b1" />

But from inside, I was convinced the belt was becoming weird. So, I undid the 0.2 mm offset and everything after it. I tried again:

- Deleted the topmost arcs from the teeth.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/a950c100-985b-4358-819a-ec2bdaf49b7d" />

- Using extend, extended the lower arcs.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/ff6478a5-0c25-40d6-9b97-ec1ee04be95f" />

- Applied 0.2 mm offsets to that shape.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/d3a40e6d-a322-4f19-8ce1-908cdd1868ab" />

- Added 0.51 mm fillets to the upper corners, representing the upper arcs.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/38d605ee-e82d-43d3-ae21-f63278e48aab" />

- Copied a neighbouring tooth to the active one to see the comparison.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/f90a264a-bf42-4406-8cfe-7b7436cb9145" />

- Applied the same fillet of 0.51 mm to the other corner.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/c3b8e827-52f4-49e4-8f49-ce2e74eafe54" />

With this, I most likely achieved a mechanically sound belt clamp design. In this design, there is 0 mm clearance in the roots/valleys of the belt, and 0.2 mm clearance around the teeth.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/58d6d72b-ac0d-4ed0-8601-15c53b85fcd3" />

Once the design for a single tooth was confirmed, it was time to model the clamp:

- I copied it to the other teeth and bridged the gaps with lines, making a closed shape.

	<img width="1365" height="736" alt="image" src="https://github.com/user-attachments/assets/addfd7bb-1110-464e-a498-37d7d5ca3d67" />

- And then extruded it to a width of 16 mm, ensuring 0.5 mm clearance on either side for the 15 mm wide belt.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/2ca0a9dd-ee3f-4eae-85bc-43c841a011b6" />

- I made a new sketch on the XY plane with a 52 mm by 27.5 mm rectangle with a 16 mm wide rectangle inside.

	<img width="1365" height="731" alt="image" src="https://github.com/user-attachments/assets/a872e9f7-af50-4a9b-996d-51437c1e3d07" />

- I added holes for M3 screws too.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/5c4a7d6b-1b0f-4519-8ddf-7fc8b1e41587" />

- Moved and placed the clamp I created on the sketch.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/5febfb7c-c3b3-47a7-9e7b-a726b9569d33" />

- Extruded the two shapes of the sketch by 5 mm.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/e2125b9d-0161-4213-b4e6-d06e055d2560" />

With this, the Z clamp was completed.

<img width="1365" height="731" alt="image" src="https://github.com/user-attachments/assets/3284d4a7-2570-4431-aae4-f032383669bb" />

It was then time to integrate the lower clamp with the upper clamp, and redo what I did on day #58, after making the lower clamp.

- I then moved it between the two Z linear blocks.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/1f453b02-6a0f-45a2-8e73-2e7f7dfbcd93" />

- Deleted the clearance holes for the screws in the upper clamp, as the screw positions changed.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/32382ac1-0a77-4695-a00d-d6d81eb9aa0e" />

- Moved the lower faces of the upper clamp up.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/ffa701ea-c40a-4b49-9e39-da4c8a2a8cb4" />

- Extended the upper clamp in length.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/8239d456-be5a-4dd0-ab30-2afa1d3aedb4" />

- Other side too.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/3572cefa-07ad-4e62-8822-a3366feb4aaf" />

But even here, there are nanoscopic dimensional errors. For instance, the length of the upper clamp is 52.00000039 mm, whereas it is supposed to be 52 mm, just like the clamp.

To fix it, I extended the body a little extra and used a split body to chop off the extra part. Both sides.

<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/f2628b2c-14df-4bbe-ba3e-9db0c13afb9a" />

<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/68dab529-1989-4a45-8496-61092e96d3d2" />

But even after that, things weren't fixed. So, I did this to make a new upper clamp entirely:

- Deleted the upper clamp. And then extended the lower clamp itself.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/30640a5c-475f-4af3-a019-ebe2d43a5b01" />

- 	Extruded cut 1.87 mm length to where the belt will enter.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/3bae2b88-9d99-4c6f-adc0-82b516eab0ba" />

But then the screw holes were another problem, so I made new ones after going back in the timeline:

- Deleted the old ones and drew new ones at a different position.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/6637c58b-2a05-445b-8e74-5be878e73944" />

- Copied the circle for the hole, making a total of four.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/9ab71d0e-0f63-4cd8-a92b-e371e9283e61" />

With this, I was finally ready to do the combination. And I did combine the upper clamp with the Z linear blocks.

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/b9292695-d64e-4f0d-8f7a-bf02d398890c" />

I deleted unnecessary chamfers and added a silver-like appearance. But I didn't combine the plate because the holes were misplaced, and the dimensions were inaccurate due to nanoscopic error. Thus, I designed a new plate for the Z axis, like this:

- First, I moved the old one away, without deleting it.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/c138ff86-2805-40cc-b84b-0d07af430e15" />

- I created a new sketch on the new body, like this:

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/c3d1fa97-7d15-45d3-8a60-da4b3a74c829" />

- I tried my best to make sure that the design corresponds to the older one in looks

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/2b15f0b1-1889-49fb-8907-aeb2f8888ec2" />

- After a few minutes of sketching, I achieved this:

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/5739948b-7de6-4430-a52d-5e0ebbe1967c" />

- Then I extruded the plate.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/3f6b06ee-c20f-4af2-a770-0487047bd2da" />

- Added 1.5 mm chamfers.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/a831e871-849e-4c8d-8f6f-112fbdd076b4" />

And with this, it was over for today's session.

Here's the lapse of today's session: [PATRA-LPS-42-D62](https://lapse.hackclub.com/timelapse/_ZJzLyDNYPNp)

**Total time spent: 4h 45m**

---

# Day 63 — 28.08.2026: Eliminating Fractional Teeth in Z Axis Tensioning System

I continued exactly where I left off yesterday.

I checked whether the Z Belt clamp lower, which I designed yesterday, had any printing risks.

<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/22fab9d7-91cb-4700-a5c4-7febf00f0f90" />

The result, sadly, wasn't in my favour. It had a printing risk. But it was solvable because the risks were with the walls in the extreme horizontal ends and along the M3 screw clearance hole walls. I went back in the timeline to when I was designing the lower clamp. Here's how I fixed it:

- I copied the tooth 5 mm away from it, placing it outside.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/231af6d5-7c76-40c2-8648-a7978753e4da" />

- Then, instead of abruptly ending the belt, I extended it 0.5 mm to the point where it reaches the other tooth.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/7860c1c1-b22e-4994-85d7-809920c7be30" />

- This made the walls thicker by 0.5 mm each side and thus the clamp longer in length, from 52 mm to 53 mm.

	<img width="1360" height="725" alt="image" src="https://github.com/user-attachments/assets/98faf182-46c3-43de-a108-9e08e7ca2133" />

- I edited the other sketch from yesterday too, extending the 52 mm length to 53 mm.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/e4d16d4f-4e81-4aff-82c0-f3d8c4d80cc1" />

- Due to this, I also had to adjust the screw hole positions.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/4cac1062-e0eb-4a65-a9b4-fa56d296979f" />

After a few more tweaks back and forth in the timeline, it was fixed.

I checked the height of the clamp and the belt.

<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/a1f519fd-8de1-4e7e-9304-5ff5327da63a" />

After I was done with the Z belt clamp, I started with the X and Y belt clamps. So, I designed a new clamp with 10 teeth, with no extra pitch in the center, the same clearance shape of 0.2 mm, 0.5 mm walls on two ends, and a 5 mm height. Then I made the clamp body the same way I did with the Z belt clamp.

But then, out of nowhere, 0.00037878 mm appeared again in the coordinates of the X axis pulley. It was normal at this point. I eliminated it again, as always, by means of translational neutralisation by moving it. I also increased the height of the end plates from 7.5 mm to 9 mm, due to the 1.5 mm belt height displacement on day #60. Besides, I did some more repetitive work: Adjusting the end plate and pulley/idler connectors for the 0.25 mm position changes.

I then created a new sketch to inspect the actual center distance for the Z axis tensioning system, and making a new belt with the updated lengths.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/566534f3-09c7-498e-b130-598b0a4be5ea" />

With the sketch completed, I extruded out a new belt.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5ec86520-7dd0-405b-904f-0f107b0535af" />

But then I made an eye-opening, clever realization: Moving the X and Y axis tensioning system pulley by 0.25 mm, and lengthening it 0.25 mm on both sides, causes the Z axis to move that much apart. Adding 0.25 mm length on both sides for the Z axis tensioning system idler and pulley renders a whole number of teeth for the Z axis belt, eliminating the fractional 500.4. Let me explain:

A GT5 profile timing belt has a tooth pitch of 5.0 mm. Because both pulleys in this system are identical (20 teeth each), the belt path is perfectly symmetrical, simplifying the standard belt length formula to: Total Belt Length = (2 * Center Distance) + (Number of Pulley Teeth * Pitch).

* Initial Geometry: The layout for this specific case dictates a center-to-center distance of 1201.0 mm, derived from a 1000.0 mm aluminum extrusion plus two half-lengths of the 67.0 mm pulley/idler cases, plus two full lengths of 67.0 mm pulley/idler cases.
* Length Calculation: This design results in a total straight section length of 2402.0 mm (2 * 1201.0 mm) and a wrapped section length of 100.0 mm (20 teeth * 5.0 mm), combining for a total belt length of 2502.0 mm.
* Teeth Consequence: Dividing this total length by the 5.0 mm pitch yields a non-integer count of 500.4 teeth, which is physically impossible for a closed-loop timing belt.

As a direct consequence of adjusting the target to a physical loop of exactly 501 teeth for this specific setup, the entire physical assembly must shift to maintain proper belt tension without slack.

* Required Length: Specifying a discrete 501-tooth belt establishes a fixed, non-negotiable total belt length of 2505.0 mm (501 teeth * 5.0 mm).
* Distance Adjustment: Subtracting the constant 100.0 mm pulley wrap leaves 2405.0 mm for the straight sections, forcing the center-to-center distance to increase to 1202.5 mm (2405.0 mm / 2).
* Structural Impact: To accommodate this wider center distance while using the same 1000 mm aluminium extrusions, the pueelys/idlers must be increased in length by 0.25 mm on both sides.

Data Summary Table

| Parameter | Configuration 1 (Previous) | Configuration 2 (Current / Consequence) |
|---|---|---|
| Belt Profile & Pitch | GT5 (5.0 mm) | GT5 (5.0 mm) |
| Pulley Teeth Count | 20 teeth | 20 teeth |
| Aluminum Extrusion | 1000.0 mm | 1000.0 mm |
| Center-to-Center Distance | 1201.0 mm | 1202.5 mm |
| Straight Section Length | 2402.0 mm | 2405.0 mm |
| Wrapped Section Length | 100.0 mm | 100.0 mm |
| Total Belt Length | 2502.0 mm | 2505.0 mm |
| Final Belt Teeth Count | 500.4 teeth (Fractional) | 501.0 teeth (Whole) |

Due to this new realization, I had to eliminate the extra 2 mm distance between the two centermost teeth in the Z belt clamp lower, next.

Here's the lapse of today's session: [PATRA-LPS-43-D63](https://lapse.hackclub.com/timelapse/EYsn6-oXwp8n)

**Total time spent: 4h 40m**

---

# Day 64 — 29.08.2026: Redesigning Clamps, Belts and Couplers

The Z axis clamp that I designed yesterday was complete in terms of design, but its position was not quite right. It is important as the position determines the thickness of the clamp and also alters the upper clamp body. Here's how I made sure that the clamp's Z axis position is exactly adjacent to the belt profile, down to nanometers:

- This is the clamp sketch for the Z axis tensioning system:

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4ef2cb31-8433-4e18-8174-b01951bbbe6d" />

- I moved the clamp up by 1.59204374 mm. I got the number from the distance between the vertices on the two bodies.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/8cb0853e-e983-4998-8c6c-fb8b0cb40aa3" />

- The clamp is now directly adjacent to the belt.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/804aff14-ebee-4b4f-ab7e-0c0746a88a00" />

- As the profile was confirmed, I executed it using extrude:

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d7e74ccf-03ce-4508-b30a-be1b5b9b1d99" />

- I used this to make a fresh new sketch for the clamp:

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/0c58daf8-482b-4e30-8a72-28c919bcb6e3" />

Next was the time for the X and Y axis clamp:

- This is the clamp sketch for the X and Y axis tensioning system:

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8a5466b4-8217-44f1-ae41-230ec3b74bd1" />

- Similar to the CA axis tensioning system clamp, I made a new sketch.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/25af2315-0b90-4c79-8a46-938a413eaae1" />

- After extruding the sketch, I have a better clamp. I also extruded 0.25 mm down to make it flush against the MGN15H linear block.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/583ee793-b448-4548-8ee3-b75ab6efb345" />

- The clamp is now directly adjacent to the belt.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8e3938d6-c808-421c-9a19-37a8e6fd0d01" />

The next part was the X and Y upper clamp:

- I had the same old sketch, which I used to create the blue-highlighted shape.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/ce6d5eab-bc9b-4e40-a7fd-d300368ddbdd" />

-  I used Split Body to cut the old upper clamp into two parts.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/9470e132-c0d6-4fca-950b-72cce8cae58c" />

- I deleted the lower part of the upper clamp and then extruded the highlighted sketch and joined it with the upper clamp's upper part.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/4ac4dd06-2ae3-47bc-83da-2ed06babaaee" />

- The distance between the ceiling of the upper clamp and the trench of the lower clamp is supposed to be 4 mm, but even here there is a problem of nanoscopic dimensional error.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/4134cb41-ed34-49d0-9265-0134b591754d" />

- I extended these two highlighted parts and connected them to the upper belt clamp.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/205b6688-a1c8-4d15-a7d0-bb6841c533c3" />

This is how the upper clamp for the X and Y tensioning system looks from below. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a96bec37-a382-4819-98ea-2f13add993a5" />

On day #62, I had modeled a new plate for the Z axis upper clamp, but today, on a closer inspection of the dimensions, I realized that it was not symmetrical in shape. I also had to redo the holes because I changed the hole positions for the X, Y, and Z axis lower clamps.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/fa58e3b7-95ce-4c2f-857d-29c80ed20828" />

To fix the symmetry, I have used the mirror tool. And after applying the chamfers in the same fashion as I did on the #62, this is what it looks like:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c6a5c3db-439d-4707-a488-43d181cddb18" />

After the plate was done for the Z axis, I also modeled with the exact same dimensions for the X axis as well, just making sure that there is no shape bridging the gap between. After extruding it and applying chamfers in the same fashion as I did in the step before, this is what it looks like:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9feabea5-0bb1-4f1e-94f1-75640173d7c1" />

But even at this point, the X axis belt had no teeth, so I projected two teeth onto the existing X axis belt profile. Here's how I added the teeth:

- I first extruded out a single tooth.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/b165b081-fb7f-4df2-9fb4-a30353b46a4a" />

- Then, using Pattern on Path, I copied it at a distance of 2256.938-5 449 times.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/769c5f93-f315-4e68-9cae-4a015d26fa13" />

- Using the Combine tool, I combined the teeth and the belt into a single body.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c978cd91-e8f8-4ead-936d-0f65363cb2c9" />
	
With this, the Z axis tensioning system belt is done. And this is what the entire KBM looks like:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/20f7fb46-314c-4223-b924-d7eea1c00760" />

Next, I addressed a few things I had forgotten:

1. **Length of the 2020 extrusions:**  I hadn't updated the length of the 2020 extrusions. As the pulley/idler cases were 0.5 mm longer (0.25 mm on each side), this added a distance of 0.5 * 2 = 1 mm to the overall length of the 2020 extrusions. The extrusions were previously 1134 mm, which now became 1135 mm. I extruded 0.5 mm on each side of the extrusions.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d3dfb058-2dcb-451e-b808-ba501c0d77ed" />

2. **Height of the parts inside the Z axis pulley/idler cases:** One more thing that was left out was the height increase of 1.5 mm for the parts inside the Z axis tensioning system pulley/idler. Using the Move tool, I moved the parts like washers, bearings, pulleys, and idlers 1.5 mm up.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5c625372-7819-4272-9c8c-d56ff8e6324c" />

3. **Remodeling the Z axis tensioning system couplers:** This is something which I had in my mind. There were numerous dimensional errors in the coupler, even though it looked flawless. To fix it, here's what I did:

- I created a new sketch on the 2020 extrusion face.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3888fa2d-c772-4ec6-805f-54555c65ec72" />

- Cut a 12.5 mm deep hole into the two sides of the case.

	<img width="1365" height="730" alt="image" src="https://github.com/user-attachments/assets/a42005c5-55ae-499d-b46f-37c259444802" />

- From the sketch, I first extruded the four connectors. 

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/e50bb28a-6a81-445b-ac01-c4fe9c3cdf9b" />

- Then the flat part of the U-shaped part.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/a8ebf1b6-5b93-480b-83e5-86666a483117" />

- And then, finally, the walls of the U-shaped part.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/6d9c2a88-3305-45d0-b461-a824e50fbc71" />

- I combined the whole part. 

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/3a919c2b-9f1b-4297-8400-f11ff56c30ba" />

- Added camphers.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/43c15c1e-b728-46a5-93e4-605c363ee433" />

- Added fillets.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/7fed0940-582e-446d-9402-0719e6e23867" />

- Added hoes using extrude cut.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/b57235d0-094d-4256-b378-4bcd6510498b" />

- Then I finally added threads.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/facb5ace-16e9-4e2e-9a41-e26359ad095c" />

With this, I successfully modeled a dimensionally correct coupler for the Z axis sensing system.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/61f023a8-d6f0-4b1d-ab64-4a381d87f827" />

After this, I added the holes in the correct position based on the coupler on the pulley case and added chamfers for the countersunk screw. This is how it looks with the pulley case:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/295db8a9-c47f-4fe8-b13e-d9d9cc9aab38" />

I had forgotten to add clearances, so I added them:

1. Coupler: I forgot to add clearance before. I added 0.2 mm clearance.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/1c85f1b1-0a71-4f86-9490-ac86aad441b6" />

2. Shaft Adapters: Previously, it was 0.4 mm diameter clearance. I changed that to 0.2 mm.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/fd791189-7ed5-4ac4-9303-ddd258b8bc0f" />

3. Bearing Covers: For some reason, their diameters were randomized. So, ensuring a diameter clearance of 0.2 mm, I made the outer diameter 39.8 mm.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/bd27fe44-f102-40b1-b8c6-e84f56129bd4" />

It was then time for the Z axis belt. Here's how I modeled it:

- I created a new sketch with the projected Z axis pulley/idler, and a 1202.5 mm long, with a 31.8309886 mm diameter. 

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/82fe0d0c-6ee9-4843-9b7a-53d3a25ee60f" />

	The diameter was calculated from the formula 20 * 5 / pi, where 20 is the number of teeth, and 5 is the pitch.

- I used the slot to draw a 3.8 mm thick belt, with one slot 1.9 mm larger in diameter and the other 1.9 mm smaller.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/170ebf60-a2ee-4b88-a1ca-040715dec493" />

- Then I extruded the sketch 15 mm wide.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1710a2cf-074d-4c51-9a36-8fb97f60fc68" />

After positioning it 1.5 mm up, adding the teeth in a similar way I did today with the Z belt, and Appearance, this is how the belt looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/bc933f7a-2b32-4f7f-b8b1-e4aebe6f0634" />

Lastly, I added fillets for the exit point edges in the peulley/idler cases in all tensioning systems.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7e8b484d-3cac-4065-8dbc-05f780bdfde2" />

Here's the lapse of today's session: [PATRA-LPS-44-D64](https://lapse.hackclub.com/timelapse/zQO9Jc_WOjpT)

**Total time spent: 6h 20m**

---

# Day 65 — 30.08.2026: Optimizing the Design for the Lengthened Pulley/Idler Cases

Now it was time to also update the Z axis belt, as I was successful in eliminating the decimal belt tooth for the Z axis as well. Due to my previous decision to increase the length of the pulley and idler cases by 0.25 mm on both sides, things got better.

A GT5 profile timing belt has a tooth pitch of 5.0 mm. Because both pulleys in this system are identical (20 teeth each), the belt path is perfectly symmetrical, simplifying the standard belt length formula to: Total Belt Length = (2 * Center Distance) + (Number of Pulley Teeth * Pitch).

* **Before:** The layout for this specific case dictates a center-to-center distance of 1201 mm, derived from a 1000.0 mm aluminum extrusion plus two full lengths of the 67 mm pulley/idler cases, plus two half-lengths of 67 mm pulley/idler cases.
	* **Length Calculation:** This design results in a total straight section length of 2402 mm (2 * 1201 mm) and a wrapped section length of 100 mm (20 teeth * 5.0 mm), combining for a total belt length of 2502 mm.
	* **Teeth Consequence:** Dividing this total length by the 5 mm pitch yields a non-integer count of 500.4 teeth, which is physically impossible for a closed-loop timing belt. This is the reason why I had to add a distance of 0.4 teeth (2 mm) between the two middle teeth of the clamp.

* **After:** This became a center-to-center distance of 1202.50 mm, derived from a 1000.0 mm aluminum extrusion plus two full lengths of the 67.5 mm pulley/idler cases, plus two half-lengths of 67.5 mm pulley/idler cases, as I increased the pulley/idler case distance by 0.25 mm on both sides (0.5 mm total).
	* **Length Calculation:** This design results in a total straight section length of 2405 mm (2 * 1202.50 mm) and a wrapped section length of 100 mm (20 teeth * 5.0 mm), combining for a total belt length of 2505 mm.
	* **Teeth Consequence:** Dividing this total length by the 5 mm pitch yields an integer count of 501 teeth, which is physically possible without adding any distance between the last and first teeth for the clamp.

**Data Summary Table:**

| Parameter | Configuration 1 (Previous) | Configuration 2 (Current)|
|---|---|---|
| Belt Profile & Pitch | GT5 (5.0 mm) | GT5 (5.0 mm) |
| Pulley Teeth Count | 20 teeth | 20 teeth |
| Aluminum Extrusion Length | 1000 mm | 1000 mm |
| Center-to-Center Distance | 1201 mm | 1202.50 mm |
| Straight Section Length | 2402 mm | 2405 mm |
| Wrapped Section Length | 100 mm | 100 mm |
| Total Belt Length | 2502 mm | 2505 mm |
| Final Belt Teeth Count | 500.4 teeth (Fractional) | 501 teeth (Whole) |

This meant that I no longer needed the clamp with a 2 mm gap in the middle. To achieve 501 teeth, I just needed to buy more teeth belt and then cut it. Here's the process I followed to eradicate the 2 mm gap in the middle:

1. I split the existing Belt Clamp Bottom Z in half using XZ plane to reveal the inner belt grooves after moving it.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3fc2a1b4-098c-4335-8985-3152be917379" />

2. Created a sketch on the split part and copied the groove next to the groove before the gap at a 5 mm pitch.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/afa09fcc-664c-4a9e-bd8d-90df8251b7d3" />

3. Extruded the right part of the sketch to create a new face for the extrusion cut.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4e054cdd-bfaa-4729-834c-0f84c124fe5d" />

4. Extruded and cut the gap in the body.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4089b63d-cedc-41a4-bfdc-369a512a7193" />

5. Moved one part and merged it into a single body using the Combine tool.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7af6abe7-c9c6-40cd-ab7b-63d953b41a37" />

6. Mirrored the part using the XZ plane to create this.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d9a4029e-3c95-4012-bb50-c567ce74ed24" />

The next thing I have to work on is the End Plate holes. The section analysis shows that the holes have stayed as they are, but as I increased the length by 0.25 mm on both sides of the pulley/idler case, the holes look like they shifted back.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/633a13cd-c356-4293-b3fb-3624fe6fe2fd" />

To fix it, here is what I did:

1. Split the body near the middle using a construction offset plane and then moved a part 0.75 mm outwards.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f8907e7b-f54b-4b71-8ba6-a295c2569dd2" />

2. To keep the total length unchanged, I moved the faces at the end of the plate back by 0.75 mm.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c074d0b2-73d9-46c4-87a2-d4d907055c5b" />

3. I then joined the parts by bridging the gap using the Extrude tool.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1e322d4f-ca63-4bb3-8610-991584892d63" />

4. I split the other part of the body as well due to misalignment.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/c3b7790e-0d80-4497-b49b-6410aee62873" />

5. Moved it 0.25 mm away from the body to align the hole.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7d4b8ea9-118c-4463-8ddf-05dc89c0e35c" />

6. Bridged the gap using extrusion.

	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/f4cde3e3-9be8-4c9d-915b-5a45bce1d9fd" />

Following this, I mirrored the geometry to the other end plate and connectors. I also renamed some components in the Browser and checked the positions of the vertices in the design, especially in the end plates.

This is the overall look of the Kinematic Base Module.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/de7ee697-6b7c-441a-9f45-b099a7fd837f" />

Here's the lapse of today's session: [PATRA-LPS-45-D65](https://lapse.hackclub.com/timelapse/5henxAHdVGoH)

**Total time spent: 3h 15m**

---

# Day 66 — 31.08.2026: Confirming Parts & Fixing End Plates

I had almost completed designing the Kinematic Base Module (KBM), so it was the perfect time to go over the BOM and confirm all the components one by one.

But before that I wanted to verify if the way I designed the system is conventional or not, and also know what more things are needed in the system. I came across [this](https://www.machinedesign.com/mechanical-motion-systems/linear-motion/article/21834576/how-to-design-a-linear-motion-system) article, on "How to design a linear-motion system"

After reading that a little, I went to Fusion to confirm the parts of the KBM (excluding the prints):

1. **LCF6-2020-1135 Aluminium 2020 T-Slot Profile Extrusion**
   * Quantity: 2
   * Unit Price: ₹306.45 / \$3.24
   * Total Price: ₹612.90 / \$6.49
   * Vendor: MISUMI
   * Link: [Product Page](https://in.misumi-ec.com/vona2/detail/110311047509?HissuCode=LCF6-2020-1135)
   
   <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/94be776d-6d84-4284-af5a-197fdc3fb140" />

2. **HFS5-4040-1000 Aluminium 4040 V-Slot Profile Extrusion**
   * Quantity: 2
   * Unit Price: ₹2,595.20 / \$27.47
   * Total Price: ₹5,190.40 / \$54.93
   * Vendor: MISUMI
   * Link: [Product Page](https://in.misumi-ec.com/vona2/detail/110302684530?HissuCode=HFS5-4040-1000)
   
   <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/9d85ff4f-0771-4d1c-a127-773dea816ec4" />

3. **MGN15H Linear Guide Rail 1m**
   * Quantity: 2
   * Unit Price: ₹2,729.00 / \$28.88
   * Total Price: ₹5,458.00 / \$57.76
   * Vendor: Robu
   * Link: [Product Page](https://robu.in/product/mgn15h-linear-guide-rail-1m-2)
   
   <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b952b04e-0f70-4246-bddd-4552fc0ffefd" />

4. **MGN15H Sliding Block**
   * Quantity: 4
   * Unit Price: ₹679.00 / \$7.19
   * Total Price: ₹2,716.00 / \$28.74
   * Vendor: Robu
   * Link: [Product Page](https://robu.in/product/sliding-block-for-mgn15h-linear-guide-rail)
   
   <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/31c85b91-9b5f-49bc-8718-06b7929c3ac6" />

5. **Belt E-GBN22505GT-150 (X & Y)**
   * Quantity: 2
   * Unit Price: ₹1,225.63 / \$12.97
   * Total Price: ₹2,451.26 / \$25.94
   * Vendor: MISUMI
   * Link: [Product Page](https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN22505GT-150)
   
   <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/94d2fe0a-72d2-4dea-b9f4-67de51758d4c" />

6. **Belt E-GBN26005GT-150 (Z)**
   * Quantity: 1
   * Unit Price: ₹1,400.77 / \$14.82
   * Total Price: ₹1,400.77 / \$14.82
   * Vendor: MISUMI
   * Link: [Product Page](https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN26005GT-150)
   
   <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ea9154e6-7268-4b6f-8c10-bb00d705352c" />

7. **Pulley & Idler CBYL-AH1-5GT150-22-A-N-d12 (X & Y)**
   * Quantity: 4
   * Unit Price: \$3.03
   * Total Price: \$12.12
   * Vendor: JLCMC
   * Link: [Product Page](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-22-A-N-d12&productModelNumber=CBYL-AH1-5GT150-22-A-N-d12)
   
   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5cd33405-bd61-458d-a9bf-d73182a85774" />

8. **Pulley & Idler CBYL-AH1-5GT150-20-A-N-d12 (Z)**
   * Quantity: 2
   * Unit Price: \$3.00
   * Total Price: \$5.99
   * Vendor: JLCMC
   * Link: [Product Page](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12)
   
   <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/af8a6dbe-b803-4574-8b4b-a7b754034eed" />

9. **6901ZZ Bearing (Pack of 4)**
   * Quantity: 3
   * Unit Price: ₹239.00 / \$2.53
   * Total Price: ₹717.00 / \$7.59
   * Vendor: Robu
   * Link: [Product Page](https://robu.in/product/6901zz-bearing-12x24x6-shielded-miniature-ball-bearings-4pcs/)
   
   <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b6638145-4234-41d6-a94f-33abda147f93" />

10. **Rtelligent T60S Closed-loop Stepper Motor Driver (X, Y & Z)**
    * Quantity: 3
    * Unit Price: ₹3,549.00 / \$37.56
    * Total Price: ₹10,647.00 / \$112.68
    * Vendor: Robu
    * Link: [Product Page](https://robu.in/product/rtelligent-t60s-closed-loop-stepper-driver/)
	
	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/210f67e1-373d-4121-af42-0cd852787129" />

11. **Rtelligent 57AM23ED 2.3 Nm Closed-loop Stepper Motor (X & Y)**
    * Quantity: 2
    * Unit Price: ₹4,079.00 / \$43.17
    * Total Price: ₹8,158.00 / \$86.34
    * Vendor: Robu
    * Link: [Product Page](https://robu.in/product/rtelligent-57am23ed-closed-loop-stepper-servo-motor/)
	
	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/93a5788a-c388-4ec2-baee-388f59166f1d" />

12. **Rtelligent 57AM30ED 3 Nm Closed-loop Stepper Motor (Z)**
    * Quantity: 1
    * Unit Price: ₹5,399.00 / \$57.14
    * Total Price: ₹5,399.00 / \$57.14
    * Vendor: Robu
    * Link: [Product Page](https://robu.in/product/rtelligent-57am30ed-closed-loop-stepper-servo-motor/)
	
	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/097f4819-3550-4bcd-8511-ec3f06ca40c4" />

Then I made two major changes to the BOM:

1. **Added Cost as INR with Updatable Exchange Rate:** As we all know, there are huge fluctuations in the USD-INR exchange rate; it was not sensible to change the INR to USD when I added them to the BOM and wrote the price down. A better way is to actually write the price in INR if prices are in INR, and use the value of a certain cell to divide it by the exchange rate. This can be done by keeping a cell with the USD-INR exchange rate and then updating the value if needed.

2. **Added Parent-Components in each Module:** It was getting really confusing with so many parts, so I added the parent components (like Tensioning Systems, TriTeron Tool Head) just below the module components (KBM, TRM, RAM) in the BOM. This improved the overall structure and introduced the existing hierarchy of Fusion in the BOM as well, making it easy to look at components for sourcing. But one important thing to note is that there are no "Fasteners" in the Fusion design, but I have added them in the BOM.

Here is the hierarchy of KBM for clarification:

- **Kinematic Base Module (KBM)**
	- Aluminum Extrusions
	- End Plates
	- Linear Guides
	- Tensioning System
	- Motors

I don't know if I have mentioned this before or not, but this is based on the assembly sequence I imagined in my Cerebrum. First the extrusions, then end plates, then linear guides, then the tensioning systems, and then finally the motors.

Next, I wanted to add all the 3D print files in the design from top to bottom (as in Fusion Browser). As there were no 3D print files in the Aluminum Extrusions, I was about to start the confirmation directly from End Plates, but then I noticed a slight mistake in the model and made a clever realization after my model got flagged for Printing Risk in JLC3DP.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/976b0b3e-e5ce-4950-9781-f975f75a915e" />

The reason was the threads. The thread geometry was unprintable or something that made JLC3DP flag it as a printing risk. I also realised that even if it had no risk, it is still problematic as cross-threading is possible. This is because there are threads inside the pulley/idler cases and the end plates, which may not line up exactly and cause cross-threading.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/638046b6-1eb7-4b91-a038-f78c38cd407e" />

Most of the warnings were gone, but one remained, which was under the part that connected the 2020 extrusion. It was off-ground, so I fixed it.

I thus decided to completely get rid of threads in the holes and instead use clearance holes for the screws. But first I deleted all the holes so that I could check if the problems actually were the threads, and not something else. I can redo them using extrusion cut in a clean way.  But before that, I decided to use inserts for the pulley/idler cases, instead of adding modeled threads on the design, which is unreliable. Since I thought of printing in SLA Resin, I had to use cold-pressed inserts with 0.1 mm radial clearance so that I could superglue them into the right places.

This is the original sketch:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/890f444b-4278-40e0-b319-3777153857f1" />

Here's what I did next:

- I extruded the original holes that existed before I modeled threads, and then added 0.8 mm radial clearance, after briefly going through [this](https://jlc3dp.com/help/article/3d-printing-design-guideline).

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/923a9d0f-f823-4506-b20e-91e678d73a29" />

- I also noticed that part of the end plate was mistakenly deleted, so I also fixed it.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4791a6f6-455b-46f4-87c3-a8997c272d3a" />

- Next, I added a 0.2 mm offset to the diameter of the holes.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6a9dbbbe-218e-4390-8451-32d34afdb2c4" />

- Then I extruded them down to make the clearance holes for the end plate.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/54bfa464-3fee-4f68-868b-ad645548d230" />
	
- Then I added the chamfers for the countersunk screws next.

  	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/866a8b5e-a9e0-4752-a055-a1357be42229" />
	
Then it was time to check if my hard work had paid off. And yes, it did. No printing risk.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/43869b88-8637-4f9e-8abc-4c2a20d88d2c" />

I finally had the estimated price for printing the end plate along with other parts. So, I updated the BOM after arranging the components in the browser.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/636c457b-9c66-43e9-a51c-a019dfdca443" />

I had forgotten to add clearance to belt clamps, so I added that as well.

Haste indeed makes waste. In my excitement and overconfidence, I sent the model to print without checking it.

<img width="1280" height="960" alt="WhatsApp Image 2026-09-13 at 10 48 07 AM" src="https://github.com/user-attachments/assets/e21ba9be-f2d3-4fe3-882d-ab3f572daa50" />

The print came out perfect, but I actually exported the design when my timeline cursor was behind the latest two features. Due to this, the clearance holes were uneven, and there were no chamfers.

But it was not all bad, as I learned that 3 mm was too tight for an M3 screw, practically, as some holes were 3 mm and some were 3.4 mm. The ones with 3.4 mm holes were perfect. I had some 2020 aluminum extrusions from an old Creality Ender 3 printer. I used it to see if the part fits. And it actually did very well.

Here's the lapse of today's session: [PATRA-LPS-46-D66](https://lapse.hackclub.com/timelapse/r_Kl-JPTx5vg)

**Total time spent: 4h 00m**

---

# Day 67 — 01.09.2026: Completing the Linear Block & Updating the BOM

I started by completing the design of the X and Y belt clamp. There was no locking mechanism or clearance. There was an unnecessary 0.25 mm gap between the clamp and the upper middle face of the MGN15H linear block. To fix all of that, here's what I did:

- Added a locking mechanism to ensure no 0.25 mm gap between the clamp and the linear block.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/63e7bf58-132c-4b3d-a89d-ecbe750208c5" />

- Added clearance to that part to ensure seamless fitting.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d6d76be6-c6f3-4be0-af26-e1c6fc9cbaf0" />

- Made the belt geometry symmetrical using split body and mirror.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ebf9980d-f51b-45fd-968c-795d63d2bce3" />

- Added clearances to the internal edges of the upper part of the belt clamp.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4562ed4b-9d42-426d-85a4-b21ba3928946" />

- Added clearance to the edges of the lower clamp block.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/eb6c9f94-509c-4f38-aa27-85cd761f7d2e" />

- Added clearance on the vertical belt stackup.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/291ecde7-881d-45ad-87d4-4079afefe5a1" />

With that done, the full linear block was completed and ready for fabrication. I checked in JLC3DP if there was any printing risk in my design of the lower clamp block.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/efd8acf3-39b2-4127-ae24-260a4bb27f25" />

This is how it looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f610c78b-6f24-47b8-8f08-62cdf19eece0" />

To proceed with completing the BOM of the KBM, I exported the other 3D models and uploaded them to JLC3DP to check the cost and see if they have any printing risk.

- First, there were the pulley and idler case (left and right) and bearing cover. Both sides of the case had printing risk. I updated the BOM.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/71c10bb4-040a-4785-accc-478c865835c4" />

- Second, there were belt shields, pulley shafts, idler shafts, and a coupler. Only the coupler had printing risk. I updated the BOM.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/57c5acc5-2af0-49e4-9a68-7a29c45975e7" /> oh no. risk

Here's the BOM so far:

<img width="2817" height="752" alt="image" src="https://github.com/user-attachments/assets/81d182ab-ad73-42ce-b924-18b04dd7f026" />

And, well, this is getting really expensive. I really need to optimize in the next few days.

Here's the lapse of today's session: [PATRA-LPS-47-D67](https://lapse.hackclub.com/timelapse/FNw_Cs9I_1ax)

**Total time spent: 3h 20m**

---

# Day 68 — 02.09.2026: Updating BOM & Cost Cutting

The KBM was getting really expensive. But that's not a big problem itself; the fact that the Forge won't pay my customs was, in itself, a nightmare. My total cost of imported merchandise from Jialichuang had already reached **$110.16**. This meant that the total CIF value, including shipping, would have significantly more import duties and GST. Thus landing the digits of the customs amount in a crazy territory.

Thus, I started with cost-cutting. The first thing that I eliminated was the **WSX-SUS-M12X18-5** Washers that cost ₹243 each. I needed 12, so it was around $30, which was getting way too expensive. I thus decided to print them, as I was just using them for spacing.

But after exporting them and importing them into Orca Slicer, the default orientation was upright, but it didn't look promising. So, I printed one laid down and one upright.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0b5296af-2f47-47ab-bd88-748a1fb90472" />

This is how the print came out for the sample.

<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/f6765e2c-f082-4acd-8ba1-5e5e0f87c27a" />

Obviously, I was going to choose the laid-down design over the upright one, so I arranged it like this and hit print.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/227e2567-d009-4843-9684-7ea8b20f0a40" />

This is how the print came out:

<img width="1280" height="960" alt="image" src="https://github.com/user-attachments/assets/b05e6913-573f-4f36-816c-25fd8dcd28a7" />

Next I noticed that the BOM for the KBM was still not complete as the Fasteners were yet not added in the BOM. Here's what I added:

1. **M3 x 12mm High Tensile (12.9) Black Oxide Grub Screw**
	* Quantity: 30
	* Unit Price: ₹2.00
	* Total Price: ₹60.00 / $0.63
	* Vendor: OnlyScrews
	* Link: [Product Page](https://onlyscrews.in/products/m3-x-12mm-high-tensile12-9-black-oxide-grub-screw-dia-3mm-length-12mm)
	
2. **M3 x 12mm Hex (Allen) CSK SS 304 Screw**
	* Quantity: 25
	* Unit Price: ₹1.80
	* Total Price: ₹45.00 / $0.48
	* Vendor: OnlyScrews
	* Link: [Product Page](https://onlyscrews.in/products/hex-allen-csk-m3-x-10-screw-pack-of-20?_pos=1&_sid=1040a6d00&_ss=r)
	
3. **M5 x 10mm Hex (Allen) Socket Head High Tensile (12.9) Black Oxide Screw**
	* Quantity: 15
	* Unit Price: ₹2.40
	* Total Price: ₹36.00 / $0.38
	* Vendor: OnlyScrews
	* Link: [Product Page](https://onlyscrews.in/products/m5-x-10mm-hex-allen-socket-head-high-tensile12-9-black-anodized-screw)
	
4. **M3 x 5mm 3D Printing Brass Threaded Slant Knurled Insert**
	* Quantity: 40
	* Unit Price: ₹4.60
	* Total Price: ₹184.00 / $1.95
	* Vendor: OnlyScrews
	* Link: [Product Page](https://onlyscrews.in/products/m3-x-5mm-3d-printing-brass-threaded-inserts-dia-3mm-length-5mm)

This is the part updated in the BOM:

<img width="2784" height="106" alt="image" src="https://github.com/user-attachments/assets/f4d2e798-b4a7-4e11-9c17-e9e46b51624f" />

After that, I made a big change in the BOM by introducing a column for physical materials. This was necessary especially for the 3D-printed parts, where I mention the material along with the printing technology like SLA, MJF, or FDM.

To further cut down costs, I reconsidered my choices with the [Rtelligent T60S Closed-loop Stepper Motor Driver](https://robu.in/product/rtelligent-t60s-closed-loop-stepper-driver/), asking Google AI mode if it was overpriced. I decided to keep it because I realised I couldn't cut down on that.

Then what came to mind was the SLA prints. I wondered if local SLA printing would be cheaper or not. So, I went to [Robu](https://robu.in/product/sla-3d-printing/) to see it myself. And the price was absolutely crazy: **₹3833 (over $40)**. JLC3DP with added shipping and customs will be cheaper than this.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/aa3770c9-d536-4aed-9b2e-6c532acfc268" />

Here's the lapse of today's session: [PATRA-LPS-48-D68](https://lapse.hackclub.com/timelapse/DT-okZpcwg7Q)

**Total time spent: 2h 10m**

---

# Day 69 — 04.09.2026: Cost Optimizing & Updating the BOM

In order to further reduce the cost of goods being imported from Jialichuang, I have decided to replace all the unnecessary SLA resin prints with FDM prints with materials ranging from PLA+, PETG, to PA.

This decision was made primarily because each half of the 6 Pulley/Idler Cases cost $6 each, without customs. This totaled a whopping $72 ($6 * 2 * 6), just like that, even without customs added. My first and foremost instinct was to use my own printer. This meant that I would now have to readjust several things in the model before I upload the same models to my Slicer and hit print.

1. **Bottom M3 Screw Hole Clearances:** As they are being replaced by heat set inserts from the previous cold pressed ones, changes are needed. SLA prints need cold-pressed inserts and thus need +0.2 mm clearance. Even though the inserts themselves are the same, I will have to reduce the clearance from +0.2 mm to -0.2 mm. Therefore, I will have to decrease the diameter of the holes by 0.2 mm - (-0.2) mm = 0.4 mm. I am using [this](https://onlyscrews.in/products/m3-x-5mm-brass-threaded-inserts-dia-3mm-length-5mm) brass insert from Only Screws.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0c026903-2227-4ac1-8419-1b6eb2f6eb5d" />

2. **M5 Screw Holes Depth:** There were 4 M5 screw holes for each motor. As I can't print the threads reliably, I will have to use Brass threaded inserts for the holes. This part is a bit tricky as I can't use the Nominal diameter * 2.5 thread rule, as the deepest I can go is 11 mm (instead of 12.5 mm), due to geometric constraints. But there are no 11 mm brass inserts, so I had to choose to make the hole 10 mm deep instead of 11 mm.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/eff1173d-03b3-4648-8ffd-c164c51a6427" />

3. **M5 Screw Holes Clearances:** As I need heat-pressed inserts, I set the hole diameter to 6.2 mm. Previously, there were M5 threads modeled here. I am using [this](https://onlyscrews.in/products/m5-x-10mm-brass-threaded-inserts) brass insert from Only Screws.
   
<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3d45c192-92d9-40dc-ade5-ba8f7d3a1a20" />

4. **Side M3 Screw Hole Depth & Clearances:** These holes are for securing the two sides of the case. I first deleted all the holes, then I created 

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/87211425-3e41-48ce-8704-028d6cf020f6" />

5. **Side M3 Screw Hole Chamfer (Side):** I set the chamfer for the holes at 1.4 mm depth and width.
	
	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/327ac6a7-bba5-416a-a9ac-1fc9670142ad" />

My designs commonly incorporate countersunk screws; I have relied mostly on AI replies. I just realised that this little mistake can ruin all my prints that incorporate chamfers. I am always confused about the chamfers, so this time I thought of sketching the screw and screw hole cross-section in Fusion. Then, later printing a sample screw hole, of the most sound design.

I made three holes side by side:

* Two with the settings I have been using and had used, respectively. One with the optimized design.
* Two of the three designs failed. Only the optimized one passed.

I revolved the trustworthy design to make a 3D body.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1c8cdce6-da1a-4728-97bb-3ae3c5cae3f8" />

And it was time to put it to the test by printing it.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8ccf40a1-aa2f-4e6d-bf39-80cb93666d56" />

This is what the cross-section looks like.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/023288c2-15b8-4cc9-aa49-08c31c06ab55" />

And well, this is how the print turned out. Flawless fit, but the screw sticks out less than a millimeter, which is not good. I need it to be completely flush against the surface. The design won't work if I stack flat surfaces on the screws. Unless I:

1. Change the chamfer width and depth of the outer edge of the countersunk screw.
2. Move the chamfered face down by, say, 0.5 mm, or a different number. This can make the total screw length more tricky.
3. Add a little hole on the smooth-surfaced parts that directly sit on the holes where the screw head sticks out.
4. Drop chamfered screws and use more predictable button head screws like [this](https://onlyscrews.in/products/hex-allen-button-head-m3-x-6-screw-pack-of-20), by modelling 90-degree hubs for screws.

I am still not sure about this. I will have to research each one and, more importantly, try each one.

Moving on from confusion, I chose the filament material after doing a deep dive into the pros and cons of different 3D printing materials.

During the research, I sliced the pulley cases to have a rough cost estimate on printing with PETG.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e004ea60-b0db-4da9-a6b3-1b5386536966" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4ee16ed2-3c75-40fd-ac11-cd370a1acd38" />

This is what I can conclude.

Direct Comparison Overview

| Feature | MJF PA12 | HP NylonFDM PA Nylon  |
| --- | --- | --- |
| Mechanical Properties | Isotropic uniform strength across X Y Z axes | Anisotropic weak Z axis layer adhesion  |
| Dimensional Accuracy | High precision 0.3 holds tight tolerances easily | Poor prone to shrinking and warping during printing  |
| Surface Finish | Smooth uniform and slightly granular excellent for teeth | Layer lines present requires post processing for tight fits  |

I looked at PA-CF, PLA-CF, PETG, PETG-CF, and finally chose PA Nylon. I then added the dev board and power supply to bring the BOM closer to reality. The electronic components I added are as follows:

1. **[Teensy 4.1 Development Board](https://robu.in/product/buy-teensy-4-1-development-board/) from Robu:** It costs ₹ 3,549.00 ($37.56 that time).
2. **[Mean Well LRS-600-48v](https://www.tradeindia.com/products/lrs-600-48v-meanwell-power-supply-c10893421.html) from Trade India:** It costs ₹ 3,802.00 ($40.24 that time).

This is how the updated BOM looks:

<img width="3018" height="1458" alt="image" src="https://github.com/user-attachments/assets/b0e52a02-31fa-4f99-9fc7-f26f2f7451c9" />

Here're the lapses of today's session: [PATRA-LPS-49-D69-1](https://lapse.hackclub.com/timelapse/XvbWNlTVEHHK) and [PATRA-LPS-49-69-2](https://lapse.hackclub.com/timelapse/zQSr7ZLNBH7M)

**Total time spent: 3h 45m**

---

# Day 70 — 05.09.2026: Cutting Down Cost, Drawing Z Axis Leg Lower A & Journaling

Let's pick up where I left off: Further cutting down the cost of the Kinematic Base Module (KBM), and especially the goods being imported from Jialichuang.

The first thing that came to my mind was unnecessary SLA Resin prints. I decided to print every part in PLA, PLA+, PA6/PA-CF, or PETG, which are not being printed in MJF PA12S-HP Nylon. MJF PA12S-HP Nylon possesses multidimensional (isotropic) strength. Unlike traditional 3D printing technologies (like FDM), where parts are significantly weaker along the vertical Z axis (linear or directional strength). Only the small crucial parts like the belt clamps, motor shaft adapters, etcetera, need isotropic strength and thus will be printed in MJF PA12S-HP Nylon. But a point to be noted is that I will still choose SLA resin printing for the Belt Clamp tops, as they are complex to print and need supports, which can cause a not-so-smooth surface, which is somewhat crucial. Additionally, they are not that expensive.

I noticed that there were 4 Belt shields, each 0.5 meter in length, for two 1 meter long Belt Sheild Groups. I further divided them to a length of 250 mm using a split tool.

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/83fa5b1b-1ca0-48a9-9017-f441573a8a7f" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/460a0f78-bd26-420e-b05d-a38ccea5ef01" />

I did that to make sure they are printable in my Elegoo Centauri Carbon using PLA/PETG. I will then apply PTFE-coated Teflon Tape on the surface to prevent belt wear, as the clearance is less than 1 mm.

I immediately checked the print cost and print time in Orca Slicer, which came to be $2.34 and 2h41m, respectively. I was just about to print them when I realised I had to toggle the settings for a strong and smooth print. I thought that I could do it later, after the 4040 extrusion arrives, so that I can check the clearances in a shorter stretch of, say, 100 mm, not 2000 mm, which would be the case if I printed them. 

<img width="1365" height="730" alt="image" src="https://github.com/user-attachments/assets/e839fcf1-6dd1-4204-ae9f-4e3ff29e5f92" />

One more important change I made to the BOM was that I wrote down the budget for each section. Here's a breakdown:

1. Kinematic Base Module (KBM): $400
2. TriTeron Robot Module (TRM): $200
3. Electronics: $350
4. Shipping & Taxes: $50

This keeps my total budget for the prototype at exactly $1000.

This is the BOM so far:

<img width="2959" height="1458" alt="image" src="https://github.com/user-attachments/assets/70275b56-e7da-4222-a422-f5aad281fd6f" />

Then I suddenly remembered that I had to make a drawing. Here is some context:

On **02.09.2026**, I had a talk with my school director. I told him about my project and briefly explained to him what I was doing. I asked him if he had anyone in his contacts who was in the CNC machining industry and could give me a quote on a sample part. I told him that I needed CNC machining for my project, and all the options in India were extremely expensive. The options from China were also expensive, with the added customs. He called someone who was in the CNC industry before me. The conclusion was the fact that I will have to provide them with a technical drawing of the part which was to be machined in aluminium.

The last time I made a drawing for a part was back in September 2025, which was for my [V1 solenoid engine](https://github.com/SunritHazra/VX-Solenoid-Engine/blob/V2-Solenoid-Engine/V2-Solenoid-Engine-Journal.md#292026---retrospective-journal-entry--v1-solenoid-engine). It was not that big of a deal because the parts were extremely simple to manufacture, and they did not require CNC machining. Instead, they just needed lathe machining.

This time, the thing I had to create a drawing of was much more complex, and I was really excited about this. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d2559781-66c2-4b67-a705-e5e6450f2ba5" />

I started simply by opening the design and creating a new drawing where I imported the leg, and then I started with the projected views from the base view of the leg. But then I noticed that the thing I imported for the drawing came oriented as in the design. At that time, I did not know how to orient it flat, so it seemed like the best option was to do something else to lay it flat in a design.  I continued by duplicating Z Axis Leg Lower A into a new design and using the Arrangement Tool to place it flat on the XY plane.

Here's how I made the drawing:

1. I first created a new drawing using Automated Drawing.

2. Then I added another base view in Home orientation and deleted the generated ones.

3. Changed the base view orientation to Top.

4. Projected 4 views all around the parent view.

5. Added a new projected view for the 3d view.

6. Chose ordinate dimensions 35 of 35 dimensions because I did not know what option to choose.

7. Deleted the new projected view to give more space for dimensions.

8. Aggressively deleted the Title Block and Borders for literally no reason.

9. Struggled to bring back a new Title Block and ended up designing my own.

	<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/5b381b6b-3853-420c-950d-d1437d06e1e2" />
	
10. Further edited the Title Block to remove unwanted details.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3a211d63-1eeb-4086-85c9-9fc652d449be" />
	
11. Added another base view, same as the one I deleted before.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d4532925-d0a4-4aae-9702-ff27350bd6c1" />

Now, finally, the drawing is complete after a few more tweaks (at least that's what I thought back then).

<img width="1024" height="663" alt="1788604893301-039b357a-4560-4843-9b33-af57f98d26be_1" src="https://github.com/user-attachments/assets/f605704d-a8bf-44e2-9374-3423e0b41b9d" />

But then I became bored and tired at the same time. Then, suddenly I remembered: nothing was journaled from day #42 to #69.

<img width="290" height="624" alt="image" src="https://github.com/user-attachments/assets/bd056bc7-ac5b-488f-b146-84239a17c1af" />

So, it was time for me to journal. With the help of PATRA [OLD] v7 and PATRA [OLD] v8 in my Autodesk Fusion, and [PATRA-LPS-22-D42](https://lapse.hackclub.com/timelapse/DzR0y5DWGWK2), I journaled Day #42 partly.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/79736694-b48c-4ae8-becc-1df1109990f9" />

Here's the lapse of today's session: [PATRA-LPS-50-D70](https://lapse.hackclub.com/timelapse/3X4rEaElD5qQ)

**Total time spent: 3h 45m**

---

# Day 71 — 06.09.2026: Re-Drawing the Z Axis Leg Lower A

Today, I actually wanted to journal the old un-journaled logs as they were piling up like crazy. But instead, I remembered that the drawing I had created on 05.09.2026 (yesterday) was absolutely unfabricatable, as I used Ordinate instead of Base Dimensions.

To be honest, I actually don't really know how to create a drawing for a complex part like that for CNC machining. What I did yesterday was mostly guesswork and intuition.

I started with a simple Google Search using the drawing made yesterday:
**"What geometrical data missing that can cause someone to be unable to give me a quote?"**

And well, the answer confirmed the fact that I really needed to start over from scratch. This meant that an automated workflow was an ideal choice for me, even though I was initially unaware of what exact automated process exists, to what extent, and how reliable it actually is.

Here's what I did next:

1. I searched for a tutorial and found [this](youtube.com/watch?v=NweBvuVYuQo) video. It showed how to create automated drawings.

2. I followed the exact workflow several times, and each time, I failed. Every time, I took the image and uploaded it to Google AI Search for consultation.

	- The first draft was this, where I did pretty much nothing, except confirming Baseline Dimensions:
	
 		<img width="655" height="464" alt="image" src="https://github.com/user-attachments/assets/34680783-744e-4048-9038-de3fff56a9e2" />
		
	- The next draft was even worse, where I selected the wrong parent body orientation, scale, and dimension density:
	
 		<img width="646" height="458" alt="image" src="https://github.com/user-attachments/assets/539d63b1-bacc-4628-b336-5bc778b98b41" />
		
	- Again, another failure, which I made because I did not understand what I was actually doing:
	
 		<img width="648" height="458" alt="image" src="https://github.com/user-attachments/assets/27f06258-eb9b-4801-863b-47d18d239368" />
	
3. Then finally, I finally understood what to do. But the first thing which I did was not the projection, but actually editing the Title Block. Editing the title block is extremely crucial because it determines at what orientation, distance, and shape you can place your projected views. It also lets you remove unnecessary information, keeping only what's needed, and add something that you need.

	<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/60b90a8e-6c08-4327-b8b9-edfb5e4177ae" />

4. A drawing can have several sheets. The first sheet, which I made, was again a failure, but the second time, when I started fresh without directly relying on Auto Dimensions from the very beginning, it actually started making sense in my drawing. Repeatedly, the auto dimensions were taking a random side of the model, which I did not want. This time, when I did that manually, I took the top orientation of the Z Axis Leg Lower A, then I made all the possible projections.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/de16187b-0272-4b9f-b03e-fc805f18efb2" />

5. Next I edited the Borders to make them spaced equidistant from the edges of the page.

	<img width="1365" height="735" alt="image" src="https://github.com/user-attachments/assets/45d09801-1868-4790-9d5d-95fae5ac0478" />

6. But then the dimensions looked way too much, and there was severe over-dimensioning. But the worst: there were way too many projected views. So I deleted some to clear up the drawing.

	<img width="1365" height="736" alt="image" src="https://github.com/user-attachments/assets/c46b0a2b-c395-4698-9b13-e091fb4e05c4" />

7. I set the dimension density at 20 of 35 datum locations as the default, as Top Left.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/03c3bf5d-cc33-444c-8e70-9d92d668f88e" />

8. I pasted the image into Google and asked what data was missing. It pointed out some, which I gradually fixed and added one by one manually. To do things manually, I used my imagination to think of me as the tip of a 3 axis CNC machine: carefully thinking about what data I needed one by one to first form the outer shape, the holes, the pockets and the receding part of the distal joint. Like this, I added several radii and distances crucial for CNC fabrication. I then continued to manually add dimensions one by one and checked them with Google AI Mode.

	- This is the first iteration:
	
		<img width="684" height="485" alt="image" src="https://github.com/user-attachments/assets/982954f4-b0d4-406e-a24a-041b68595337" />
		
	- This is the second iteration:
	
		<img width="684" height="485" alt="image" src="https://github.com/user-attachments/assets/38e6b2ce-d564-4af8-8c35-d15f341d8b34" />
		
	- This is the third iteration:
	
		<img width="684" height="485" alt="image" src="https://github.com/user-attachments/assets/01a3cd00-0c63-4d72-a779-3495da876a85" />
	
9. By this time, there were way too many dimensions, especially for the base view. Thus, it seemed sensible to add the bottom view of the Z Axis Leg Lower A. But to do it, I couldn't use a projected view. So, I created another base view and rotated it so that the drawing stays clean. I then added the necessary dimensions and again consulted Google for assistance.

	<img width="684" height="485" alt="image" src="https://github.com/user-attachments/assets/f5d8898f-4401-41b7-93af-fd6d53b92c1e" />

10. Then finally, with some more review, I had the drawing ready. It seemed fine to me and most probably had no missing dimensions. I also edited the Title Block and added some more details like the project title and fixed minor issues.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d0416f4b-bb70-4ee0-a93a-4c27197b9b22" />

With all that done, I saved all the designs, including the failed ones, and named them in the following sequence:

<img width="379" height="442" alt="image" src="https://github.com/user-attachments/assets/b971ceeb-23eb-48cf-b540-b7b57d994940" />

This is how the drawing looks at last:

<img width="3509" height="2480" alt="Z Axis Leg Lower A Drawing v3" src="https://github.com/user-attachments/assets/9aa9e2c4-848f-4c2f-9cad-fe3aaf0b22e2" />

Here's the lapse of today's session: [PATRA-LPS-51-D71](https://lapse.hackclub.com/timelapse/lAy-izM683f_)

**Total time spent: 3h 05m**

---

# Day 72 — 08.09.2026: Journaling

Journaled day #71 and #70 (partly).

Day #71

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f7cd7595-6cb5-405d-a11e-e53e867ac71e" />

Day #70

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1c8458b1-1f47-4908-abae-6b712e2aaa55" />

Here's the lapse of today's session: [PATRA-LPS-52-D72](https://lapse.hackclub.com/timelapse/FMU-NvBEFHSQ)

**Total time spent: 3h 15m**

---

# Day 73 — 09.09.2026: Journaling

Journaled day #70 (full).

Day #70

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c1a216d2-77f3-460e-91ca-c95f4ae6d9eb" />

Here's the lapse of today's session: [PATRA-LPS-53-D73](https://lapse.hackclub.com/timelapse/hbXuvaWEzDlR)

**Total time spent: 1h 05m**

---

# Day 74 — 11.09.2026: Researching on Print Filament & Journaling

Today, as I was journaling day #69, I came across the decision I made back then: using PA-CF for printing the pulley and idler cases. I still get that it was a wonderful filament and it, by itself, prevents belt wear pretty well. But the cost was too much to bear. Looking at some more options like PLA-CF, ABS-GF, ABS-HF, PLA-HF, and PETG-CF, I chose to use PETG-CF. I don't need high temperature resistance more than rigidity and strength.

PETG-CF itself was quite cheap, but thanks to crazy customs, maybe the cost is ridiculous on most sites. I found a reasonable price in [3D Master India](https://3dmasterindia.in/product/elegoo-carbon-fiber-petg-filament-black-1kg/?srsltid=AfmBOopAwQI3m084wMjB5dR5WAvgTmA4XG1KtMEJiToUiWxFLAs1Qwe-HJk).

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/40db9700-8ea2-4826-8aec-921d29e70e6a" /> 

Journaled day #69 (full).

Day #69

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f03f71c6-19bc-4a9b-a3d1-5b84f4c839cc" />

Just out of curiosity, I wanted to see the mountain of work I have left behind. These are the days containing an [incomplete] or missing journal body tag:

* Day #29
* Day #30
* Day #31
* Day #36
* Day #37
* Day #41
* Day #42
* Day #43
* Day #44
* Day #45
* Day #46
* Day #47
* Day #48
* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64
* Day #65
* Day #66
* Day #67
* Day #68

I really, really need to journal more. It is the fault of my flow state. I have decided to journal every single day before I proceed with the design. This is because the older they get, the more I forget. Despite having all of them lapsed, I couldn't ask myself about my own design and how it happened in the future. Also, journaling is extremely necessary for the Forge program.

Here're the lapses of today's session: [PATRA-LPS-54-D74-1](https://lapse.hackclub.com/timelapse/JHAkLwwLItsD) and [PATRA-LPS-54-D74-2]()

**Total time spent: 3h 40m**

---

# Day 75 — 12.09.2026: Journaling

In order to live up to my commitment, I journaled today. While journaling day #29, I saw poor journaling on day #28, so I fixed it. I also synced my lapses with Hacktime (important but really tedious).

Journaled days #28, #29, #30, #67, and #68 (partly)

Day #28

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/8b11a728-4122-4748-af98-b67631578ecc" />

Day #29

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/41e96698-27b5-452b-a1d1-7ed34377cc01" />

Day #30

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2e19e4a0-b436-47d4-9e60-a85845aeb04a" />

Day #67

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c4b6565e-8cf1-4e56-81a0-d58e00cca527" />

Day #68

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/9a6aed0e-dd6f-455c-a0e4-3153689ecc3a" />

After today, these days are left to be journaled:

* Day #31
* Day #36
* Day #37
* Day #41
* Day #42
* Day #43
* Day #44
* Day #45
* Day #46
* Day #47
* Day #48
* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64
* Day #65
* Day #66
* Day #68 (partly)

Here're the lapses of today's session: [PATRA-LPS-55-D75-1](https://lapse.hackclub.com/timelapse/hbXuvaWEzDlR) and [PATRA-LPS-55-D75-2](https://lapse.hackclub.com/timelapse/Ef9ur-75vopq)

**Total time spent: 3h 40m**

---

# Day 76 — 13.09.2026: Journaling

Journaled days #31, #36, #65 (partly), and #68 (full).

Day #31

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/feb5eb68-57fd-4a39-a547-db08e91e7a7f" />

Day #36

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5a43fa15-9130-4024-8bfd-f727e81e976a" />

Day #65

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/da25f9a7-27e4-45f5-8611-89b829ccaca8" />

Day #68

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4f8fb892-971f-4114-b718-dac43a1ce36f" />

After today, these days are left to be journaled:

* Day #37
* Day #41
* Day #42
* Day #43
* Day #44
* Day #45
* Day #46
* Day #47
* Day #48
* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64
* Day #65 (partly)
* Day #66

Here's the lapse of today's session: [PATRA-LPS-56-D76](https://lapse.hackclub.com/timelapse/YCfkx4a_ljDg)

**Total time spent: 5h 45m**

---

# Day 77 — 14.09.2026: Journaling & Reconsidering Motor Layouts

While journaling day #66 in the motor section, I randomly came across integrated motors and started comparing them to my discrete driver setup.

The numbers came out to:

* Setup 1 (Discrete T60S Drivers + Separate Motors): ₹20,125 INR total
* Setup 2 (Integrated All-in-one Motors): ₹17,737 INR total

After asking Google which one was better, this distinction came out:

| System Parameter | Setup 1: Discrete Layout (₹20,125) | Setup 2: Integrated Layout (₹17,737) |
|---|---|---|
| Components | 3x Discrete T60S Drivers + 2x 57AM23ED + 1x 57AM30ED | 2x Integrated IT57AM23 + 1x Integrated IT57AM30 |
| Max Voltage | 50V DC (Strict hardware limit) | 50V DC (Strict hardware limit) |
| 48V PSU Margin | High Risk (Only 2V headroom; prone to back-EMF spikes) | High Risk (Only 2V headroom; prone to back-EMF spikes) |
| Fusion 360 Fit | Flawless fit for standard NEMA 23 profiles | Interference (Driver block hits custom mount brackets) |
| Loop Tuning | Software config via RTConfigurator | None (Strictly limited to physical DIP switches) |
| Failure Isolation | Excellent (Can replace just the independent driver block) | Poor (If driver fries, the entire motor must be replaced) |

I learned that running integrated motors at 48V on the Mean Well LRS-600-48V is a massive risk. Fast deceleration profiles on our heavy ~5 kg KBM frame will generate back-EMF voltage spikes. The discrete T60S handles up to 68V, providing solid safety headroom, while the integrated units cap out strictly at 50V and will fry the onboard chips.

The integrated motors are as follows:

1. Integrated motor for Rtelligent 57AM23ED is [Rtelligent IT57AM23](https://robu.in/product/rtelligent-integrated-closed-loop-stepper-motor-57mm-flange-23nm-holding-torque-it57am23/)

	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/255a68e6-977c-4216-83b2-be1a0c458855" />

2. Integrated motor for Rtelligent 57AM30ED is [Rtelligent IT57AM30](https://robu.in/product/rtelligent-integrated-closed-loop-stepper-motor-57mm-flange-30nm-holding-torque-it57am30/)

	<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6f29bb9d-fc1c-4cd9-b5d7-215ceeee3e2b" />

Finally, because PATRA has a constantly changing parallel axis load profile, being able to plug into Rtelligent's software via the tuning port to adjust PID loops, current values, and multi-stage digital position filters is critical. The integrated series locks me out completely, forcing reliance on basic hardware DIP switches with no way to tune out resonance or mechanical hunting vibrations under load.
Even though Setup 1 carries a ₹2,388 INR premium, it is the only route that is structurally and electronically viable for the project. It preserves my existing CAD timeline geometry, keeps my power grid stable, and gives me the configuration space I need to interface smoothly with the Teensy 4.1.

The previous configuration, though ₹2,388 more expensive, was actually better.

Journaled days #65 (full) and #66 (partly).

Day #65

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/dec669e3-9dd0-4c97-aa50-38914e6f2a53" />

Day #66

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/af5a04d4-897e-487d-978f-16815c5f1f7b" />

After today, these days are left to be journaled:

* Day #37
* Day #41
* Day #42
* Day #43
* Day #44
* Day #45
* Day #46
* Day #47
* Day #48
* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64
* Day #66 (partly)
* Day #77 (partly)

Here's the lapse of today's session: [PATRA-LPS-57-D77](https://lapse.hackclub.com/timelapse/8T-JtHAdSQJ7)

**Total time spent: 3h 40m**

---

# Day 78 — 19.09.2026: Drafting Emergent Ventures Proposal & Almost Completing Phase 1 BOM

My midterms were knocking on the door, and I was absolutely scared to open the door as I was cooked. So, I decided to focus on my studies more until the exams ended. But before closing my doors temporarily for PATRA and opening them for exams, I had something in mind. Two days ago, on 16th September, 2026, I had discovered Emergent Ventures that help early stage projects by non-dilutive funds, with direct, fair and non-bureaucratic means from $1000 all the way up to $50000.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/09ca1546-13b3-458f-9fa3-96e7b60e6d5f" />

I was immediately blown away by the fact that I just needed to be 13 years old to be eligible to apply. The joy upon discovery was similar to that of when I discovered Hack Club Blueprint. I really needed it, as I didn't know what was coming or how I would be able to complete this project after Forge ends on 30th November, 2026.

Not caring about the acceptance rate, which is similar to some Ivy League schools, I decided to apply as soon as possible on that day. I then wrote an application, of course using AI, as I had no idea what I was even doing, to be honest. After several revisions that day, I actually submitted it. It was only after I submitted that I realized that it was way too inaccurate and bad. Again, haste made AI-slop.

So, I decided to do it myself instead on 17th September, 2026. I wrote the full thing, the introduction, the consensus view that I agree with, and the budget.

> [!Important]
> All of this took me over 3 hours in total, if I exclude the time I spent convincing AI that the application sounded too "AI". I think it is not wrong to add the time I spent typing, and since this is completely about my project, I am adding this time to the time spent today.

Today is just two days prior to my exam, and I decided to almost complete the Bill of Materials as I needed a proper budget for the Emergent Ventures application. I made several changes to the existing BOM.

I classified my project into three distinct phases:

1. PATRA Phase 1: KBM + TRM with no CNC-machined parts. Budget: $1000. High confidence in the budget, as it is mostly calculated.
2. PATRA Phase 2: KBM + TRM with CNC-machined parts. Budget: $2000 (extra $1000). Budget is made up of realistic estimates and online quote averages.
3. PATRA Phase 3: KBM + TRM + RAM with CNC machined parts after testing with 3d printed parts. Budget $5000 (extra $3000). Budget is a pure estimate.

Forge could fund phase 1, or even phase 2 if it ends after April 2027 instead of 30th November 2026. But for phase 3, I needed more financial support.

Since the budget for the first phase was capped at $1000, I wanted to make the most of it without overspending. Here is the new budget breakdown:

Kinematic Base Module (KBM): $550
TriTeron Robot Module (TRP): $50 (as it's mostly 3D printed)
Electronics: $300
Miscellaneous: $100

Here's what I did:

- I upgraded from generic MGN15H linear blocks and rail to genuine HIWIN linear rail and blocks.
- Changed printing material from PA Nylon to PETG-CF and PLA PRO.
- Added estimated shipping costs, electronics, filament costs, and taxes.

This is the BOM before:

| PATRA Parallel Axis TriTeron Robotic Arm BOM |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------------|----------------------|----------------------------------------------------------------------------------|----------------------|----------|------------|--------------|------------|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Component Category                           |                      | Item                                                                             | Material             | Quantity | Cost (USD) |  Cost (INR)  | Total Cost | Source          | Link                                                                                                                                                                                                                                                                                                                                                                                                            |
| Kinematic Base Module (KBM)                  | Aluminium Extrusions | LCF6-2020-1135 Aluminium 2020 T-Slot Profile Extrusion                           |  Aluminium           | 2        |  $3.24     |  ₹ 306.45    |  $6.49     |  MISUMI         | https://in.misumi-ec.com/vona2/detail/110311047509?HissuCode=LCF6-2020-1135                                                                                                                                                                                                                                                                                                                                     |
|                                              |                      | HFS5-4040-1000 Aluminium 4040 V-Slot Profile Extrusion                           |  Aluminium           | 2        |  $27.47    |  ₹ 2,595.20  |  $54.93    |  MISUMI         | https://in.misumi-ec.com/vona2/detail/110302684530?HissuCode=HFS5-4040-1000                                                                                                                                                                                                                                                                                                                                     |
|                                              | End Plates           | End Plate Body                                                                   |  FDM PETG            | 2        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | End Plate Connectors                                                             |  FDM PETG            | 8        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              | Linear Guides        | MGN15H Linear Guide Rail 1 m                                                     |  Bearing Steel       | 2        |  $28.88    |  ₹ 2,729.00  |  $57.76    |  Robu           | https://robu.in/product/mgn15h-linear-guide-rail-1m-2                                                                                                                                                                                                                                                                                                                                                           |
|                                              |                      | MGN15H Sliding Block                                                             |  Bearing Steel       | 4        |  $7.19     |  ₹ 679.00    |  $28.74    |  Robu           | https://robu.in/product/sliding-block-for-mgn15h-linear-guide-rail                                                                                                                                                                                                                                                                                                                                              |
|                                              |                      | Belt Clamp Bottom (X & Y)                                                        |  MJF PA12S-HP Nylon  | 2        |  $2.07     |              |  $4.14     |  JLC3DP         |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Belt Clamp Top (X & Y)                                                           |  SLA 9600 Resin      | 2        |  $1.47     |              |  $2.94     |  JLC3DP         |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Belt Clamp Bottom (Z)                                                            |  MJF PA12S-HP Nylon  | 1        |  $2.01     |              |  $2.01     |  JLC3DP         |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Belt Clamp Top (Z)                                                               |  SLA 9600 Resin      | 1        |  $3.79     |              |  $3.79     |  JLC3DP         |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              | Tensioning Systems   | Belt E-GBN22505GT-150 (X & Y)                                                    |  Rubber Glass Core   | 2        |  $12.97    |  ₹ 1,225.63  |  $25.94    |  MISUMI         | https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN22505GT-150                                                                                                                                                                                                                                                                                                                                   |
|                                              |                      | Belt E-GBN26005GT-150 (Z)                                                        |  Rubber Glass Core   | 1        |  $14.82    |  ₹ 1,400.77  |  $14.82    |  MISUMI         | https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN26005GT-150                                                                                                                                                                                                                                                                                                                                   |
|                                              |                      | Pulley & Idler CBYL-AH1-5GT150-22-A-N-d12 (X & Y)                                |  Aluminum Alloy      | 4        |  $3.03     |              |  $12.12    |  JLCMC          | https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-22-A-N-d12&productModelNumber=CBYL-AH1-5GT150-22-A-N-d12                                                                                                                                                                                                                                                                      |
|                                              |                      | Pulley & Idler CBYL-AH1-5GT150-20-A-N-d12 (Z)                                    |  Aluminum Alloy      | 2        |  $3.00     |              |  $5.99     |  JLCMC          | https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12                                                                                                                                                                                                                                                                      |
|                                              |                      | Pulley Case Left (X)                                                             |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Pulley Case Left (Y)                                                             |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Pulley Case Left (Z)                                                             |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Pulley Case Right (X)                                                            |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Pulley Case Right (Y)                                                            |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Pulley Case Right (Z)                                                            |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Idler Case Left (X)                                                              |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Idler Case Left (Y)                                                              |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Idler Case Left (Z)                                                              |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Idler Case Right (X)                                                             |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Idler Case Right (Y)                                                             |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Idler Case Right (Z)                                                             |  FDM PA Nylon        | 1        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Belt Sheilds (X & Y)                                                             |  FDM PLA+            | 8        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Pulley & Idler Case Coupler (Z)                                                  |  FDM PETG            | 2        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Bearing Cover                                                                    |  FDM PETG            | 9        |            |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | 6901ZZ Bearing (Pack of 4)                                                       |                      | 3        |  $2.53     |  ₹ 239.00    |  $7.59     |  Robu           | https://robu.in/product/6901zz-bearing-12x24x6-shielded-miniature-ball-bearings-4pcs/                                                                                                                                                                                                                                                                                                                           |
|                                              |                      | WSX-SUS-M12X18-5 Washer                                                          |  FDM PETG            | 12       |  $-        |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Pulley Shaft (X, Y & Z)                                                          |  MJF PA12S-HP Nylon  | 3        |  $1.10     |              |  $3.30     |  JLC3DP         |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Idler Shaft (X, Y & Z)                                                           |  MJF PA12S-HP Nylon  | 3        |  $1.46     |              |  $4.38     |  JLC3DP         |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | PTFE Coated Teflon Tape                                                          |                      | 1        |  $4.23     |  ₹ 400.00    |  $4.23     |  Amazon         | https://www.amazon.in/Keiko-adhesive-Release-sealing-purpose/dp/B0DCGGGGGJ?th=1                                                                                                                                                                                                                                                                                                                                 |
|                                              | Motors               | Rtelligent 57AM23ED 2.3 Nm Closed-loop Stepper Motor (X & Y)                     |                      | 2        |  $43.17    |  ₹ 4,079.00  |  $86.34    |  Robu           | https://robu.in/product/rtelligent-57am23ed-closed-loop-stepper-servo-motor/                                                                                                                                                                                                                                                                                                                                    |
|                                              |                      | Rtelligent 57AM30ED 3 Nm Closed-loop Stepper Motor (Z)                           |                      | 1        |  $57.14    |  ₹ 5,399.00  |  $57.14    |  Robu           | https://robu.in/product/rtelligent-57am30ed-closed-loop-stepper-servo-motor/                                                                                                                                                                                                                                                                                                                                    |
|                                              | Fasteners            | M3 X 12mm High Tensile(12.9) Black oxide Grub Screw (Dia. 3mm, Length 12mm)      |                      | 30       |  ₹ 0.02    |  ₹ 2.00      |  $0.63     |  OnlyScrews     | https://onlyscrews.in/products/m3-x-12mm-high-tensile12-9-black-oxide-grub-screw-dia-3mm-length-12mm                                                                                                                                                                                                                                                                                                            |
|                                              |                      | M3 X 12mm Hex (Allen) CSK SS 304 Screw (Dia. 3mm, Length 12mm)                   |                      | 25       |  $0.02     |  ₹ 1.80      |  $0.48     |  OnlyScrews     | https://onlyscrews.in/products/hex-allen-csk-m3-x-10-screw-pack-of-20?_pos=1&_sid=1040a6d00&_ss=r                                                                                                                                                                                                                                                                                                               |
|                                              |                      | Socket Head High Tensile(12.9) Black oxide screw (Dia. 5mm, Length 10mm)         |                      | 15       |  $0.03     |  ₹ 2.40      |  $0.38     |  OnlyScrews     | https://onlyscrews.in/products/m5-x-10mm-hex-allen-socket-head-high-tensile12-9-black-anodized-screw                                                                                                                                                                                                                                                                                                            |
|                                              |                      | M3 X 5mm 3D Printing Brass Threaded Slant Knurled Inserts (Dia. 3mm, Length 5mm) |                      | 40       |  $0.05     |  ₹ 4.60      |  $1.95     |  OnlyScrews     | https://onlyscrews.in/products/m3-x-5mm-3d-printing-brass-threaded-inserts-dia-3mm-length-5mm                                                                                                                                                                                                                                                                                                                   |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |  OnlyScrews     |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |  OnlyScrews     |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |  OnlyScrews     |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              | Total                |                                                                                  |                      |          |            |              |  $386.10   |  Budget = $400  |                                                                                                                                                                                                                                                                                                                                                                                                                 |
| TriTeron Robot Module (TRM)                  | Leg Mounts           |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              | Legs                 |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              | Leg Joints           | MSB8-30 Screw                                                                    |                      | 15       |  $0.84     |              |  $12.60    |                 | https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30                                                                                                                                                                                                                                                                                                                                            |
|                                              |                      | EMLC-S1-N-M6 Nut                                                                 |                      | 100      |  $0.02     |              |  $1.65     |                 | https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M6&productModelNumber=EMLC-S1-N-M6                                                                                                                                                                                                                                                                                                          |
|                                              |                      | SS304 M8 Washer                                                                  |                      | 100      |  $0.02     |              |  $1.90     |                 | https://onlyscrews.in/products/m8-washer-ss304?currency=INR&country=IN&variant=49592314691897&stkn=6e84ebfba1b8&utm_source=google&utm_medium=cpc&utm_campaign=Inderans_Campaign&utm_content=Other_than_fasteners_wala_copy&gad_source=1&gad_campaignid=22229905346&gbraid=0AAAAA9sP2SS13C7O8clb3n7juN0NJicBD&gclid=Cj0KCQjwrZTRBhDSARIsAHidYff_2voIe-8RPEu9AA21EZff0GSSyk4MWjjptkDVLWuZe4Rjuu5uqCkaAtCuEALw_wcB |
|                                              |                      | 608ZZ Bearing                                                                    |                      | 25       |  $0.65     |              |  $16.25    |                 | https://robu.in/product/608rs-rubber-sealed-ball-bearing-miniature-bearing-8-x-22-x-7-mm-2pcs/?gad_source=1&gad_campaignid=20387462343&gbraid=0AAAAADvLFWcUP3CknhSW9eUY6CQlfupzk&gclid=Cj0KCQjwrZTRBhDSARIsAHidYfd0S1D73ieG7aGP_yzNHDVsqFkIBv0Nb17ZW9C3qtAqVlHfgalc-asaAqjfEALw_wcB                                                                                                                             |
|                                              | Tool Head            |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              | Total                |                                                                                  |                      |          |            |              |  $32.40    |  Budget = $200  |                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Electronics                                  |                      | Rtelligent T60S Closed-loop Stepper Motor Driver (X, Y & Z)                      |                      | 3        |  $37.56    |  ₹ 3,549.00  |  $112.68   |  Robu           | https://robu.in/product/rtelligent-t60s-closed-loop-stepper-driver/                                                                                                                                                                                                                                                                                                                                             |
|                                              |                      | Teensy 4.1 Development Board                                                     |                      | 1        |  $37.56    |  ₹ 3,549.00  |  $37.56    |  Robu           | https://robu.in/product/buy-teensy-4-1-development-board/?gad_source=1&gad_campaignid=17413441824&gbraid=0AAAAADvLFWfXLdA6AANHs5Ve4AQK9bfZ8&gclid=Cj0KCQjw2OnUBhC2ARIsACKyfaFzWoNclj3oNfiAD4EIvs_Ez1LKw9-ygCR7iBL90tSr9sch6fNVC1IaAk0PEALw_wcB                                                                                                                                                                  |
|                                              |                      | Mean Well <br>LRS-600-48v                                                        |                      | 1        |  $40.24    |  ₹ 3,802.00  |  $40.24    |  Trade India    | https://www.tradeindia.com/products/lrs-600-48v-meanwell-power-supply-c10893421.html                                                                                                                                                                                                                                                                                                                            |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  $-        |              |  $-        |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              | Total                |                                                                                  |                      |          |            |              |  $190.48   |  Budget = $350  |                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Shipping, Taxes, and Customs                 |                      |                                                                                  |                      |          |  misumi    |              |  $114.78   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  tax       |              |  $20.66    |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |  total     |              |  $135.44   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |  $20.66    |  Budget = $50   |                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Miscellaneous                                |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      |                                                                                  |                      |          |            |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                              |                      | Total                                                                            |                      |          |  $-        |              |            |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Grand Total                                  |                      |                                                                                  |                      |          |  $-        |              |  $629.64   |                 |                                                                                                                                                                                                                                                                                                                                                                                                                 |


This is the BOM after:

| Parallel Axis TriTeron Robotic Arm BOM |                      |                                                                                  |                        |          |            |              |            |                   |                                                                                                                                            |
|----------------------------------------|----------------------|----------------------------------------------------------------------------------|------------------------|----------|------------|--------------|------------|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| Component Category                     |                      | Item                                                                             | Print Material         | Quantity | Cost (USD) |  Cost (INR)  | Total Cost | Vendor            | Link                                                                                                                                       |
| Kinematic Base Module (KBM)            | Aluminium Extrusions | LCF6-2020-1135 Aluminium 2020 T-Slot Profile Extrusion                           |                        | 2        |  $3.19     |  ₹ 306.45    |  $6.39     |  MISUMI           | https://in.misumi-ec.com/vona2/detail/110311047509?HissuCode=LCF6-2020-1135                                                                |
|                                        |                      | HFS5-4040-1000 Aluminium 4040 V-Slot Profile Extrusion                           |                        | 2        |  $27.05    |  ₹ 2,595.20  |  $54.10    |  MISUMI           | https://in.misumi-ec.com/vona2/detail/110302684530?HissuCode=HFS5-4040-1000                                                                |
|                                        | End Plates           | End Plate Body                                                                   |  FDM PLA PRO (Silver)  | 2        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | End Plate Connectors                                                             |  FDM PLA PRO (Silver)  | 8        |            |              |  $-        |                   |                                                                                                                                            |
|                                        | Linear Guides        | HIWIN MGN15H Linear Rail 1 m                                                     |                        | 2        |  $88.59    |  ₹ 8,499.00  |  $177.17   |  novo3D           | https://novo3d.in/hiwin-mgn15-linear-guide-rail/                                                                                           |
|                                        |                      | HIWIN MGN15H Sliding Block                                                       |                        | 4        |  $18.75    |  ₹ 1,799.00  |  $75.01    |  Industrybuying   | https://www.industrybuying.com/linear-guides-hiwin-BEA.LIN.820966212                                                                       |
|                                        |                      | Belt Clamp Bottom (X & Y)                                                        |  MJF PA12S-HP Nylon    | 2        |  $2.07     |              |  $4.14     |  JLC3DP           |                                                                                                                                            |
|                                        |                      | Belt Clamp Top (X & Y)                                                           |  SLA 9600 Resin        | 2        |  $1.47     |              |  $2.94     |  JLC3DP           |                                                                                                                                            |
|                                        |                      | Belt Clamp Bottom (Z)                                                            |  MJF PA12S-HP Nylon    | 1        |  $2.01     |              |  $2.01     |  JLC3DP           |                                                                                                                                            |
|                                        |                      | Belt Clamp Top (Z)                                                               |  SLA 9600 Resin        | 1        |  $3.79     |              |  $3.79     |  JLC3DP           |                                                                                                                                            |
|                                        | Tensioning Systems   | Belt E-GBN22505GT-150 (X & Y)                                                    |                        | 2        |  $12.77    |  ₹ 1,225.63  |  $25.55    |  MISUMI           | https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN22505GT-150                                                              |
|                                        |                      | Belt E-GBN26005GT-150 (Z)                                                        |                        | 1        |  $14.60    |  ₹ 1,400.77  |  $14.60    |  MISUMI           | https://in.misumi-ec.com/vona2/detail/110411276379?HissuCode=E-GBN26005GT-150                                                              |
|                                        |                      | Pulley & Idler CBYL-AH1-5GT150-22-A-N-d12 (X & Y)                                |                        | 4        |  $3.03     |              |  $12.12    |  JLCMC            | https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-22-A-N-d12&productModelNumber=CBYL-AH1-5GT150-22-A-N-d12 |
|                                        |                      | Pulley & Idler CBYL-AH1-5GT150-20-A-N-d12 (Z)                                    |                        | 2        |  $3.00     |              |  $5.99     |  JLCMC            | https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12 |
|                                        |                      | Pulley Case Left (X)                                                             |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Pulley Case Left (Y)                                                             |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Pulley Case Left (Z)                                                             |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Pulley Case Right (X)                                                            |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Pulley Case Right (Y)                                                            |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Pulley Case Right (Z)                                                            |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Idler Case Left (X)                                                              |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Idler Case Left (Y)                                                              |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Idler Case Left (Z)                                                              |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Idler Case Right (X)                                                             |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Idler Case Right (Y)                                                             |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Idler Case Right (Z)                                                             |  FDM PETG-CF (Black)   | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Belt Sheilds (X & Y)                                                             |  FDM PLA PRO (Silver)  | 8        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Pulley & Idler Case Coupler (Z)                                                  |  FDM PETG-CF (Black)   | 2        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Bearing Cover                                                                    |  FDM PETG (White)      | 9        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | 6901ZZ Bearing (Pack of 4)                                                       |                        | 3        |  $2.49     |  ₹ 239.00    |  $7.47     |  Robu             | https://robu.in/product/6901zz-bearing-12x24x6-shielded-miniature-ball-bearings-4pcs/                                                      |
|                                        |                      | WSX-SUS-M12X18-5 Washer                                                          |  FDM PETG (White)      | 12       |  $-        |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Pulley Shaft (X, Y & Z)                                                          |  MJF PA12S-HP Nylon    | 3        |  $1.10     |              |  $3.30     |  JLC3DP           |                                                                                                                                            |
|                                        |                      | Idler Shaft (X, Y & Z)                                                           |  MJF PA12S-HP Nylon    | 3        |  $1.46     |              |  $4.38     |  JLC3DP           |                                                                                                                                            |
|                                        | Motors               | Rtelligent 57AM23ED 2.3 Nm Closed-loop Stepper Motor (X & Y)                     |                        | 2        |  $42.52    |  ₹ 4,079.00  |  $85.03    |  Robu             | https://robu.in/product/rtelligent-57am23ed-closed-loop-stepper-servo-motor/                                                               |
|                                        |                      | Rtelligent 57AM30ED 3 Nm Closed-loop Stepper Motor (Z)                           |                        | 1        |  $56.27    |  ₹ 5,399.00  |  $56.27    |  Robu             | https://robu.in/product/rtelligent-57am30ed-closed-loop-stepper-servo-motor/                                                               |
|                                        | Fasteners            | M3 X 12mm High Tensile(12.9) Black oxide Grub Screw (Dia. 3mm, Length 12mm)      |                        | 30       |  ₹ 0.02    |  ₹ 2.00      |  $0.63     |  OnlyScrews       | https://onlyscrews.in/products/m3-x-12mm-high-tensile12-9-black-oxide-grub-screw-dia-3mm-length-12mm                                       |
|                                        |                      | M3 X 12mm Hex (Allen) CSK SS 304 Screw (Dia. 3mm, Length 12mm)                   |                        | 25       |  $0.02     |  ₹ 1.80      |  $0.47     |  OnlyScrews       | https://onlyscrews.in/products/hex-allen-csk-m3-x-10-screw-pack-of-20?_pos=1&_sid=1040a6d00&_ss=r                                          |
|                                        |                      | Socket Head High Tensile(12.9) Black oxide screw (Dia. 5mm, Length 10mm)         |                        | 15       |  $0.03     |  ₹ 2.40      |  $0.38     |  OnlyScrews       | https://onlyscrews.in/products/m5-x-10mm-hex-allen-socket-head-high-tensile12-9-black-anodized-screw                                       |
|                                        |                      | M3 X 5mm 3D Printing Brass Threaded Slant Knurled Inserts (Dia. 3mm, Length 5mm) |                        | 40       |  $0.05     |  ₹ 4.60      |  $1.92     |  OnlyScrews       | https://onlyscrews.in/products/m3-x-5mm-3d-printing-brass-threaded-inserts-dia-3mm-length-5mm                                              |
|                                        |                      |                                                                                  |                        |          |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Total                                                                            |                        |          |            |              |  $543.66   |  Budget = $550    |                                                                                                                                            |
| TriTeron Robot Module (TRM)            | Leg Mounts           | X Axis Mount                                                                     |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Y Axis Mount                                                                     |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Z Axis Mount                                                                     |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        | Legs                 | X Axis Leg Upper                                                                 |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | X Axis Leg Lower                                                                 |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Y Axis Leg Upper                                                                 |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Y Axis Leg Upper                                                                 |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Y Axis Leg Lower                                                                 |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Z Axis Leg Upper A                                                               |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Z Axis Leg Lower A                                                               |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Z Axis Leg Upper B                                                               |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Z Axis Leg Lower B                                                               |  FDM PLA PRO (Silver)  | 1        |            |              |            |                   |                                                                                                                                            |
|                                        | Leg Joints           | MSB8-30 Screw                                                                    |                        | 15       |  $0.84     |  ₹ 4.60      |  $12.60    |  MISUMI           | https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30                                                                       |
|                                        |                      | EMLC-S1-N-M6 Nut                                                                 |                        | 100      |  $0.02     |  ₹ 4.60      |  $1.65     |  JLCMC            | https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M6&productModelNumber=EMLC-S1-N-M6                                     |
|                                        |                      | SS304 M8 Washer                                                                  |                        | 100      |  $0.02     |  ₹ 4.60      |  $1.90     |  OnlyScrews       | https://onlyscrews.in/products/m8-washer-ss304                                                                                             |
|                                        |                      | 608ZZ Bearing                                                                    |                        | 25       |  $0.65     |  ₹ 4.60      |  $16.25    |  Robu             | https://robu.in/product/608rs-rubber-sealed-ball-bearing-miniature-bearing-8-x-22-x-7-mm-2pcs/                                             |
|                                        | Tool Head            | Tool Head                                                                        |  FDM PLA PRO (Silver)  | 1        |            |              |  $-        |                   |                                                                                                                                            |
|                                        |                      | Total                                                                            |                        |          |            |              |  $32.40    |  Budget = $50     |                                                                                                                                            |
| Electronics                            |                      | Rtelligent T60S Closed-loop Stepper Motor Driver (X, Y & Z)                      |                        | 3        |  $36.99    |  ₹ 3,549.00  |  $110.98   |  Robu             | https://robu.in/product/rtelligent-t60s-closed-loop-stepper-driver/                                                                        |
|                                        |                      | Teensy 4.1 Development Board                                                     |                        | 1        |  $36.99    |  ₹ 3,549.00  |  $36.99    |  Robu             | https://robu.in/product/buy-teensy-4-1-development-board/                                                                                  |
|                                        |                      | Mean Well <br>LRS-600-48v                                                        |                        | 1        |  $39.63    |  ₹ 3,802.00  |  $39.63    |  Trade India      | https://www.tradeindia.com/products/lrs-600-48v-meanwell-power-supply-c10893421.html                                                       |
|                                        |                      | PCB (Price estimated at 100 USD)                                                 |                        | 1        |  $100.00   |              |  $100.00   |                   |                                                                                                                                            |
|                                        |                      | Wires (Price estimated at 10 USD)                                                |                        | 1        |  $10.00    |              |  $10.00    |                   |                                                                                                                                            |
|                                        |                      |                                                                                  |                        |          |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Total                                                                            |                        |          |            |              |  $297.60   |  Budget = $300    |                                                                                                                                            |
| Miscellaneous                          |                      | MISUMI 18% GST                                                                   |                        | 1        |  $18.24    |  $1,750.38   |  $18.24    |                   |                                                                                                                                            |
|                                        |                      | Industrybuying 18% GST                                                           |                        | 1        |  $6.75     |  ₹ 647.64    |  $6.75     |                   |                                                                                                                                            |
|                                        |                      | JLCCNC + JLC3DP + JLCPCB Shipping (Estimated at 20 USD)                          |                        | 1        |            |              |  $20.00    |                   |                                                                                                                                            |
|                                        |                      | Elegoo PETG-CF Black                                                             |                        | 1        |  $20.84    |  ₹ 1,999.00  |  $20.84    |  3D Master India  | https://3dmasterindia.in/product/elegoo-carbon-fiber-petg-filament-black-1kg/                                                              |
|                                        |                      | Elegoo PLA PRO Silver                                                            |                        | 2        |  ₹ 11.20   |  ₹ 1,075.00  |  $22.41    |  Robu             | https://robu.in/product/elegoo-pla-pro-filament-1kg-spool-silver/                                                                          |
|                                        |                      | PTFE Coated Teflon Tape                                                          |                        | 1        |  $4.17     |  ₹ 400.00    |  $4.17     |  Amazon           | https://www.amazon.in/Keiko-adhesive-Release-sealing-purpose/dp/B0DCGGGGGJ?th=1                                                            |
|                                        |                      |                                                                                  |                        |          |            |              |            |                   |                                                                                                                                            |
|                                        |                      | Total                                                                            |                        |          |            |              |  $92.41    |  Budget = $100    |                                                                                                                                            |
| Grand Total                            |                      |                                                                                  |                        |          |            |              |  $966.07   |  Budget = $1000   |                                                                                                                                            |

I created a new separate file for Phase 1:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/28cb7c59-ea07-493a-ac84-0efa363861a8" />

Next, I reviewed my Emergent Ventures Proposal, and then I submitted it on 20th September 2026, after some final adjustments.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ae130e56-23c7-4ff1-b9c4-c32c181c9801" />

I also fixed some broken links. Thanks to fellow Hack Clubber duck for helping me find it out.

Final BOM:

<img width="2187" height="1216" alt="image" src="https://github.com/user-attachments/assets/6692d489-9fe0-4a05-aa95-1ec85da8ad22" />

Here's the lapse of today's session: [PATRA-LPS-58-D78](https://lapse.hackclub.com/timelapse/J5WCGaXc-DjG)

**Total time spent: 7h 50m**

---

# Day 79 — 01.10.2026: Removing AI Polish & Journaling

On 16th September 2026, I asked my Forge Guild if my journaling is good or not, expecting a positive reply with flaws pointed out. I did get both, but maybe not in the same ratio, as the former was less. But no worries, here is what was pointed out:

1. Day #2 to #7 was way too AI-refined.
2. Many days unjournaled.
3. Lapses mixed up and broken (fixed on day #78)

I knew about the second one. The first one was mostly forgotten over time, and the last was already fixed. So, today I fixed days #1 to #7 and completed journaling day #66 (full) and #78.

Day #1

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/8b4a7f55-d5e3-4ae7-8222-e94d8534181a" />

Day #2

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1da76dd2-30a4-437d-a66a-5629902632b2" />

Day #3

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6a639997-9adc-4800-886b-2c2d5e3d2ad4" />

Day #4

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/cd95ab14-514d-4f0e-a54d-bbd190535f24" />

Day #5

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0a481204-4a63-47e3-bf41-7b5a8ee9c2d9" />

Day #6

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ed524c14-a2ef-4a38-942b-c8c2200c1ef8" />

Day #7

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/67f9bc2e-e124-4aee-a1ec-3934d2e84453" />

Day #66

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/14ad3808-7a38-40db-8d06-e18f5f33438a" />

Day #78

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e6ef34e8-6fe9-4652-9572-4f26768d71d4" />

Alongside the journaling, I also added support for motors, which will prevent the PETG-CF from flexing under the weight of the 1.2 kg to 1.5 kg motors. I did model one from the sketch of the motor's shape, but I wasn't able to copy it to other motors due to processing issues.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/86de543e-bd9d-4bce-9ebc-12cb1e270345" />

After today, these days are left to be journaled:

* Day #37
* Day #41
* Day #42
* Day #43
* Day #44
* Day #45
* Day #46
* Day #47
* Day #48
* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64
* Day #77 (partly) 

Here's the lapse of today's session: [PATRA-LPS-59-D79](https://lapse.hackclub.com/timelapse/JpZZQGepYBA-)

**Total time spent: 4h 50m**

---

# Day 80 — 06.10.2026: Journaling & Working on Motors

I have a confession to make. I have spent a lot of time journaling in this project. Yet, I am always in a huge debt of journaling. And there is a very logical reason behind that. I do not perceive journaling to be real progress, though I understand its importance. Due to this, I maximize the time spent in a session with actual work done. Journaling needs a lot of mental bandwidth. I really need High Bandwidth Memory (HBM) more than NVIDIA. Especially the older the day is, the more I have to think about what I actually did. Even though it is true that there are lapses for most of the days, it still requires a lot of thinking. Even in parallel, when I open Fusion Timeline, I struggle to find the time when I did that. Even if I find it, there's still a lot of thinking involved. 

This is the reason why I have decided to stop making any more progress, at least any more significant progress, until I am free from the debt of journaling. Journaling is extremely important to keep track of all my decisions. All of those days when I have not journaled are a really big burden. I don't want to be indebted by journaling. So I am deciding from now on that for every single session from now I will write down all of the important decisions I took real time, and then, after the session, put it all together.

Journaled days #37, #41, #42 and #43

Day #37

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f8b29a7d-0519-4d64-8580-77b2bc88ee9d" />

Day #41

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/47688eae-e48c-4d5d-96ff-00e56b5288ed" />

Day #42

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7a5cfd11-48d4-4726-9603-7ea31e411386" />

Day #43

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/de679c69-6681-4272-ad73-07bb6895e0c0" />

While journaling, I also fixed the problem I was facing on the last day. It was the wrongly positioned motors. It was not possible to move them without disrupting the timeline. So, I removed the motors. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8ec9c6c5-f3b6-4779-980a-ba9342852a1d" />

And imported new models, added appearance, and used them instead.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/76122c65-0972-4624-b4bb-a99ed7fb8dc0" />

I also continued modelling the support structure for the motors and achieved this design.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/17696cca-d531-4f20-ac4c-f59cbfd79552" />

After today, these days are left to be journaled:

* Day #44
* Day #45
* Day #46
* Day #47
* Day #48
* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64
* Day #77 (partly)

Here's the lapse of today's session: [PATRA-LPS-60-D80](https://lapse.hackclub.com/timelapse/6VuvPVunCxcQ)

**Total time spent: 5h 20m**

---

# Day 81 — 08.10.2026: Journaling & Attempting to Fix Floating Washers

Journaled day #44 partly.

Day #44

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/9712afb0-ee7a-4ae7-ad89-5f7534a56a77" />

I noticed that in the TriTeron, there are some floating components that must be fixed.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/99ade5ab-e09a-4638-a764-b73443a6147d" />

At a closer inspection, I noticed that somehow the washers are misplaced in a way that their positions in a specific Distal Joint Set corresponds exactly to the an other washer in position. I tried looking into the timeline to see when it even happened. I tried removing components and adding new washers in the design as a copy, but it had its own problems.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a095bd84-e63d-4989-a50f-a57659b83189" />

My practical exams still weren't over, so I had to stop.

After today, these days are left to be journaled:

* Day #44 (partly)
* Day #45
* Day #46
* Day #47
* Day #48
* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64
* Day #77 (partly) 

Here's the lapse of today's session: [PATRA-LPS-61-D81](https://lapse.hackclub.com/timelapse/NfYOcsd-JYDs)

**Total time spent: 1h 05m**

---

# Day 82 — 09.10.2026: Journaling & Fixing Floating Washers

I started by fixing the problem I left on the table yesterday. I looked at the problem from a different angle today: the angle of versions. I opened version 5 and saw that my current unsaved version 6 has almost no changes, except for the fact that the former one had no problems. So, I unhesitatingly clicked on **"Don't Save"** and deleted the unsaved and problematic file.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/805c820b-54e8-4b24-ad2d-79fd57330bc5" />

Then I journaled days #44 (full), #77, and #45.

Day #44

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/842a6c4a-dd2e-4592-92ac-ae06893b8ed8" />

Day #77

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b6301c2a-374e-458a-947c-21cc71bc03b5" />

Day #45

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/a54d6e75-cf3a-450e-86f1-6ce991bdfdb2" />

I also wanted to address the pending problems with the KBM, which were the countersunk chamfers and the inserts that stopped me from completing the KBM. Here's what I did:

1. **Fixing the M5 motor mounts:**
   
	- The first thing I did was delete the holes, as they were in the wrong position due to the previous motors that were not placed correctly.

  		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1f40509d-7eb9-473e-9237-d79956263891" />
		
	- Then I created a new sketch with the projection of the newly and correctly placed motors. I kept the hole diameter at 6 mm as the heat set insert is 6.4 mm.

		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5b60b2bb-18ee-48e4-b036-992e90fd6cfb" />
		
	- Then I extruded the hole 10 mm inside and added 0.2 mm chamfers, making the outermost diameter of the chamfer 6.4 mm.

		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/591db845-de23-4273-aad9-566d489d6ef9" />

2. **Fixing the M3 pulley case mounts:**

	- I had to know the exact chamfer value, so I downloaded [this](https://cdn.shopify.com/s/files/1/0871/5295/1609/files/CSK_M3x6mm.step?v=1753268015) STEP file from OnlyScrews.

		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d0eee580-6f5e-4794-83b0-7232ef61e802" />
		
	- I made a cylinder with a 3.4 mm hole in it and tested it with chamfers of different values. 1.3 mm deep and 1.3 mm wide chamfer was the best.

		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9052eb39-ef7d-47af-9847-9798e88c76fd" />
		
	- I also did a section analysis to see if this is actually correct.

		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/531c4d63-1e73-43b3-b780-70fa402d15d8" />
		
	- As I knew the value, I applied it in the design.

		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/43e6d727-a521-4811-8cb0-49d664741dd7" />

3. **Adding M5 brass inserts:**

	- There was [this](https://cdn.shopify.com/s/files/1/0871/5295/1609/files/BI_M5x10.step?v=1746464097) STEP file for the 10 mm M5 brass insert in OnlyScrew, which I downloaded.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9357efa4-71b9-49a5-9995-ae5dcb10cb1d" />
		
	- I then placed it inside the design as well.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/20ed5682-751e-4034-89c4-907ffe6b5d36" />

After today, these days are left to be journaled:

* Day #46
* Day #47
* Day #48
* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64

Here's the lapse of today's session: [PATRA-LPS-62-D82](https://lapse.hackclub.com/timelapse/SN3cpATvOXLr)

**Total time spent: 5h 20m**

---

# Day 83 — 10.10.2026: Addressing Missing Parts of Kinematic Base Module (KBM) — Part 1

Yesterday's session ended at the step where I was addressing the missing things in the Kinematic Base Module (KBM). Today I did a lot of the next steps, instead of journaling.

First, I added M5 brass inserts.

Here's what I did:

1. **Adding M5x10 mm brass inserts for X and Y axes (continued from last session):**

	- The center of the insert and the hole did not match. This meant that it was misplaced in the last session.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/24cf8abd-11a1-4c91-ba09-4ed07b6822e7" />
		
	- I used the Join tool to place it correctly. Then I copied it to make a total of four inserts.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f1ae876b-88da-46c4-973a-c0a8f9642e1d" />

2. **Adding M3x10 mm brass inserts for X and Y axes:**

	- I first closed the holes, as they were threaded.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5dcd1f70-3b02-41c4-8d9c-a0b4368df048" />
		
	- Then I made the hole 4.4 mm in diameter, as the insert is 4.8 mm. I also added a 0.2 mm chamfer, making the outermost edge 4.8 mm in diameter.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2489300e-c70c-47f4-8855-df54a360a54c" />
		
	- But due to that wide hole, the walls became too thin. So, I moved the holes 1 mm away from the center.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1e7c28d4-81a4-4c1b-b692-583812695c5d" />
		
	- I then extruded out my own inserts, as OnlyScrews had no STEP files.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/29843e3a-04cd-445a-93ec-9f6612d740c4" />
		
	- Added threads for the inserts I made.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5bddd210-4fcd-4eb1-8104-6592103ae725" />

3. **Adding M3x6 mm brass inserts for X and Y axes:**

	- For the screws below, I first thought of a length of 5 mm. But I changed it to 6 as I had space. I made the depth 6 mm and kept the diameter at 4 mm, as the insert was 4.4 mm.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e545c1a0-8845-44df-aba4-9e4f6ea50cbe" />
		
	- I then extruded out three inserts.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c1387c1d-c4dc-401a-8d54-4575d93a833d" />
		
  	- I added 0.2 mm chamfers to the edges of the hole, making the outermost diameter 4.4 mm.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3216add1-d099-4b78-871d-24ff8606436c" />
		
	- Then I added threads and copied it for the other side too.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/98c41682-3787-45d7-b5b7-dc93b4eff176" />

After this, I also thought of adding the screws for this. But while searching for screws, I discovered that only SS304 screws had STEP files, and the mild steel ones had no datasheet or STEP files. I first thought of making the screw 35 mm, where 20 mm is on the outer half of the pulley/idler case, and the remaining 15 mm is inside the other. But I made the inside 10 mm instead, as the longest SS304 M3 screw was 30 mm, which covers 20 mm + 10 mm (not 15 mm). I was not sure about the mild steel screw's dimensions, so I chose SS304 30 mm. Still, 10 mm depth is fine as per the thread depth rule for M3. This forced me to change both the hole depth and the insert length from 15 mm to 10 mm.

4. **Adding M3x30 mm countersunk screws for X and Y axes:**

	- I downloaded [this](https://cdn.shopify.com/s/files/1/0871/5295/1609/files/CSK_M3x30mm.step?v=1753269088) STEP file from OnlyScrews and imported it into the design.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7583c7df-d573-4fb2-aa78-854f6ac519f9" />
		
	- Then I remembered that I forgot to move the holes 1 mm away from the center for the other half of the case. So I did that.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/fc88ee64-6e76-4a93-9a89-1f578a27ad43" />
		
	- With that done, I copied the screw and used the circular pattern to copy it a total of 8 times in the correct position.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a4806f14-945b-49be-b1ff-0a59c45cd880" />

After making and adding so many new bodies and components, I arranged them inside the browser, placing each insert inside the Bodies folder of that case, making sure I didn't need joints, and arranging them nicely in the design. I made a separate component for the eight M3x30 mm screws.

With this, all fasteners needed for the X/Y pulley/idler were done. I can now mirror this to the idlers, then to the Y axis.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/37db4a0f-c218-4995-97b5-5c00cb7e099b" />

This is how it looks after copying it to all the others. Now, only the Z axis fasteners are left. Here's how it looks so far:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/703820c5-e11f-4d07-8c0d-25c749969df8" />

With the X and Y axes done, I next addressed the Z axis.

5. **Adding M5x10 mm brass inserts and fixing M3 holes for Z axis:**

	- The inserts were already arranged the way I needed them. So, I copied the inserts into the correct places.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1c156ab0-faae-4798-aea5-b1077ad2902e" />
		
	- I created a sketch with the correct position of the M3 holes, which are 1 mm from the center, and the correct position for the M5 holes.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/57e78a08-44e3-42d8-b4fc-d6c5cd7cf000" />
		
	- The holes weren't correct and were threaded. So, I first deleted the M5 holes and extruded the correct holes with a 6 mm diameter and 0.2 mm chamfer.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/67e083c1-66ec-4e23-80d5-089b449b9550" />
		
	- Then I extruded in the 3.4 mm M3 clearance holes, making sure there are 6 holes, not 8 (due to the case shape)
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c5f2813e-0a6f-4aa0-82ba-df844d3e9032" />
		
	- Added 1.3 mm wide and 1.3 mm deep clearance on the edges.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5ac81823-ceee-4e68-b3eb-7f3fa75799ad" />

6. **Adding M3x10 mm brass inserts for Z axis:** 

	- First, I got rid of the threaded holes using extrusions.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1cfc510f-4e0d-49d2-b91b-dd45c1016eac" />
		
	- Then I used my previous sketch to extrude the correct holes. I also added 0.2 mm chamfers.
	
		<img width="1365" height="731" alt="image" src="https://github.com/user-attachments/assets/e90333ae-b4c3-44c3-b099-4b2ed11dafd9" />
		
  	- Next, I copied the inserts and arranged them in the browser.
	
   		<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/36c8a0cc-0b31-4e1e-b1db-466654c4ecd9" />

7. **Adding M3x6 mm brass inserts for Z axis:**

	- I first made the hole from 5 mm deep to 6 mm, and added chamfers.
	
		<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/56f684c2-d5c8-443a-ae13-a4cb4edf3934" />
		
	- Next, I copied the inserts from the other case and then duplicated them for the other side too.
	
		<img width="1365" height="733" alt="image" src="https://github.com/user-attachments/assets/2f1b730f-9278-41b4-8d7c-26e0f5f221e9" />
		
	- But then I noticed missing chamfers on some sides, so I fixed it by adding 0.2 mm chamfers.
	
		<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b4153b65-293b-43bb-9258-9b31655f2e27" />

8. **Adding M3x30 mm countersunk screws for Z axis:**

	- I copied the screws from the other case.
	
		<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/8f1fab7c-7041-40ff-afe3-a667ff33e558" />
		
	- Deleted the extra two screws on the side.
	
	  	<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/482994d4-39e3-484b-bfff-9342b0c65ff3" />
		
	- Copied the screws to the other side. But I hadn't fixed the idlers yet.
	
		<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/5e2ede81-2062-482a-a2f2-83559a3e7b86" />

The idler case of the Z axis tensioning system is yet to be fixed. But so far, the other pulley/idler cases are done with their inserts and screws. Arranging the components in Browser was also left.

Here's the lapse of today's session: [PATRA-LPS-63-D83](https://lapse.hackclub.com/timelapse/PrdOEF78XoIv)

**Total time spent: 7h 20m**

---

# Day 84 — 11.10.2026: Addressing Missing Parts of Kinematic Base Module (KBM) — Part 2

The very first thing I did was arrange the components from last session in the Browser, and copy the Z axis pulley to the idler.

With that done, I decided to continue with the Motor Supports. The motor support was modeled, but the design didn't look any good. I wanted a design that would match the rest of PATRA. So, I deleted the feet extension, which I added for stability. I deleted that because it can't trip, as it would hold the motor's mass. I also added a combined cut with facial offset on the intersecting face for the back of the motor.

Thus, this is how it looked before:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/17581344-cc6e-4987-8328-3b0f10c16e0c" />

And this is how it looks after:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/17c3edac-9862-4cf2-a6ab-73bd8f6aec42" />

I copied this to make sure that there are three of them for each axis. For the Y axis, I used the mirror tool. This is how it looks from beneath:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c6997d8a-7f61-490f-b04b-5936734fc71d" />

While taking the screenshot for the under-view, I noticed the chamfers for countersunk screws, which were most likely wrong. This is because back then, I was assuming the dimensions. But now I know what chamfer dimensions are needed.

Here's what I did next:

- I first deleted all the chamfers.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0b55f1e8-eb04-4987-9cc4-767373dabee4" />
	
- Then I added the 1.3 mm chamfers.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/cb5e8b85-0093-4b06-b815-89d32dc766f1" />

But then I noticed that I was using connectors to connect the End Plate and the 4040 extrusions. But I realised that I can integrate the connectors into the End Plate itself, without making them separate and printing them separately.

- I used extrusion to fill the gap between the holes and the outer face.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a043b5c8-4e23-4264-9115-89a8a438a449" />
	
- Then I used the Combine tool to combine the connectors and the End Plate into a single body.

  	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/05174f4e-420c-4545-a556-d830980ec9ee" />
	
- Next, I noticed that the connector bodies are 0.1 mm high up in the air. So, using Extrude, I fixed that.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/efd8a70d-9355-4fc6-bb51-14bbb70359ea" />

But I made a devastating realization then. Actually, I can't just print the connectors. The width which is 5.5 mm is too thin and weak to house a M3 brass insert with is nearly 4.4 mm in diameter. But I can't even buy them, as the hole pitch won't match the 29.5 mm pitch of the screw for the pulley/idler cases. Additionally, they are quite hard to find and very expensive on most sites. That's why, before, I thought of printing them. I can't even print the threads, as it won't be reliable.

I searched for straight line connectors in MISMUMI, and I found [this](https://in.misumi-ec.com/vona2/detail/110310155069/). I found what I was looking for after a long search, but the pitch didn't match, obviously.

But I got the perfect idea to use M2 screws instead of M3. But I still needed to use inserts. So, I searched on OnlyScrews. They had M2x6 mm inserts with a 3.8 mm outer diameter. 3.8 mm outer diameter leaves only 0.85 mm on both sides, which will most likely fail.

I then started looking for slimmer M2 inserts, and after a long search, I found [this](https://robokits.co.in/robot-parts/nut-bolts-standoffs/nuts/m2-x-5-mm-brass-heat-threaded-round-insert-nut-moq-25-pcs.), a 3.5 mm outer diameter insert on Robokits.

- Once I was certain about the dimensions of the insert, I created a new sketch and drew all the correct dimensions of the diameters. Then I extruded it.
	
- Then I added 1.3 mm chamfers for the M3 holes and 0.2 mm chamfers for the M2 insert holes, after making the inner diameter of the M2 brass insert holes 3.1 mm.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/d0f4eeab-5381-4148-aac9-d161553fc17c" />
	
- Next, I extruded the brass inserts.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/716efc80-69a0-42c2-b2c6-464037acf1ea" />
	
- Then I added threads to the inserts.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0a278c54-a724-46eb-a719-8b9b3d54b65a" />

Here's the lapse of today's session: [PATRA-LPS-64-D84](https://lapse.hackclub.com/timelapse/5wXoN12hrMMv)

**Total time spent: 4h 00m**

---

# Day 85 — 12.10.2026: Addressing Missing Parts of Kinematic Base Module (KBM) — Part 3

I continued exactly where I left off yesterday. The screws were left to be added in the design. So, I added those.

**Adding M3x12 mm countersunk screws for endplates:**

- I first imported [this](https://cdn.shopify.com/s/files/1/0871/5295/1609/files/CSK_M3x12mm.step?v=1753268797) STEP file from OnlyScrews into the design and placed it in one hole using Joint.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8bc26337-f6dc-4702-9c0a-c6360d43d1f2" />

- Then I copied it first using Rectangular Pattern, then simple copy and paste.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4315bd14-df68-47ee-8449-8db0ec641cff" />

After that was done, I was supposed to add screws for the connectors next. I needed an M2x14 mm socket head screw, but I found none. After spending some time searching, [this](https://onlyscrews.in/products/m2-x-12mm-hex-allen-socket-head-ss-304-screw-dia-2mm-length-12mm) is the closest thing I found to what I needed. It is 12 mm, not 14 mm. 

Next was screws for the motors. I initially thought of 15 mm socket head screws. But there was no M5x15 mm socket head, only [this](https://onlyscrews.in/products/m5-x-15mm-phillips-pan-head-mild-steel-with-zinc-blue-plating-screw-dia-5mm-length-15mm) Philips button head screw.

Next, I updated the BOM. Here are the things I added to the BOM:

1. **M5 x 10mm brass threaded inserts**
   	* Quantity: 15
    * Unit Price: ₹4.60
	* Total Price: ₹69.00 / $0.72
	* Vendor: OnlyScrews
	* Link: [Product Page](https://onlyscrews.in/products/m5-x-10mm-brass-threaded-inserts)
	
2. **Brass Insert M3x10 mm**
	* Quantity: 50
	* Unit Price: ₹3.60
   	* Total Price: ₹180.00 / $1.88
   	* Vendor: OnlyScrews
   	* Link: [Product Page](https://onlyscrews.in/products/m3-x-10mm-brass-threaded-inserts)
	  
3. **Brass Insert M3x6 mm**
	* Quantity: 40
    * Unit Price: ₹4.80
   	* Total Price: ₹230.40 / $2.00
   	* Vendor: OnlyScrews
   	* Link: [Product Page](https://onlyscrews.in/products/m3-x-6mm-3d-printing-brass-threaded-inserts-dia-3mm-length-6mm)

4. **Brass Insert M2x5 mm [25 pcs]**
	* Quantity: 1
	* Unit Price: ₹63.00
	* Total Price: ₹63.00 / $0.66
	* Vendor: OnlyScrews
	* Link: [Product Page](https://robokits.co.in/robot-parts/nut-bolts-standoffs/nuts/m2-x-5-mm-brass-heat-threaded-round-insert-nut-moq-25-pcs.)
	
5. **Pan Head Screw M5x15 mm**
	* Quantity: 15
   	* Unit Price: ₹1.60
   	* Total Price: ₹24.00 / $0.25
   	* Vendor: OnlyScrews
   	* Link: [Product Page](https://onlyscrews.in/products/m5-x-15mm-phillips-pan-head-mild-steel-with-zinc-blue-plating-screw-dia-5mm-length-15mm)
	
6. **Countersunk Screw M3x30 mm**
	* Quantity: 50
   	* Unit Price: ₹3.80
   	* Total Price: ₹190.00 / $1.98
   	* Vendor: OnlyScrews
   	* Link: [Product Page](https://onlyscrews.in/products/hex-allen-csk-ss-304-screw-dia-3mm-length-30mm)
	
7. **Countersunk Screw M3x12 mm**
	* Quantity: 48
	* Unit Price: ₹1.80
	* Total Price: ₹86.40 / $0.15
   	* Vendor: OnlyScrews
   	* Link: [Product Page](https://onlyscrews.in/products/hex-allen-csk-m3-x-10-screw-pack-of-20)
	
8. **Socket Head M2x12 mm**
	* Quantity: 20
   	* Unit Price: ₹4.00
   	* Total Price: ₹80.00 / $0.83
	* Vendor: OnlyScrews
    * Link: [Product Page](https://onlyscrews.in/products/m2-x-12mm-hex-allen-socket-head-ss-304-screw-dia-2mm-length-12mm)

This was the updated section of the BOM:

| Item                          | Quantity | Cost(USD) | Cost(INR) | Total Cost |  Vendor      | Link                                                                                                                   |
|-------------------------------|----------|-----------|-----------|------------|--------------|------------------------------------------------------------------------------------------------------------------------|
| Brass Insert M5x10 mm         | 15       |  $0.05    |  ₹ 4.60   |  $0.72     |  OnlyScrews  | https://onlyscrews.in/products/m5-x-10mm-brass-threaded-inserts                                                        |
| Brass Insert M3x10 mm         | 50       |  $0.04    |  ₹ 3.60   |  $1.88     |  OnlyScrews  | https://onlyscrews.in/products/m3-x-10mm-brass-threaded-inserts                                                        |
| Brass Insert M3x6 mm          | 40       |  $0.05    |  ₹ 4.80   |  $2.00     |  OnlyScrews  | https://onlyscrews.in/products/m3-x-6mm-3d-printing-brass-threaded-inserts-dia-3mm-length-6mm                          |
| Brass Insert M2x5 mm [25 pcs] | 1        |  $0.66    |  ₹ 63.80  |  $0.66     |  Robokits    | https://robokits.co.in/robot-parts/nut-bolts-standoffs/nuts/m2-x-5-mm-brass-heat-threaded-round-insert-nut-moq-25-pcs. |
| Pan Head Screw M5x15 mm       | 15       |  $0.02    |  ₹ 1.60   |  $0.25     |  OnlyScrews  | https://onlyscrews.in/products/m5-x-15mm-phillips-pan-head-mild-steel-with-zinc-blue-plating-screw-dia-5mm-length-15mm |
| Countersunk Screw M3x30 mm    | 50       |  $0.04    |  ₹ 3.80   |  $1.98     |  OnlyScrews  | https://onlyscrews.in/products/m3-x-30mm-hex-allen-csk-ss-304-screw-dia-3mm-length-30mm                                |
| Countersunk Screw M3x12 mm    | 40       |  $0.02    |  ₹ 1.80   |  $0.75     |  OnlyScrews  | https://onlyscrews.in/products/hex-allen-csk-m3-x-10-screw-pack-of-20                                                  |
| Socket Head M2x12 mm          | 20       |  $0.04    |  ₹ 4.00   |  $0.83     |  OnlyScrews  | https://onlyscrews.in/products/m2-x-12mm-hex-allen-socket-head-ss-304-screw-dia-2mm-length-12mm                        |

But still, the screws for the Linear Rails and other parts are left. But for the tensioning system, the screws are done.

Here're the lapses of today's session: [PATRA-LPS-65-D85-1](https://lapse.hackclub.com/timelapse/uW1uWNp6xbwo) and [PATRA-LPS-65-D85-2](https://lapse.hackclub.com/timelapse/fa5BPyqrjwpY)

**Total time spent: 5h 20m**

---

# Day 86 — 13.10.2026: Addressing Missing Parts of Kinematic Base Module (KBM) — Part & Journaling

I still wasn't out of yesterday's flow state, so I started with mechanical design first. But deep down, I knew I had to journal sooner or later to get out of this debt. So, after a few minutes of addressing the screw holes for connectors in the 4040 extrusions, I journaled.

As I previously thought of using M3 screws for the connectors, the holes have a 3.4 mm clearance diameter.

So, I created a new sketch with a 2.4 mm clearance diameter.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/fb63e90f-b2b8-4caa-aa14-810137f16d3f" />

And then I extruded the sketch.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/569cff35-fb8b-437b-850e-76cc4ff4c563" />

I journaled days #46, #47, and #48.

Day #46

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f1a1b9f5-1f8e-4fe1-bd88-c592636738a5" />

Day #47

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/dda5484c-6170-4b3d-acf1-62425019a6de" />

Day #48

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/fa1116b5-5840-4987-92fc-a74598106e50" />

After today, these days are left to be journaled:

* Day #49
* Day #50
* Day #51
* Day #52
* Day #53
* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64

Here're the lapses of today's session: [PATRA-LPS-66-D86-1](https://lapse.hackclub.com/timelapse/q7r-0WpErT2k) and [PATRA-LPS-66-D86-2](https://lapse.hackclub.com/timelapse/-lW0wZMilQFT)

**Total time spent: 5h 35m**

---

# Day 87 — 14.10.2026: Journaling

Journaled days #49, #50, #51, #52, and #53.

Day #49

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b5d3082b-d5df-4842-9a6d-3bbe6c4cb234" />

Day #50

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/68e0b61d-82f0-41ac-9852-ddd066744988" />

Day #51

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/8832d2b5-9a07-4e95-a044-f769b0480593" />

Day #52

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/96519f70-ae86-463e-8eec-4b653c25e085" />

Day #53

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/dd297a30-22cc-48ae-8518-00c782e2354d" />

After today, these days are left to be journaled:

* Day #54
* Day #55
* Day #56
* Day #57
* Day #58
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64

Here's the lapse of today's session: [PATRA-LPS-67-D87](https://lapse.hackclub.com/timelapse/LjDu3gUB8yXM)

**Total time spent: 5h 30m**

---

# Day 88 — 15.10.2026: Journaling

Journaled days #54, #55, #56, #57 and #58 (partly)

Day #54

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4a4eab26-ae77-48ff-93d9-90acfcbe7c45" />

Day #55

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7e9d83c9-ea39-4d6f-abe2-70e0785a6f2e" />

Day #56

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/86b5752f-f995-47da-bef7-c5cf5ef3a18e" />

Day #57

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b128127e-f7f4-4685-b4f6-30bf528a2481" />

Day #58

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7e82268b-e25f-4d12-8324-33d68987adfb" />

After today, these days are left to be journaled:

* Day #58 (partly)
* Day #59
* Day #60
* Day #61
* Day #62
* Day #63
* Day #64

Here's the lapse of today's session: [PATRA-LPS-68-D88](https://lapse.hackclub.com/timelapse/B87cJ20xdBof)

**Total time spent: 4h 20m**

---

# Day 89 — 16.10.2026: Journaling

Journaled days #58 (full), #59, and #60.

Day #58

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e7f5e23f-fe80-4aff-bfe3-d910fef9accb" />

Day #59

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f7016905-6691-48a8-b816-a74a56ea7323" />

Day #60

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5fd38299-0e98-4efd-b225-5a8218723838" />

After today, these days are left to be journaled:

* Day #61
* Day #62
* Day #63
* Day #64

Note: Started Lapse late. I started working 30 minutes early.

Here's the lapse of today's session: [PATRA-LPS-69-D89](https://lapse.hackclub.com/timelapse/o1DvW-_qGENh)

**Total time spent: 6h 20m**

---

# Day 90 — 17.10.2026: Journaling

Journaled days #61, #62, #63, and #64 (partly).

Day #61

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/d5bc5d5c-e9a1-479d-ac2a-8608edb1c286" />

Day #62

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c0346858-108d-4e8c-a457-0f1c7729c510" />

Day #63

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ccafbc45-2ae4-4c1d-b899-4a39334428a6" />

Day #64

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6c30948c-f98b-4831-ac89-0eee7dde0848" />

Besides, using Grammarly, I grammar-checked days #1 all the way to #90, except day #64. Fixed many things from days #52 to #60.

After today, only one day is left to be journaled, after today.

* Day #64 (partly)

Here's the lapse of today's session: [PATRA-LPS-70-D90](https://lapse.hackclub.com/timelapse/jlPXhm_LF2zE)

**Total time spent: 7h 10m**

---

# Day 91 — 19.10.2026: Journaling & Reconsidering Motor Driver Choices

Journaled day #64 (full).

Day #64

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/17552fc5-34d5-4407-a27a-687c12b52d5f" />

With this, not a single day is left to be journaled. I am finally free of my journal debt!

Day #45 lacked images, so it didn't meet the entry requirements for Forge. So, I had to add images.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f6611bef-f5b3-41e9-a1cf-fe0a94238376" />

With this, all entries meet the requirements for Forge.

These days, while I have been journaling, I have noticed a very big problem with my electronic system in this project. It is about the Rtelligent T60 and T60S motor drivers. On day #44, I chose the Rtelligent T60S over the T60 without looking at the rated voltage. For maximum performance, I am going to use the power supply, Mean Well LRS-600-48V, which was already confirmed before. But the problem here is that the Rtelligent T60S supports 18 to 50 V DC power supply. 48 V is technically within that range, but it does not provide any safety headroom. It is much better to instead use the Rtelligent T60, which supports 18 to 68 V DC. 

Thus, I updated the bill of materials, removed the Rtelligent T60S, and I replaced it with this:

* **Rtelligent T60 Closed-loop Stepper Motor Driver (X, Y & Z)**
   	* Quantity: 3
    * Unit Price: ₹ 4,039.00 
	* Total Price: $127.79
	* Vendor: Robu
	* Link: [Product Page](https://robu.in/product/rtelligent-t60-closed-loop-stepper-driver-18-68vdc-6a-for-stepper-motors-below-nema-24/)

Looking at the BOM, I suddenly remembered that I was now using genuine HIWIN components. The vendor I am sourcing from has the MGN15H linear block with black-colored ends, so instead of keeping my model green and red at the ends, I made it matte black. 

So it went from this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/69aaf8bf-9f9d-4446-b1bd-d3831200debe" />

To this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2a07173f-cf01-410c-940f-8a0c8d8b825f" />

Once that was done, I made another change I should have made long ago: adding fillets to the 90-degree edge of the belt clamps.

Here's how I did it:

- I created a new sketch on the teeth plane of the X axis belt clamp lower

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0237f506-fb36-4131-b80d-15c3646c16a7" />

- I copied one tooth out of the shape.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/b5883be7-e883-408a-b906-c6c400074881" />

- Next, I projected the clamp itself to mark the outlines.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/506b2076-0afa-4f1b-8a54-8a300784520b" />

- Bridged the gap with straight lines, and I had this shape:

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/66b8986a-5dd8-43a6-a5fa-1ff4cd14cf7f" />

- Did the same on the opposite side as well.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f57f08e9-179b-4807-b72a-26a0c8326e9b" />-

- I extruded the extreme ends of the sketch, and I used the join tool.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/aceecdc8-7095-455f-a455-d027e8a01612" />

- But after combining them, I noticed that there is unnecessary randomness in the dimensions, which must be addressed.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/edf8f175-66c7-4fb2-9ff3-5b538ae36ab5" />

Please note that when I started working in Fusion today, due to some problems, I had to close the design, and as a result, I lost progress up to day #86. I have to start over again the next day.

Here's the lapse of today's session: [PATRA-LPS-71-D91](https://lapse.hackclub.com/timelapse/bvvssjpO0AF4)

**Total time spent: 5h 00m**

---

# Day 92 — 20.10.2026: Fixing the X, Y & Z Belt Clamps

I picked up exactly where I left off yesterday: fixing the uneven X and Y belt clamp. Here's how:

- I created a midplane on the body first.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2c5c1d78-f8de-4472-8fc9-f5dda547e885" />

- Used Split Body to split the body.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3b54a416-6749-4977-83b1-8e0ee2d47e11" />

- I copied and moved the upper filleted and flat part of the crests 5 mm on both sides.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/50285e96-20a8-423e-9efb-4929aea617fc" />

- This is how uneven the shape is.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/74490c7d-91a3-46e8-adee-f8e851254d54" />

- Drew a dead-straight line connecting the crests of the far ends.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5b157d3b-fc80-4420-927a-75a90cb003a6" />

- Due to some problems, Extrude wasn't working on the sketch, so I instead used Split Body to cut the uneven parts.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a6b59685-eea8-490b-ae27-33d66fd9d032" />

- The extra uneven side was sliced off, but I also discovered uneven crest heights for the teeth.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7b894e28-1426-4b6d-8a8b-d2747ee37c77" />

- Even in individual crests, the Z position doesn't match.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7fa60129-53db-4717-a11c-3420070e017b" />

I then decided to make a new clamp, wondering why I always have to start over. But I needed to inspect the source of the problem. And just as I suspected, the teeth profile itself was crooked. Because one the height of one side of the profile was 2.12753874 mm, while the other was 2.13 mm. The second one is accurate, as the height of a tooth is 1.93 mm. With 0.2 mm clearance added, it is 2.13 mm. Fixing the teeth was crucial, so here's how I did it:

- I made a vertical line in the center and used Break on the valley arc.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6dca3ad2-a19d-4b14-95f8-d8c5c8cd7ce8" />

- Next, first deleted the wrong side completely, leaving only the correct one.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/32ec1319-b858-4367-b554-e3645c6d9d4a" />

- Used Mirror to mirror the right side of the deleted one.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3261ec4e-d041-40b5-9859-073a3b7cf4a3" />

- Deleted the projected arcs and the mirror line. Dimensions are accurate.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f2b64c9a-34bd-4a1e-94ff-176a40dc0b54" />

I then finally had the ability to create a new clamp with the correct dimensions. Here's what I did:

- On the same sketch, I copied the tooth to a distance of 5 mm.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5ac66ddf-84ad-44cb-ba45-0d41c8864e29" />

- Drew a line on the centre of the clamp.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5d61f887-550f-4c7c-8815-f8fa03ec44d0" />

- Placed the two teeth in the centre by moving them -20.00974711 mm.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/cf01e1c1-ad08-42e2-afcf-72ebd4e1ef59" />

- Used the Rectangular Pattern to copy it 10 times.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0d7dd210-e987-4d88-9418-cb0c6d8a7262" />

- Added curved ends to both sides.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/57fe6cac-978b-46e0-93cc-fb71bf11f20f" />

- Joined all the missing lines.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0526cb18-113c-4420-b4ef-2468dd4731aa" />

- Then I extruded the belt profile.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/8c4f2b68-eabc-41ec-88a2-8cb9724a0956" />

- Split the body of the previous clamp, deleting the teeth.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2f4abc69-d322-4345-abfd-78b775529f25" />

- Extruded the clamp 5 mm up to give it more height to cut.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/bfed4c5a-9cb4-4590-8a77-04b0b2a7d683" />

- Used Split Body to cut the extra geometry.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e0c465cd-e299-44bf-9da4-dc73bbfd00d3" />

- Extruded the clamp to the extra length added on both sides.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6cbdccd8-3d18-4f25-8619-da368515ad30" />

- Used the Construct plane to mirror it.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/502790ee-e4ae-46df-b722-468952175b77" />

But during this, I captured the reason behind probably every single dimensional error. I extruded this correctly, but the teeth profile I made is still 51.64655384 mm long, while the old clamp is 51.64854897 mm. I don't seem to find the reason why. The logic is simple: if Fusion rounds off extruded features, why does it see a body, face, or edge as thick as a tenth of a nanometer as a separate body, face, or edge?

I wasn't going to take any risks, so I completely deleted the old clamp body, or whatever of it was remaining, and did this: 

- I used the sketch that I used to make the new teeth profile to extrude a new body and join it with the teeth profile on both sides.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/48f4f9b8-a68e-4a68-ac26-101a6eb3def6" />

- I added holes in the correct places.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2e9c3829-30b3-4026-a9c5-8ab033955d0d" />

- After removing the old clamp, adding appearance, and arranging the bodies in the Browser, this is how it looks:

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/a7bb0b85-7439-4f63-b481-54801a2a937d" />

As the clamp is now slightly longer, I must readjust the clearances.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/63378291-32e6-44c5-9776-077752e3d903" />

This is how it looks with the correct clearances:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/62113896-5626-45ae-a2da-b715c2796b76" />

Next, it was time to fix the Z-axis tensioning system bottom clamp. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f668ba7d-9f3a-4cf4-9f30-c3fddc977bab" />

Here's how I did it:

- Using Split Body, I isolated the teeth profile.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6a57fbaa-cd06-4c1d-992c-cb8bfd0390e3" />

- After copying the X clamp bottom, I did the same.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1bc1c97b-ca47-4c09-8b2a-24513d832ce8" />

- Moved the teeth profile to the place of the Z bottom clamp teeth profile.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e80d5f35-dde7-48c6-8c7d-da823d5344da" />

- Extruded the teeth profile to the bottom of the Z bottom clamp.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/29f66bf2-301b-4f98-b371-02640268731a" />

- Combined the bodies.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6453cf1b-4e4f-4f1c-82bc-cb2125f30750" />

- Using Offset Face, I made the faces deeper by 0.5 mm.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/044e0bef-ab6d-4399-96fe-a15f3cb58be2" />

- After extruding the remaining faces, the clamp is complete.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9465bd57-d3bd-4885-842e-8ca67b24414d" />

Here's the lapse of today's session: [PATRA-LPS-72-D92](https://lapse.hackclub.com/timelapse/Uy8AiN9iMsvQ)

**Total time spent: 3h 00m**

---

# Day 93 — 20.10.2026: Rigidly Connecting the Aluminium Extrusions

I wanted to speedrun to complete the Kinematic Base Module strategically. So, I decided to live through the assembly process to see what connects to what and fill all the missing gaps in the system. These are the components in the KBM:

- Aluminium Extrusions
- End Plates
- Linear Guides
- Tensioning System
- Motors
- Supports

I have arranged them on the basis of assembly sequence. This meant that I was going to start from the most fundamental component of the KBM: the aluminium extrusions.

These are the aluminium extrusions.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e0d3ddff-0178-4914-9398-02f1554d51f8" />

There are:

- Two 4040 extrusions (HFS5-4040-1000)
- Two 2020 extrusions (LCF6-2020-1135)

But I realised that there was nothing in the assembly to connect them rigidly. I didn't want the entire system to rely on the End Plates. So, I had to find a way to connect these extrusions, like this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/aa132bba-654d-448b-b2d3-d23a760a8ebf" />

I needed a way to connect the 2020 extrusions with the 4040 extrusions side by side, but I could not find a reliable way to connect them side by side anywhere on the internet; they have different profile sizes. But I got a really good idea to connect the lower 2020 extrusions with the 4040 extrusions. I could make my own custom side-by-side connector, and here's how I did it. 

- I created a new sketch on the 2020 and 4040 extrusion profiles.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9f39b064-9db0-4f58-8ff0-63f402616a07" />

- Sketched a new connector profile with 0.2 mm clearance.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f4f1de64-8c08-4446-a0e3-1c4898284a9e" />

- I extruded the connector at a length of 25 mm, but I was still not sure how I could connect the 4040 extrusions rigidly with that.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5b8befa5-3350-4a76-bf50-bc3cc8794499" />

One very good way to rigidly connect them would be to drill a 100 mm hole through the 4040 and 2020 extrusions and connect them all with a single bolt. The problem is that I don't have a drilling jig for extrusions, and I cannot even tap holes inside my own house. Misumi is not providing the holes where I need them, nor do I have any drilling jig nearby. I was very confused at that point.

Then I suddenly remembered that I had forgotten to change the M3 holes to M2 holes for the aluminum extrusions, so I did that.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/fc11c7d7-2261-4ac4-a7ab-4a914f3c514d" />

After doing that, I got a really good idea that I could technically connect everything without a single screw. It won't even be visible and would make the system much stronger. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2bd28621-5848-4a52-be71-d1d1e9ab73cf" />

In this sketch, which I have created, the Z-axis return belt gets shielded from all four sides. The 4040 extrusions are now rigidly connected to the upper 2020 extrusions, and the two more blocks that I created in the step before directly connect the lower 2020 extrusion with the 4040 extrusion. There are 0.2 mm clearances all around, and I've also added fillets on the internal corners of the walls for the Z return belt. 

The following shape, with added screws and nuts, would make the overall system extremely strong, even though it will be 3D printed:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/129dfd5e-5a23-44b1-b734-3bc81193817e" />

I'll obviously make sure that the 3D print is done with maximum density and with top filaments like PETG-CF. It is extremely easy to make my own custom 3D-printed bracket for the aluminum extrusions, but I believe that it is extremely hard to tap the aluminum extrusions so that I could reliably connect the custom brackets. This was my biggest roadblock. 

I could use this shape for the extended part for the two 2020 extrusions:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/389029cc-dd47-46b6-b5c9-4b5c95a1ce9e" />

I also added fillets to the entry points and exit points for the belt. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6c311b5a-855f-4bab-9f19-17ccbe103e15" />

I also deleted unnecessary faces that made the shape much more dimensionally accurate and printable. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/9625dabb-e1c4-4173-a12a-a8f1ed5aa4ca" />

By the very end, I actually wanted to model all of the screw holes needed in the 4040 and 2020 aluminium extrusions, due to which I also did something which I should have done a long time ago: adding the screw holes for the linear guides on the flat face of the 4040 extrusion. Here's exactly how I did it:

- I created a new sketch and projected the flat faces of the 4040 extrusion that were facing up.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0281ecf6-ee8d-4308-9d7e-54756e352d39" />

- Then I added 3.5 mm holes with a distance of 40 mm between them, making sure that the first hole is 20 mm away from the edge. 

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2d559b26-aca7-4c6b-a01e-72e487a0b2f7" />

- Using a rectangular pattern, I copied it 25 times on each extrusion face.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0fab221c-0677-478c-873b-56e715f2eeb2" />

- Then I extruded it to cut the holes in the extrusions.

	<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/eecaeb05-ad8f-4ee7-bceb-2c03ab8d5775" />

With this, the holes are finally added on the 4040 extrusion faces. Next, I needed to find a way to connect the linear guide to the extrusion reliably. It was hard because of the fact that I cannot use drop-in T-nuts, as I am placing it dead center on the flat face of the 4040 extrusion. But after speaking with Google AI, it recommended that I use rivet nuts.

But one more problem arose: I can absolutely not have the linear guide sit not flush against the flat face. If I used regular rivet nuts, it meant it would be 0.5 to 1 mm higher up on the face. If I wanted it to sit flush, I had to use countersunk rivet nuts, but to use countersunk rivet nuts, I had to drill countersunk holes. Drilling holes in the first place is hard for me, let alone countersinking them to use countersunk rivet nuts. 

So far, I understood something: it is extremely easy to make your own custom brackets, but altering a metal aluminum extrusion, when you only have a 3D printer with no jig, CNC, or a machinery lab hardware, is extremely difficult, especially as a student.

At this point, I had realised:

- 2 mm thick aluminium is way too thin to grip the linear guide rail by thread, let alone the entire linear guide, tripteron, and later the robotic arm.
- No tool would reach past 70 mm from either side of the extrusions, so I can't fasten the nuts if I drill clearance holes into the flat face.
- Using rivet nuts is structurally sound, but it would raise the linear rails and make the entire thing above it unstable.
- Countersunk rivet nuts need a rigid and dedicated jig for the chamfers on the extrusion, and the wall is just 2 mm thick.

It seemed that the best way to clear this roadblock was to actually speak to professional, real engineers, not AI.

I also started worrying about the holes that are passing through vertically to connect the end plates to the 4040 extrusions. I didn't know if it would be reliable or if I could actually drill those holes by hand. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/dba5b5e1-2542-4ae6-a694-467467a90ae4" />

Yeah, but it is indeed true that I had the ability to print some kind of alignment block that I could use to drill the holes on the extrusions. I can't even possibly change the position of the linear guides to make them positioned directly on the hollow profile so that I could use T-nuts. That way, I would have to redesign the entire TriTeron. 

After all this thinking, I decided to arrange the components that I created today in the browser, and that was the end of today's session. I saved the kinematic base module in Fusion. 

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e34e5868-1848-4a25-959d-10f5a4ff8930" />

Here's the lapse of today's session: [PATRA-LPS-73-D93](https://lapse.hackclub.com/timelapse/Iya6jc8WFlgv)

**Total time spent: 5h 00m**

---
