---
**Title:** PATRA (Parallel Axis TriTeron Robotic Arm)  
**Author:** Sunrit Hazra  
**Description:** A Hybrid robot architecture of a kinematically linear 3 DOF parallel axis triteron system and a 6 DOF serial robotic arm.  
**Created on:** 2026-05-02  
**Progress (%): 33.33%**
---

# Day 0: Flashback

A Random Day in December, 2025, I was scrolling through my YouTube feed. I came across this [video](https://www.youtube.com/shorts/74T0LF2l5Ck) with TriTeron Robot concept. The mechanics were immediately impressive — a clean parallel axis system with a movement profile I hadn't seen in a hobbyist build before. The logical extension was obvious: mount a robotic arm on the head, and you get something that combines the workspace coverage of a gantry with the dexterity of a serial arm. I thought that is really cool.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ff8585a7-c18c-4249-9e0b-f1dbca4265bf" />

**Total time spent: 0h 1m**

---

# Day 1 — 10.04.2026: Planning & Studying

Ever since I was a member at Hack Club, I wanted to make a TriTeron robot. Originally, I thought of doing this project in **Blueprint** as two separate modular projects: **TriTeron Robot** for $400 and **Robotic Arm** for $400. But Blueprint ended even before I could start. So, I chose Fallout. I didn't start there either, partly due to running Construct and Stasis in parallel, and partly because the scope wasn't clearly defined enough.

This is the Tipteron Robot built by Rudmin:

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1e31c116-bfa6-4f96-a2c2-00662f581cc6" />

The right opportunity came with Forge. The Tier 1 has unlimited budget but I capped the budget at $700, which is was tight but workable.

Here's what shaped my thinking, and inspired me:

* [This](https://www.youtube.com/shorts/74T0LF2l5Ck) is the video that first sparked my interest.

* [This](https://www.youtube.com/watch?v=6EtXycVGJg4) video by Rudmin introduced the original concept.

* [This](https://www.youtube.com/watch?v=io4S9amExNM) video by [Not An Engineer](https://www.youtube.com/@NoEngineerHere) introduces the carriage system. I watched this multiple times specifically to understand how the X and Y axes are driven independently on the carraige.

* [This](https://www.youtube.com/watch?v=3fbmguBgVPA) pushed me toward adding a robotic arm, and gave me a ough idea of what style robotic arm I could add.

* [This](https://www.youtube.com/watch?v=MeRaYVntxMk) is a solid breakdown of the differences between serial and parallel systems. PATRA essentially combines both, which is why understanding this distinction matters.

To get started, I did focused research on the following (only this time is counted):

* **Kinematics:** Beyond just the general definition, I read articles and watched detailed videos specifically on parallel axis kinematics and kinematically linear systems. I also explicitly read [this](https://en.wikipedia.org/wiki/Kinematics) Wikipedia page, and watched [this](https://www.youtube.com/watch?v=3fbmguBgVPA).

* **Robotic Arms:** I did a deep dive into 5 DOF and 6 DOF robotic arms, studying their structure, joint arrangements, and torque requirements. I also carefully studied the Meca500 robotic arm as a size and precision reference.

* **Linear Belts:** Although I was already familiar with them, I studied motor selection, torque transmission, belt pitch types, and tensioning systems in more detail.

* **Ball Screws:** This was a completely new concept for me. I learned that ball screws offer higher precision and better load handling compared to belts, but at the cost of speed and higher complexity.

* **Aluminium Extrusions:** I knew nothing beyond 2020 and 4040 aluminium extrusion. So, for the sake of this project, I made a deep dive into JLCMC's Aluminium Extrusion Profiles, and I read their [datasheets](https://drive.google.com/file/d/1X2043j8HutSmY2QTKigUobWLhu9sI9k2/view?usp=sharing).

* **Zaber LC40:** Rudmin used [LC40 family](https://www.zaber.com/products/families/LC40) for the TriTeron, which is configurable, belt drive, t-slot profile linear stages. Prices were mostly in the $2000–$3000 range, which is consistent with industrial-grade configurable stages.

**Things I Learned:**

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

**Total time spent: 6h 0m**

---

# Day 2 — 11.04.2026: The First Pitch

Time for the first pitch. I had a rough plan, ran a sanity check on it, sketched it out on paper, and then spent several hours researching parts on Google and JLCMC. I also used AI for sourcing — primarily as a search tool, not for generating content — to find parts on sites I wouldn't have otherwise located. From that, I assembled a rough BOM with an initial target of $500 for the TriTeron and $500 for the 6 DOF arm.

The honest problem at this stage was that without any CAD done, the plan was still too abstract. I drew seven different versions of the thing before settling on what to pitch, which tells you how much I was still working it out. Still, the goal was to get external feedback early rather than spend weeks refining a plan in isolation.

After writing the draft and building the BOM manually, I pitched in the #forgery channel.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/afd7d77b-3889-44e8-b776-08f510aa0ad4" />

The most frustrating part of this phase was the overwhelming number of choices. Linear guides alone had dozens of variants across multiple vendors, with no clear basis for choosing one over another without more context. That changed gradually as I got deeper into datasheets.

**A little fast forward:** This project was returned for changes by the reviewer on **14th April, 2026**. I did not make any changes as he said, but my overall plan had changed significantly by then. So, I re-pitched officially on **30th April, 2026**.

**Please note that I did not use AI for any fields of the pitch. I have only used it to search the sources of my parts (pretty much like Google, but better). Then, manually I visited the sites and made the estimates. Please try to understand.**

**Summary of today's session (Day 2):**

1. Developed the first formal pitch for PATRA based on preliminary planning and research.
2. Created multiple design sketches and evaluated different architectural possibilities.
3. Assembled an initial bill of materials with separate budgets for the TriTeron and robotic arm.
4. Performed extensive component sourcing and feasibility analysis.
5. Submitted the project for external review to gather technical feedback and validation.

**Total time spent: 4h 52m**

---

# Day 3 — 12.04.2026: Starting to Model

I started by rewatching [Rowan's video](https://www.youtube.com/watch?v=io4S9amExNM&t=1s) from start to finish, this time specifically tracing the carriage assembly — how it moves, how the X and Y axis legs are attached, and where the belts actually run. He has a Patreon with the Fusion file, which I downloaded and used as a structural reference. Not copied wholesale — just as a baseline to understand what I'd be modifying.

I then created the project in Fusion and imported the relevant reference geometry.

The plan at this point: follow Rowan's carriage approach (independently driven X and Y axes), but substitute a ball screw for the main axis, on a 1 metre rail.

I started with the 4040 T-slot aluminium extrusions. I re-read the [datasheets](https://drive.google.com/file/d/1X2043j8HutSmY2QTKigUobWLhu9sI9k2/view?usp=sharing) and downloaded the STEP files for [TXCL-H7-4040E-L1000](https://jlcmc.com/product/s/T01/TXCL/extruded-aluminum-t-slot-40-series(eu)-8mm-slot-width?k=TXCL-H7-4040E-L1000&productModelNumber=TXCL-H7-4040E-L%5B50~6000%2F0.1%5D) from JLCMC — $8.99 each, which is reasonable. Added two to cart.

Then the Ball Screw. After reading the datasheet, I settled on BSUF-C7-20-5-L640-F30-P12, added it to cart and downloaded the STEP file.

Same process for the linear guides — chose E-BMN15H-2-L1000-ZF-C-E20, two of them added and downloaded.

As a sizing reference, I downloaded the [Meca500 CAD model](https://www.3dfindit.com/en/digitaltwin/meca500-assembled?path=mecademic%2Findustrial20robotic20arms%2Fmeca50020six-axis20robot20arm%2Fmeca50020assembled.prj&mident=%7Bmecademic%2Findustrial20robotic20arms%2Fmeca50020six-axis20robot20arm%2Fmeca50020assembled.prj%7D%2C013+%7BLINEID%3D10%7D++%7BNB%3DMeca500+Assembly+simple%7D%2C%7BORDERNO%3DMeca500+Assembly+simple%7D%2C%7BMOUNTING%3Dany+orientation%7D%2C%7BPAYLOAD%3D0.5+kg+rated+%28max.+1+kg%29%7D%2C%7BREACH%3D260+mm+%28see+diagram+below%29%7D%2C%7BWEIGHT%3D4.5+kg%7D%2C%7BNAME%3DMeca500+Assembly+simple%7D%2C%7BSOURCEURL%3Dhttps%3A%2F%2Fwww.mecademic.com%2Fen%2Fdownloads%7D) from 3Dfindit, and skimmed the [official documentation](https://resources.mecademic.com/en/doc/MC-OM-MECA500/11.1/mc-om-meca500.pdf). This wasn't for replication — it was just useful to have accurate geometry in the assembly to check proportions.

After roughly half an hour of assembly:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ae1e4371-f2ac-4b45-ac44-78ecef0699c0" />

Then came the cost check. Shipping from JLCMC alone was over $200 even on the cheapest option, before customs. At 35–50% customs on top, this approach was clearly unworkable for the budget. Deleted the cart, noted the lesson: source locally wherever possible.

Dropping the 1 metre rail brought its own constraints. With 500 mm usable travel, the TriTeron needed to be scaled up to preserve the arm's proportions — and that scaling introduced two problems. First, the robot looked disproportionate. Second, the available travel was now borderline inadequate for the scaled frame.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/19ec1236-b435-48a9-bfb8-c7fb5c37ef8a" />

I spent another three hours iterating — trying smaller JLCMC variants, adjusting the usable length to keep costs down:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/51f2d2e0-dca3-43d2-9c9e-54db52e20baf" />

The proportions weren't working. I took a step back and reconsidered the carriage architecture itself. Instead of following Rowan's design where the motors are remote and belt-driven to the carriage, I tried making the carriage self-contained — motors mounted directly on it, freeing up the rail geometry. This meant extending the carriage base using extrusions on the front face and rethinking the drive path.

After more hours of iteration:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/28d18e54-e5e2-471f-a430-8d8cc5a90f1b" />

For a rough picture of how I did the CAD throughout today, [here](https://drive.google.com/file/d/17hyzQvfrPkSDDIoYjY-ttWvvfYUGDrAG/view?usp=sharing) is a timelapse-like video, exploiting the Fusion Timeline. Fusion being parametric saved a lot of time here.

**Summary of today's session (Day 3):**

1. Began CAD development by studying Rowan's carriage-based TriTeron architecture.
2. Imported reference models and established the Fusion 360 project environment.
3. Planned a hybrid architecture combining carriage mechanisms with ball-screw actuation.
4. Started modelling the primary structural framework using aluminium extrusions.
5. Used existing designs as educational references while preparing for future modifications.

**Total time spent: 8h 12m**

---

# Day 4 — 13.04.2026: The CAD Failure Day

The plan today was to ignore the rail sourcing problem entirely and focus on adding motion using As-Built Joints. The X and Y leg joints went in initially without issue, but the assembly quickly became inconsistent — components were referencing incorrect parent frames and the motion wasn't physically meaningful.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/492c4516-e10d-4c0a-946f-2e5b47b9d086" />

I dropped the joint work and instead scaled the TriTeron up by 1.5x to better fit the Meca500 at original size. In doing so, I also noticed the two sides of the frame were asymmetric — fixed that with a split body approach, deleting one side and mirroring.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/93acdf6c-3b9c-457f-8c5d-3f718d41657e" />

At this scale, the travel envelope was clearly insufficient. 600 mm started to look necessary, so I did a rough BOM check on paper to see how much that would push the cost — which took more time than expected.

I re-added the joints one leg at a time. This was faster than the first attempt, but the slider joint didn't resolve correctly. I traced the issue back to the scale step in the timeline, found the relevant operation, and scaled the slider to match — which introduced further downstream problems. After fixing those and completing the joint set, the motion was at least physically plausible for the first time.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/667bc22a-e696-4321-8b5e-c26f8a8732b1" />

From there, a sequence of smaller adjustments:

* Made the tool head larger so the Meca500 base seats correctly — about 10 minutes.
* Went back and forth between 1.25x and 1.5x scaling, editing the timeline directly, trying to balance proportions against motion clearance — about 1.5 hours.
* Attempted to shorten the carriage slider to give the robot more room to move — about 40 minutes.

The result of all of this: disproportionate geometry, and motion joints that had drifted out of the correct configuration again. The scaling changes had accumulated too many dependencies in the timeline.

Decision: delete all joints, reset the motion setup, and re-examine the underlying plan before continuing.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/183ff45a-b18b-4c35-99e1-2a7a8030f256" />
<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3c7e5950-0ebe-4217-807d-f8d1e3b2d580" />

No pitch response yet. Waiting on that before making any major structural decisions on the build.

**Summary of today's session (Day 4):**

1. Experimented with Fusion 360 joints and assembly constraints for motion simulation.
2. Encountered challenges in achieving correct kinematic relationships between components.
3. Shifted focus toward refining the structural design rather than motion studies.
4. Rescaled the mechanism to better fit the intended robotic arm dimensions.
5. Improved frame symmetry by rebuilding and mirroring major structural elements.

**Total time spent: 5h 50m**

---

# Day 5 — 14.04.2026: Post-Pitch-Review CAD & Research

First [pitch response](https://hackclub.slack.com/archives/C0AQG3VPQDD/p1776140495172719?thread_ts=1775931663.812209&cid=C0AQG3VPQDD) came in. The reviewer didn't flag issues with the project concept itself, but pointed out a better driver and an alternative sourcing approach. Both were actually useful — the driver suggestion changed how I was thinking about the control architecture, and the sourcing direction helped clarify what was realistic within budget constraints.

That led me to reconsider the overall scale of the build:

* Use a 1 metre rail instead of 500 mm?
* Keep the robotic arm at original Meca500 size?
* Scale the TriTeron to 1.75x the original Rowan design?

These changes don't necessarily blow the budget — the question is whether the rail length and proportions can be made to work within the $700 ceiling with Indian-sourced parts. I spent about an hour and a half testing different rail lengths and linear guide models in Fusion, importing actual STEP files to check fit rather than guessing.

I also did a rough manual torque calculation for the main axis, which came out to approximately 1.1 Nm. That sits in the range where the best NEMA 17s are marginal and a mid-tier NEMA 23 is more appropriate. JLCMC had a wide selection, so most of the motor research was done there alongside their datasheets.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c2d27b79-ea12-4ee8-9492-0111a22336d0" />

I imported the 42CM08 motor model into Fusion to check spatial feasibility for my original plan — motors mounted directly on the carriage. The result was clear: two NEMA motors on the carriage make it significantly bulkier, and the placement geometry doesn't work cleanly. The approach that both Rudmin and Rowan use, mounting motors off the carriage and transmitting via belt, makes more sense mechanically. Testing with a 600 mm 4040 extrusion also confirmed that it's too short for the scaled design.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/927c9935-bbf2-4ddb-8740-0aa628d0fd2a" />

I started yet another BOM — this time separating Indian-sourced components from JLCMC components, and adding shipping and customs estimates to each. The conclusion was unambiguous: JLCMC isn't viable for this project given the import costs. Everything needs to come from Indian vendors.

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

I [re-pitched](https://hackclub.slack.com/archives/C0AQG3VPQDD/p1777518863427759?thread_ts=1775931663.812209&cid=C0AQG3VPQDD) PATRA in the Forge channel. The project description stayed mostly the same; the significant change was the BOM. Rail length was fixed at 600 mm usable travel. About 40 minutes of additional research went into tightening the component list and price estimates.

**Worth noting:** the sources listed below are indicative, not finalised — they establish a price baseline using mean market values. The actual sourcing will be determined after approval.

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
HTD 20T Aluminium Pulleys (4 pcs) – ≈ $20 USD
Example pulleys:
[Link](https://www.amazon.in/Timing-Pulley-Bore-6mm/dp/B08CXZ7VMH)

Frame + Structure
4080 + 4040 Aluminium Extrusion (cut locally) – ≈ $170 USD (combined)
Sources for Indian extrusion retailers with custom lengths:
Search on India marketplaces like India Mart for:
"2040 T-slot aluminium extrusion all lengths"
"4040 T-slot aluminium extrusion custom cut"
Example extrusion supplier:
[Link](https://www.indiamart.com/proddetail/aluminium-t-slot-extrusion-6762050720.html)
Aluminium Plate ~10–12 mm (Custom CNC cut) – ≈ $70 USD
Local metal supplier or shop near you can cut to size.

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
[Link](https://www.amazon.in/2-Axis-Stepper-Motor-Driver/dp/B01MTOYCRA)
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
SectionEst. CostBall Screw & Support~$90Linear Motion Rails & Blocks~$85Belt Drive Components~$45Frame & Plates~$240Motors~$140Drivers & Power~$90Controller + I/O~$40Misc Hardware~$40Total≈ $700 USD

**Summary of today's session (Day 6):**

1. Investigated CNC manufacturing options for custom robot components.
2. Requested and compared quotations from multiple fabrication services.
3. Analyzed manufacturing costs against overall project budget limitations.
4. Evaluated the practicality of CNC machining versus additive manufacturing.
5. Decided to prioritize 3D printing for most custom structural components.

**Total time spent: 3h 55m**

---

# Day 7 — 01.05.2026: The Research for Sanity

Yesterday I pitched the project again. The BOM was assembled from placeholder sources to establish price ranges — today the goal was to actually commit to real components, working from the structural base upward.

Going back to first principles, I re-watched the [original TriTeron video](https://www.youtube.com/shorts/74T0LF2l5Ck) to re-anchor the architecture.

Something worth admitting: the reason I had switched to [Rowan's carriage approach](https://www.youtube.com/watch?v=io4S9amExNM&t=1s) in the first place was that I hadn't correctly understood [Rudmin's drive system](https://www.youtube.com/watch?v=6EtXycVGJg4). Specifically, I missed that there are two independent outputs on a single rail.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/43b30add-53ae-4e89-a968-f8cbf16d96b9" />

Looking at it again: the front two Z-axis legs are controlled by a belt running through the centre. There are three belts total, and once I spotted the middle one, the whole system clicked. The two outputs on a single rail aren't separated by physical distance — they're driven by independent belt loops running in the same channel.

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
* [TB6600 Stepper Motor Driver](https://robu.in/product/tb6600-stepper-motor-driver-controller-4a-942v-ttl-16-micro-step-cnc-1-axis-upgraded-version-425786-stepper-motor?gclid=CjwKCAjwntHPBhAaEiwA_Xp6RtwUATtWsr6ENAJnefCDD7A_hFCG6G0U4FvI7KcqhoYZApcELbKBxhoCF8cQAvD_BwE&gad_source=1&gbraid=0AAAAADvLFWeX0A7E-QWDpuYY72tUYPPuB&gad_campaignid=20381096599) — Robu.in.
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

Today the pitch was approved finally. Now I am finally sure that I can continue working on this project. Thanks a lot, to Souptik Samantha for the pitch approval! I decided to adopt strategy this time, not random guesses.

I made the following finalised decisions:

* I will make the usable rail length 900 to 950 mm.
* I am absolutely eradicating ball screws from my project, for linear belts.
* I will keep the arm size at the size of Meca500.

I now finally had everything nescessary to start modelling my PATRA again, with a clear goal in my mind. But looking at my BOM, and clicking those links, I saw that not a single source I have selected has a 3D model attached with them. That changed the direction of the entire day. Up until this point, sourcing was a cost problem. Now it became a CAD problem. Every link I had carefully collected — Robu, Robokits, Novo3D, Amazon listings — had images, basic specs, sometimes even dimensional drawings. But no STEP files.

And this matters more than it sounds.

So, why didn't I used the part name and dowloaded the model from somewhere else? It is because everytime I visit a site, even though the thing is same, I see in the drawings they are a little different and inconsistent, which is unprofessional and intolerable becuase I don't want to risk the assembly by ordering wrong parts. Even pulley hub thickness varies between sellers.

But the Indian hobby market behaves differently than industrial suppliers: Most sites sell parts. Very few provide CAD. Even fewer provide verified manufacturer datasheets. Many are resellers of unnamed OEM parts.

So I was stuck in between two worlds:

Industrial-grade suppliers  
→ Reliable: OK fine  
→ CAD models: Yes!  
→ Datasheets: Awesome!  
→ Expensive: Not fine  

Hobby-market suppliers  
→ Affordable: Only this matters  
→ Available locally: Important!  
→ No CAD: Why?  
→ Ambiguous tolerances: Very unprofessional  

So, this is what I did: I started from the very foundation, and worked my way up till I complete the Kinematic Base Module (KBM). Instead of abandoning the plan, I tried systematic verification.

1. **4040 Aluminium Extrusion** from Robokits 4040 T-Slot (Astro Industrial grade): I checked slot width (8 mm vs 10 mm variants), core wall thickness, center bore diameter, and outer corner radius. There is only a 2D drawing image provided. No tolerance specifications. No downloadable 3D model. So, I chose [this](https://www.3dprintronics.com/products/t-slot-aluminium-extrusion-4040-8mm?srsltid=AfmBOorlrQFAR1Xrt53eLpePYovKiCMCeYb2kc3UqxQDkFEoahj_P2o4YdA) from 3DPrintronics, instead.

2. **MGN15H Rail & Block** — Candidate: Robu MGN15H Sliding Block. I checked rail height (H dimension), block width (W), mounting hole pitch (C dimension), and mounting hole diameter. Only basic specifications are listed. No full dimensional drawing is available. The official HIWIN datasheet shows precise tolerances and preload classes, but Indian sellers do not specify the actual manufacturer. “MGN15H” is a size class, not a brand guarantee. So, I trusted Robu and decided to use model from JLCMC.

3. **NEMA23 PR57HS51** — Candidate: Robu NEMA23 PR57HS51. Torque is approximately 1.0–1.2 Nm. Body length varies by torque variant. I compared body length, shaft diameter, shaft length, and mounting face standard (47.14 mm square pattern). The mounting pattern is standardized. The body length is not. So, I am also trusting this.

Okay, now this is the BOM for the Foundation Structure, for now:

<img width="2340" height="132" alt="image" src="https://github.com/user-attachments/assets/52d7d490-c39b-4479-955c-b229921b5a04" />

I will continue with this for the next day, and start modelling again.

**Summary of today's session (Day 8):**

1. Received approval to continue development and refine the project further.
2. Finalized important design parameters such as rail dimensions and workspace.
3. Permanently removed ball screws from the system architecture.
4. Investigated CAD model availability for selected commercial components.
5. Began rebuilding the project around verified and practical hardware selections.

**Total time spent: 3h 55m**

---

# Day 9 — 03.05.2026: Modelling Based on New Plan

Today I started modelling PATRA again from scratch based on the components that were finalised for the first stage, yesterday. I wanted to start fresh. I had my parts listed, so I simply went for the 3d models one by one.

1. **[4040 Aluminium Extrusion](https://www.3dprintronics.com/products/t-slot-aluminium-extrusion-4040-8mm?srsltid=AfmBOorlrQFAR1Xrt53eLpePYovKiCMCeYb2kc3UqxQDkFEoahj_P2o4YdA) from 3DPrintonics:** For the model, I went to JLCMC and chose [TXCL-H7-4040E-L1000](https://jlcmc.com/product/s/T01/TXCL/extruded-aluminum-t-slot-40-series(eu)-8mm-slot-width?k=TXCL-H7-4040E-L1000&productModelNumber=TXCL-H7-4040E-L%5B50~6000%2F0.1%5D), and made sure that the exterior of the profiles match, wven thought the interior dosen't.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e7cef8d2-06e1-49ae-8467-1d2626996399" />

2. **[2020 Aluminium Extrusion](https://robu.in/product/easymech-20x20-t-slot-aluminium-extrusion-profile-1000-mm) from Robu:** For the model, I again went to JLCMC and I chose [TXCJ-H7-2020-L1000](https://jlcmc.com/product/s/T01/TXCJ/extruded-aluminum-t-slot-20-series(eu)?k=TXCJ-H7-2020-L1000&productModelNumber=TXCJ-H7-2020-L%5B50~6000%2F0.1%5D) for the model.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/f1a07dde-2669-431b-9970-775c29f5b4a0" />

3. **[Linear Rail](https://robu.in/product/mgn15h-linear-guide-rail-1m-2) from Robu:** I sourced the model from JLCMC. I used [E-BMN15H-2-L1000-ZF-C-E20](https://jlcmc.com/product/s/B03/E-BMN/economical-linear-guide-mini-standard-type-7-9-12-15?k=E-BMN15H-2-L1000-ZF-C-E20&productModelNumber=E-BMN15H-2-L%5B70~1800%2F1%5D-ZF-C-E%5B0~39%2F0.5%5D) for reference.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/6bf120ce-1bd0-4ff0-b6dc-b1268900974d" />

5. **[Linear Guides](https://robu.in/product/sliding-block-for-mgn15h-linear-guide-rail) from Robu:** I sourced the model from JLCMC. I used [E-BMN15H-2-L1000-ZF-C-E20](https://jlcmc.com/product/s/B03/E-BMN/economical-linear-guide-mini-standard-type-7-9-12-15?k=E-BMN15H-2-L1000-ZF-C-E20&productModelNumber=E-BMN15H-2-L%5B70~1800%2F1%5D-ZF-C-E%5B0~39%2F0.5%5D) for reference.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/edb5886a-23ee-43a3-bb78-ea120d2b0e70" />

Then I went back to researching about motors I could potentially use, and I tried to gather estimates of my producable torque from PATRA.

Here is a what I found:

Moving mass per axis	~5 kg
Static torque requirement	~0.49 N·m
Dynamic/stiff torque requirement	~1.5–1.8 N·m
Your old motor running torque	~0.7–0.8 N·m
Recommended motor torque	≥ 1.5–2.0 N·m
Good motor choice	~18.9 kg·cm (~1.85 N·m)
Great motor choice	~30.6 kg·cm (~3.0 N·m)

Some important points tobe noted:

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

I did some research on the MGN15H I am choosing, and after comparing models, I found out that the profile I sourced from JLCMC and the profile avaiable in HIWIN do not match exactly. The dimensions are a little diffferent as well. I went to Robu.in to check the dimensions, but they didn't match exactly.

This meant that I have to choose my 3D model of MGN15H rail from TraceParts HIWIN.

I found [this](https://www.traceparts.com/en/product/hiwin-technologies-corp-mgn15h?Product=90-07042020-029729) from TraceParts, and I downloaded it. I will use it in my model the next day.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/3ec1d41c-ce74-4d99-8577-02b12531358d" />

I then dived into a little foreseeing the future. I know that CNC machinging is really pivotal to give a robotic look to my PATRA, and no kind of 3D printing could match that feeling. But, CNC is very expensive. I exported a random leg of Rowan's tirpteron to use it for an instant quote. I started searching for cheap CNC services in India.

1. **[Igus](https://iglidur-cnc-designer.igus.tools/result/drawing):** The first one I tried was from Igus. I first thoutght that since they have a branch in India, I can expect their machined parts without any customs, cheaply. But I was astonished to see the amount in Pound Sterling. The cost was 3,139.83 GBP. Looking at the amount I realsed beforehand that this is too much. Just as I converted the 3,139.83 GBP to INR, it came literally 4,04,245.26 INR which is completely crazy.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/8c17b34f-da34-4bf3-8174-de8b505bc730" />

2. **[JLCCNC](https://jlccnc.com/cnc-machining-quote):** I have experience from JLCMC. Both of ordering and paying customs, so there was no way I was going to source my parts from JLCMC. But just to see how much it costs, out of curiosity, I uploaded the same model here to see the price. And, as I expected it was a lot cheaper, ye expensive for me. Price was quoted at $54.16.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c11e0e9b-6d01-4784-905c-fd6a0f7b36f5" />

3. **[PCBWay](https://www.pcbway.com/rapid-prototyping/manufacture/?type=1&reffercode=W):** Again, as I expected, the prices were much higher compared to JLCMC. The cheapest possible option with Aluminium 6061 was quoted at $329.46, which is way too much expensive for an arm.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/dbc4f73a-2304-47a2-9749-9d6cf7e5e4e5" />

I then made the hard desicion of choosing only 3D printing for all the parts of my project. I would either print in my future printer, or I would choose MJF or SLA printing from local sources if possible.

**Summary of today's session (Day 10):**

1. Investigated dimensional discrepancies among linear rail suppliers.
2. Adopted verified HIWIN references to improve modelling accuracy.
3. Continued evaluating fabrication methods for custom robot parts.
4. Compared manufacturing services and their pricing structures.
5. Improved confidence in future fabrication planning and component selection.

**Total time spent: 3h 50m**

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

Previously the bare bones tensioning system involved the following:

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

I started by downloading the [Pulley CBYL-AH1-5GT150-20-A-N-d12 (Z)](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-20-A-N-d12&productModelNumber=CBYL-AH1-5GT150-20-A-N-d12) and [Idler CBYL-AH1-5GT150-18-A-H-d16 (Z)](https://jlcmc.com/product/s/C03/CBYL/gt5-htd-timing-belt-pulley?k=CBYL-AH1-5GT150-18-A-H-d16&productModelNumber=CBYL-AH1-5GT150-18-A-H-d16) from JLCMC, which were the components paired with the [Belt E-GBN26005GT-150 (Z)
](https://in.misumi-ec.com/vona2/detail/110411276379/?HissuCode=E-GBN26005GT-150) that I had finalized for the Z axis tensioning system. Then I updated the assembly by replacing the comonents.

Since I had replaced the pulleys and idlers, it meant that I had to make sure that the belt fits perfectly with the new components, instead of adapting. So, I visited [this](https://in.misumi-ec.com/vona2/detail/110411276379/) datasheet of GT5 belt from MISUMI, and had a brief look on the dimensions, so that I can match mine existing one with it. I had a look at the 3D preview, but it honestly made no conclusion, so I downloaded the STEP file.

<img width="447" height="163" alt="image" src="https://github.com/user-attachments/assets/7c7fc1eb-e7e2-476b-a30e-eed67d72015a" />

I imported the model in my workspace, positioned it just above that one belt lock which i imported from GrabCAD yesterday. To be specific, it is this one: [GT5 belt lock](https://grabcad.com/library/gt5-belt-lock-1). My eyes kept telling me since yesterday that it was no way GT5. I confirmed it now. Maybe I did make a mistake while choosing the file to download. Anyways, it seemed like I could make my own timing belt. I proceeded to take measurements of the imported model and confirmed if the dimensions actually match with the datasheet.

Once I confirmed that each tooth was absolutely perfect, I used the pattern tool to duplicate a single tooth accross the whole belt. I kept the spacing, or pitch at 5mm. Of course, the last one was not perfectly distanced from the first tooth, but it didn't matter.

The reason I am doing this is becuase of the following reasons:

* I wanted to carve out my own timing belt lock, instead of relying on other models from internet.
* I wanted to see how the whole belt would look with all the tooth.
* I wanted to see how well the teeth would line up with the idler and pulley.

I then shifted focus away from the belt, pulleys and idlers of the tensioning system, and instead focused on the pulley case, idler case and the extrusion. So I fixed the length of the 2020 aluminium extrusion to prevent operlapping and the raddii of the point of intersection between the NEMA23 and the pulley and idler case.

Then it was time to fix the X and Y belt locks, because they were still HTD 5M compatible, not GT5 compatible. For that, here is the workflow I adopted:

1. I used extrusion to cut down the belt clamp to half of it's width, making sure I can directly look into the teeth grooves.
2. I positioned the 8 teeth (with 5 mm pitch) properly by moving it 0.1 mm, since it was off by that margin.
3. I created a sketch for the profiles that were excess in the cross-section and them extruded them in and joined.
4. I mirrored the corrected part and then combined them.

I then fixed the celling of the part above to make sure it thghtly clamps the belt in place. With this, the clamping system for both the X and Y tensioning systems was fixed. Now it was time for the Z axis tensioning system that will sit in the middle of the two Z linear blocks.

For that, I duplicated the clamp then positioned it to perfectly align with the belt path of the Z axis tensioning system. But, during that, I found some weird problems with the faces of the belt clamp. So, I had to fix it by making it a solid body extrusions, then using the 8 teeth to cut out the shape of the GT5 tooth. It produced a cleaner and more accurate customized clamping belt that it more reliable. Then I replaced the old messy GT5 clamp with the new clamp, for both the X and Y axis, while keeping the part with the mounting screw hubs almost untouched.

Next part was about to model the part that actually connects the floating belt clamp to the two Z linear blocks. This step was not very strict in terms of design, so I made it look as good as possible. For that I added little fins on either sides of the linear block ends. I copied the design to the X and Y linear blocks as well.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/18da3741-9f52-4d04-862a-2d8d56af0993" />

Since the motor of the Z axis was running two linear blocks, I decided to use [NEMA23 PR57HS112-4204-01 31kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs112-4204-01-31kg-cm-stepper-motor-round-type-shaft/) instead of [NEMA23 PR57HS76-2804-05 18.9kg-cm Stepper Motor](https://robu.in/product/nema23-pr57hs76-2804-05-18-9kg-cm-stepper-motor-d-type-shaft/).

With this much progress done today on the parts, it was now time to update the BOM. And so I did.

<img width="2559" height="297" alt="image" src="https://github.com/user-attachments/assets/718dc784-ccae-405c-a248-e06c685a839d" />

But when I paused my lapse, and then came back, I forgot to resume it. I had made more changes to the BOM and fixed some overlapping compoents, troublesome downstream features and timeline errors. The First stage is almost complete after all this.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/4b605071-5c56-4343-b12e-89baed85f349" />

Here's the lapse of today's session: [PATRA-LPS-1-D21](https://lapse.hackclub.com/timelapse/LMIzn1To8zm3)

**Total time spent: 5h 55m**

---

# Day 22 — 23.05.2026: TriTeron Robot Module (TRM) Progress — Part 1

With the Tensioning System mostly done, it was time time to start working on the triteron. As discussed earlier, I will be following Rudmin's design combined with Rowan's. For the Kinematic Base Module (KBM) I followed Rudmin's design, and for the TriTeron I will be following Rowan's design with slight changes in the leg position.

Before I dived into the tripteron part, I thought of first improving certain design features of the Linear Block, using chamfers and drafts. Once it seemed like it looked better than before, it came to me that if I am adding something on the top of the Linear Block Unifier, I had to use flat head screws.

For that, I went to OnlyScrews and started searching for the right screw. I found the perfect screw type needed. For the adjustmesnts, I added chamfers to house the screw heads.

With the thought of starting easy, I chose to work on the front two legs, which are supposd to be the Z axis legs. They will be connected via Z Axis Mount. Thus, I started modelling the Z axis mount, which was supposed to have an angle of 45 degress at the face where the front two Z axis legs were supposed to be attached. For this step I looked at the Rowan's model and Rudmin's video several times.

Once the Z axis mount was roughly done, I shifted focus to the X and Y axis mounts. I was confused with the angles of the joints, so, I relied mostly on the exact angles provided in the model of Rowan's tripteron. For getting the angles right, I even imported the Bearing Mount of Rowan's design in my workspace. But they made almost no sense to me. So I followed Fusion's measurement tool's data about the angles, and I made a circular body that I could use in the future for joining the legs.

Next I thought of modelling the legs, for which I will be following Rowan's design, not Rudmin's. So, first I made holes in the Z axis mount that was supposed to mount the lower part of the two front Z axis legs.

Then, I made a new design, where I started to model the leg, by drawing a sketch. Here's how I did it:

1. I made a center-tocenter slot of 150 mm and 30 mm diameter.
2. Then I made circles of 15 mm and 25 mm on either center points of the slot.
3. I drew a line 7.5 mm away from the slot's central line, and made it connect to the circles.
4. I made some adjustments to manage to add fillets to the point of intersection between the line and the circles.

After the sketch was done, here's how it looked:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/478bc880-ab3f-469c-811a-9e9f799a4f07" />

Next step was the extrude the sketch to achieve the shape needed. Here's how I did it:

1. I first extruded the full sketch, creating a solid body.
2. I made the 15 mm holes using extrusion cut.
3. I made the 25 mm diameter 7.5 mm deep hubs for the bearing for the bottom part.
4. I made the 25 mm diameter 7.5 mm deep hubs for the bearing for the top part.

After this step, here's how it looked:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/caf97c09-089a-4fc3-a060-ef940fc1c394" />

Next step was to create a sketch along the outer flat face of the leg, to add design:

1. I drew a shape where one circle of the extruded slot had only half of its height, and added fillets.
2. I used offsets to achieve a shape similar to the face itself.
3. I extended the corners to form trianglular points.
4. I added fillets in the corners, to make it look better.

Here's how the sketch after completion:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/cd156669-c61c-47e5-819d-57a95f0afc3b" />

After I made the extrusion only for the design part, here's how it looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/5868b29e-e968-491b-8cf3-084f0069687e" />

Next I needed to set up a face that was located along the length of the slot. For this, I copied the component, named it "midref" and extruded in a specific part from the last sketch, achieving this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/eeef17e7-e2cd-49db-b783-c39f10407753" />

On that face of the midref, I made this sketch:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/65ad18c3-2c2f-4b7d-886c-6947e29b667a" />

Using the revolve tool, I revolved the sketch and achieved this shape which I wanted. Then I made a little extrusion to make the pace above the bearing hub flat, which would be in contact with other legs. And I also adjusted the bearing hubs' positions using nothing but extrusions.

Here's what I achieved:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c27b5ead-c0aa-4bfb-b9b9-2533e48c4258" />

The leg was complete. It was then time to integrate that into the assembly. So, I imported two of them and used revolute joints to place them exaclty over the hubs which I made in the Z axis mount. I will later mirror them after one side it finalized. That was all for today. Here's how it looked:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2c66b2a1-0610-49ad-af57-415c9bb4c596" />

Here are the lapses of today's session: [PATRA-LPS-2-D22-1](https://lapse.hackclub.com/timelapse/DfNLfUEVeITT) and [PATRA-LPS-2-D22-2](https://lapse.hackclub.com/timelapse/8V5IIaFo7r2J) (the third lapse showed error and was deleted)

**Total time spent: 3h 50m**

---

# Day 23 — 24.05.2026: TriTeron Robot Module (TRM) Progress — Part 2

I picked up exatcly where I left off yesterday. As the leg was complete, and imported into the assembly, I can continue with positioning them properly.

There are going to be 4 legs in total, each with two connected legs.

* There will be one X axis leg consisting one upper and lower leg
* There will be one Y axis leg consisting one upper and lower leg
* There will be two Z axis legs consisting one upper and lower leg, each

But due to some errors, I went back in the timeline and then restarted from the part where I had just imported the leg into the assembly. After that, I created new components and duplicated the Leg 4 times in one way and 4 more times mirrored. But due to some chaos, I deleted them and instead imported the design as bodies, not components, and copied them like that.

I started with the assembly of front two legs of the Z axis, and used joints to position them into correct place. And for the angles, I follwed the exact angles of Rowan's design provided in the design. For once it felt like I had to learn 3d kinematics algebra. I was actually quite excited for this, but I had a better idea, for the time being.

The plan was to import Rowan's design's legs into the model only to get the angles and align components in place, not to actually use the model.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/be227750-5b7d-4c37-8e2f-d9bb3357811c" />

Once I adjusted the positions and angles, I made sure that the legs made by me follow the poition of Rowan's designed legs as closely as possible.

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

I was done with the positioning of the the front two Z axis legs. Now was the time to fix the position of the Z and Y axis legs.

By fixing, this is what I mean:

* The lower end of the X and Y axis legs do not not overlap or touch the ninear block.
* The elbow of the X and Y legs do not extend much farther out or much in.
* The elbow height matches the elbow height of the front legs of Z axis.
* The back legs are positioned similar to [Rudmin's design](https://www.youtube.com/watch?v=6EtXycVGJg4).

Using rotations and movements, I positioned the X and Y legs properly.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/33c1c2a2-e56b-4d25-aaaf-d6e44f021965" />

Then it was the time to work on the X and Y axis mounts, which was quite tricky due to the angles, but with some extrusions I was able to come up with this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/88e2584d-1f0c-46fe-834a-50ec65aee4c2" />

With that done, I started writing past incomplete journals of older days, and added summary for journals of days #1 to #10, simply because I was tired.

Here's the lapse of today's session: [Well, well, it failed]

**Total time spent: 1h 30m**

---

# Day 25 — 27.05.2026: TriTeron Robot Module (TRM) Progress — Part 4

Today's session achieved almost nothing except the sketch I made at last. But I am stil writing this all up for the sake of appreciating failures.

I was not starting from scratch this time, because I had this body which I don't know what to call or even what exactly to do with. This is what I am talking about:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0ad9b52f-ca36-4bef-aab7-7935601e8f79" />

I wanted to achieve a carved out geometry that could enclose the losai of the legs. I used the lower leg geometry to cut out a part of the shape and I wanted to make something from it, which I wasn't quite sure of.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ba754a84-7fec-481f-aee6-735917bc60dc" />

But this design was not much promising. Then, I wanted to have a body with chamfered vertex that would be of same angle as the X and Y lower legs' last joint's angle. For that approach, I deleted that part, and I achieved this.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/80a13c4f-c5f1-4fb9-a050-361de76cbd6d" />

But also this was seemingly strange and structurally weak. 

I continued working on the X axis leg mount, but I was not coming up with any ideas about how to connect the legs to the linear blocks. That's when I had a look into Rudmin's design and then I found out exactly what to do.

I made this sketch that will have a extruded out diagonal body that will have hole to connect the lower part of the back legs.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/25f28af6-ed21-44ad-ba67-ad4a61c93ca2" />

The sketch was for creating a body that intercets with the extended mid-point of the lower leg when viewed from top and the linear block's vertical center of mass when viewed from top as well. There was an angle of 56.105 between the linear path and the angle of the lower leg when projected on the floor.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/55de0995-3577-456e-812f-851f899dd5cd" />

I had some problems with positioning the sketch correctly. At times it was 1.5 mm off and the sketch between the lower leg and the linear block didn't line up. But while fixing that my time was over.

Here are the lapses of today's session: [PATRA-LPS-4-D25-1](https://lapse.hackclub.com/timelapse/XQaZ_Rl9L285) and [PATRA-LPS-4-D25-2](https://lapse.hackclub.com/timelapse/zi7MiJX0X9Cf)

**Total time spent: 3h 20m**

---

# Day 26 — 28.05.2026: TriTeron Robot Module (TRM) Progress — Part 5

Last day the sketches didn't line up. Today after fixing the offset, but there were problems with the sketch itself due to the timeline features. So, redrew the setch again, but after fixing the offset of 1.5 mm.

I then confirmed if the sketch was correct and if the points are intersecting correctly. The angles lined up and it seemed fine. Then I followed these steps to achieve the geometry which not only looked better but also was structurally more sturdy and ideal.

This is the sketch:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/2000a1ac-f4ae-4ad1-a120-c3650d24d216" />

I first extruded out a body.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/de70120c-563d-4a19-b3e6-83e6af7c3f87" />

Then I made a hole into it using extrusion from the lower leg profile.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c3b6d0aa-948c-47ef-bd13-931dd4d450ab" />

I added chamfer to make it look better.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c4f8c16a-9a18-4f8e-86f2-ad8038503620" />

I also mirrored it and gave it appearence.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/99717ec1-d8fb-4012-a1c0-712dee0e32f7" />

Then it was time for the Tool Head to be brought into existence. Immediately I did this:

* Started with a simple sube of 100 mm by 100 mm by 100 mm.
* I moved it up into correct position.

But wait, I had forgotten some things:

1. Arrange the components and establish correct parent-chile component relationships in the Browser. So I did that first.
2. Convert the Legs, which were bodies, to components.
3. Apply revolute joints to every point in the leg.

The first two didn't take much time, but the third one took a lot of time to achieve. This was not my first time adding revolute joints to an already-established triteron (even though the tool head was not completed), this took some more time than I had expected.

But yeah, I was indeed able to achieve normal movement in the triteron.

[lapse](https://lapse.hackclub.com/timelapse/oC5sY39XrQ18)

**Total time spent: 1h 45m**

---

# Day 27 — 30.05.2026: TriTeron Robot Module (TRM) Progress — Part 6

With that joints done on the previous day, I continued with modelling the Tool Head, which I was most concerned, worried and confused for becuase I assemed that it would be very complex to model the tool head, since the very begging. But I logically broke down the workflow into these simple steps in the real time (not pre-planned) and achieved the correct geometry.

Here's what I did:

1. I moved the leg a little towards the front (towards the direction of the Z axis legs)

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/137222c6-7c54-441a-855f-1a3887d16f1f" />

2. Extruded the back of the cuboid 25 mm, to acheieve a longer body.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/86958251-43a4-488d-b2ac-5f0097d2b904" />

3. Movied it again a little towards the front.

   <img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/687e3745-9817-4db2-ac76-21e5ab78d09d" />

4. Using Combine Cut tool, made the upper X, Y and Z legs cut the tool head.

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

Throughout the workflow, in the first steps, I was working by seeing Rowan's design, but on the later stage, it seemed like I found the pathfor the correct set of stps to achieve the design needed.

There is some difference between this design and the design of Rudmin and Rowan. To be specific, this is a perfect mix of both.

Let me explain Rudmin's Tool Head design:

* Rudmin's design features all the legs in the same level.
* Rudmin's design is simpler, more straightforward and even has a hole in between.

Let me explain Rowan's Tool Head design:

* Rowan's design features the X and Y axis legs to be raised above the front Z axis legs.
* Rowan's design has lots of chamfers, fillets, extrusions, and a more detailed design.

Now, let me explain my Tool Head design:

* Just like Rudmin's design, all the legs are present at a similar level, in my Tool Head Design.
* Just like Rowan's design, the Tool Head is designed in a more complex manner, with fillets, chamfers and extrusions.

With that done, I was testing the movement of the tripteron, or more appropriately, playing with my digitally made triteron and also checking if angles are okay, movements make sense, and if it is flexible enough to bend in different angles.

Here's the lapse of today's session: [PATRA-LPS-6-D27](https://lapse.hackclub.com/timelapse/srgx05NYIPdJ)

**Total time spent: 1h 00m**

---

# Day 28 — 31.05.2026: TriTeron Robot Module (TRM) Progress — Part 7

In today's short session, I added one more design elements to the Tool Head.

Firstly, I made fillets in 4 sharp edges under the Tool Head.

So, it went from this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/1bcce337-590e-4964-99fc-9839c2e9fd54" />

To this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/cd5f307a-f0af-4e93-9159-7e22c1a98aa2" />

Secondly, I made extrusions on both left and right of the Tool Head by extruding in a sketch on the sides of the Tool Head, and adding fillets. This made sure it uses less filament, and of course, looks better.

So, it went from this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0baf591d-b81f-4fa3-bc55-b2e9f4af3637" />

To this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/af27709b-435a-452f-80b7-07bc542075e5" />

But then, I wondered that Rudmin's design of clevis joint for legs will be better for the system. For the two front legs, I noticed that the angle of rotation is not much high, and the legs easily overlap if the angle goes over 30 degrees. Thus, it seemed like I seemed like I needed to use clevis joint.

So, I started modelling a fork of the clevis joint for leg. Starting from this mirrord architecture of the pre-existing leg.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/eb47c686-c2e4-443b-8419-14740291def6" />

I turned it into this:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7bda38c3-2899-46e4-8a9a-075073129543" />

But it is not yet completed. I will complete this the next day.

At last, this is how the triteron looks:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/336a41aa-2f9b-46e7-8f2a-d78c0f5852be" />

Here's the lapse of today's session: [PATRA-LPS-7-D28](https://lapse.hackclub.com/timelapse/AqGtmyhMh9QV)

**Total time spent: 0h 20m**

---

# Day 29 — 01.06.2026: TriTeron Robot Module (TRM) Progress — Part 8

Today I continued modelling the fork of the clevis joint from the day before, and also modeled the tang of the clevis joint for the leg. But I also dropped the whole idea for using the clevis joint for the front legs.

Using split body, extrusions and facial offsets, I was able to achieve a mechanically sane fork.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/203c00ec-21d5-45c0-9e44-541810209755" />

Then it was time to model the tang.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/7143e603-d600-4d8d-9c20-0eed25de1eb4" />

But when I imported them into the workspace and tested the movements, it performed even worse. There were overlapping sections at even lower angles.

Then I got the perfect idea.


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

But then I found this [MSB8-30](https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30) screw that seemed perfect for the assembly, since it had no narrow points and a decent thread length. I briefly went through the data sheet, to give it approval.

<img width="900" height="1271" alt="image" src="https://github.com/user-attachments/assets/4344263f-def7-4784-a7aa-cfeb2aa381a7" />

But there was one problem. The the length of the smooth shoulder was exactly 30 mm, which mean that the washer to waher max distance was also supposed to be 30 mm, for a perfect fit. The washer is 1.5 mm thick and the 608 bearing is 7 mm thick. But currently, this was 1.5 + 7 + x + 7 + 1.5 = 32 mm, where X is the TriTrron leg's gap between the bearings, which was 15 mm. This meant that I had to reduce the X from both sides by 1 mm, to make the total 30 mm.

Thus, I made the adjustments to all the 24 bearing hubs in the legs, using extrusions and facial offsets. Then I deleted the old rigid joints of the bearings and reassembled them correctly.

This made sure that there is 27 mm of gap between the washers, and since the washers were 1.5 mm thick, the distance between the extreme faces of the wo washers is 30 mm.

This is how it looks now.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/0470ebae-430b-425c-98ed-8ca5e5f1259c" />

The problem was fixed, and the screw was supposed to be a perfect fit.

I added rigid joint for the first washer (after struggling to delete the pre-existing joint), and then for the second, and then the nut.

Yes, it was a perfect fit, and the fastening system was completed. But before I could proceed, time was over for today's session.

Here's the lapse of today's session: [PATRA-LPS-11-D32](https://lapse.hackclub.com/timelapse/0scjCOx6vKE7)

**Total time spent: 3h 30m**

---

# Day 33 — 05.06.2026: TriTeron Robot Module (TRM) Progress — Part 12

I proceeded exactly from where I left off yesterday. I started today's session by solving that very bottleneck that was lurking within the whole triteron system's foundation, which was the nut fastening the whole system itself. The fastener was simply upside down, in simple terms.

So, I flipped it, cauing chaos in the whole workspace, I don't know why. The slign simply affects each of the component's copy and changes their orientation upon any chang made to one of the component. In this case, it was the nut.

To start fresh, I made some adjustments back in the timeline, causing the hole to delete itself. Then I did the following:

* Used rigid joint to properly place the nut into position.
* Used cut tool to re-establish the hole.
* Used sketch to extrude out the right geometry to fix things.

I then proceeded to repeat the same assembly sequence involving the [MSB8-30 screw](https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30), M8 washers, and of course the [EMLC-S1-N-M8 nut](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M8&productModelNumber=EMLC-S1-N-M8), just like yesterday.

But then I noticed a terrible mechanical flaw. The threaded part of the [EMLC-S1-N-M8 nut](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M8&productModelNumber=EMLC-S1-N-M8) was 6 mm in diameter, which meant that it was supposed to be an M6 nut. I was using M8.

So, I went to JLCMC, corrected my confuiguration and downloaded this [EMLC-S1-N-M6 nut](https://jlcmc.com/product/s/E04/EMLC/anti-loosening-nut?k=EMLC-S1-N-M6&productModelNumber=EMLC-S1-N-M6), and imported it in my design.

I then adjusted the geometry of the Z Axis mount to perfectly house the M6 nut. I also made sure that there is no friction among the rotating parts. I then split the body of the mount and then mirrored the geometry.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/837e92ed-5d3f-47dd-b31c-2ef821414f03" />

Since I had worked quite a lot on my design, there was a high chance that I was potentially making a mistake. So, I consulted with Gemini and showed it my assembly and it pointed out the issues, and I fixed them, and was completely rest assured of my design's sanity.

I can now copy this new logic to the other mounted joints (including the tool head) and complete the triteron just except for the double joints.

Here's the lapse of today's session: [PATRA-LPS-12-D33](https://lapse.hackclub.com/timelapse/1AzmvcisTlWN)

**Total time spent: 1h 50m**

---

# Day 34 — 06.06.2026: TriTeron Robot Module (TRM) Progress — Part 13

Before I could copy the fastening logic from yesterday, I had to name the fastening components logically so that everythings makes sense, and is easy to navigate.

For that, I decided to make two different fastening sets:

* Fastening Set S: Here "S" means single, and they are bascially the joint connected with the mount and the tool head.
* Fastening Set D: Here "D" means double, and they are basically the elbow joints, that are the joints between the legs themselves.

I belived that this was okay for the time being, and I thought of coming up with a better name later on.

Then I proceeded to follow the exact naming sequence I had used for the Bearings, exactly where the Bearings existed. Here is the logic:

* "Fastener Set" is the core name, for all the fastenser sets that include either, "Fastener Set S" or "Fastener Set D".
* Then it is followed by either "X", "Y", or "Z" depending on the axis.
* If it is "X" then, it is followed by either "U", for upper, "L" for lower, "UL" if it was the elbow joint that falls in between.
* If it is "Y" then, it is followed by either "U", for upper, "L" for lower, "UL" if it was the elbow joint that falls in between.
* If it is "Z" then, it is followed by either "A" or "B", depnding on the rail their loest joints sit on. Then it is followed by either "U", for upper, "L" for lower, "UL" if it was the elbow joint that falls in between.
* If the joint is single and I use "U", OR "L" as suffix, then I establish Fastener Set S as the child component.
* If the joint is double and I use "UL" as suffix, then I establish Fastener Set D as the child component.

There are the following numbers of both type of joints:

* There are 8 single joints.
* There are 4 double joints.

Note that this session only involves the single joints.

Next part was about completing the **Fastener Set S**. For that, I edited the [MSB8-30 screw](https://in.misumi-ec.com/vona2/detail/110100143940?HissuCode=MSB8-30), by adding thread and nice appearence, and redifned the joints as an independent system. I made sure that the washer placement, nut placement and the both placement are interdependent in Fusion assembly and are unified as a Rigid Group.

Then I duplicated the **Fastener Set S** total 8 times using rectangular pattern, and placed them inside the correct component one by one. A clean logic was then established.

Here's how the X axis fasteners were named:

<img width="357" height="510" alt="image" src="https://github.com/user-attachments/assets/d3dafbea-1688-4e54-94d3-1fda8e150912" />

Here's how the Y axis fasteners were named:

<img width="357" height="510" alt="image" src="https://github.com/user-attachments/assets/d02e9428-40ae-457e-83b9-c2e561bb8d59" />

Here's how the Z axis fasteners were named:

<img width="357" height="510" alt="image" src="https://github.com/user-attachments/assets/fec31666-7f32-4a52-8084-133a2707186d" />

Followed by this, it was the time to establish the cuts for the nuts to go in for the other mounts and the tool head. But I noticed asymmetry in placement of the Tool Head, and saw that it was overlapping with one of the legs. I want back in the timeline and fixed the position.

But then again, the cut in the Z Axis Mount disappeared. This was probably my fourth or fifth time modelling this part. But since I knew what to do, I got over with it quickly, mirrored the logic and moved to the Tool Head.

I extruded out a body that followed the exact geometry of the hub for the nut and the screw's thread's end part, and named it "NUTCRAKER" because I didn't want it to disappear into the other Bodies, if I just kept the name default; and also because it is supposed to crack a hole for the nuts to go in, so I think this makes sense.

I aligned NUTCRACKER in the two of the hubs of the Tool Head, and used the Combine Cut tool to carve out the geometry.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/03eb6746-b47f-4576-9a36-a07aae84c1a4" />

Then I split the body and then mirrored it to make the geometry symmetrical.

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/e2122bb5-3d25-4f25-b764-fb98bf3840ba" />

Then it was the time to work on the X and Y Axis Mounts, which have been floating since their very existence. I used NUTCRAKER this time to align with the last nut and create geometry, not cut. I first extruded a circuar profile from inside the mounts. Then I created a sketch where I made a hexagon and added fillets, then I extruded it inwards and made it a seperate part which I can assemble seperately. I used NUTCRACKER to crack a hole just like the other ones. I mirrored the components, and had them placed correctly. I named the extrusions, "Extensions".

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/45fec21d-1e35-44f9-8ed6-1d156d20a948" />

Next I moved to also work on the double joints, but I wondered how. I did some research and found that I had to use mechanical shims between the rtating components. I did not proceed as the time for today's session was over already.

But, anyways, here's how the tripteron looks like now:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/c1db48ba-c4e4-4622-8c12-8fb6650436ea" />

Here's the lapse of today's session: [PATRA-LPS-13-D34](https://lapse.hackclub.com/timelapse/nWiG3ZvdcpSs)

**Total time spent: 3h 20m**

---

# Day 35 — 07.06.2026: TriTeron Robot Module (TRM) Progress — Part 14

I started by fixing all the minor problems from yesterday, which I had ignored knowingly or unknowingly.

So, what waere the problems?

* The internal diameter of NUTCRACKER surrounding the thread was randomized at 3.84 mm radius.
* The X and Y upper leg was rubbing against the tool head, with zero clearence. I had to make it 1 mm.
* The distance between the NUTCRACKER hole's deepest point and the surface was not seen consistent.

Here's what I did to fix them:

* Went back in timeline to make the radius from 3.84 mm to 3.5 mm.
* I took out the extrusion from the axis mount.
* Then I named it FRICTIONKILLER, you know why.
* Then I made face offsets in tool head holes.
* Mirrored the parts, and used Combine tool.
* Took measurements to see if everything is alright.

Here's what I ended up with:

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/ebd91876-da58-4df6-a788-8de189a43f8f" />

<img width="1366" height="733" alt="image" src="https://github.com/user-attachments/assets/162c38a3-4bda-4a03-9bec-28a4b0007b97" />

Here's the lapse of today's session: [PATRA-LPS-14-D35](https://lapse.hackclub.com/timelapse/kdLlRkzxfTa4)

**Total time spent: 3h 25m**

---

# Day 36 — 08.06.2026: TriTeron Robot Module (TRM) Progress — Part 15

I started by fixing some structural and mechanical errors that I noticed with the depth of NUTCRACKER.

Here's the lapse of today's session: [PATRA-LPS-15-D36](https://lapse.hackclub.com/timelapse/1kYZRIteUWKL)

**Total time spent: 0h 45m**

---

# Day 37 — 16.06.2026: Research on the Robotic Arm

Here are the lapses of today's session: [PATRA-LPS-16-D37-1](https://lapse.hackclub.com/timelapse/zAi2jDNiKqpI) and [PATRA-LPS-16-D37-2](https://lapse.hackclub.com/timelapse/Pgd6fTYl6KDr)

**Total time spent: 3h 00m**

---

# Day 38 — 17.06.2026: Writing Past Missed Journals

Journaled the days #21 and #22 (partly).

Day #21

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b225f8c6-459e-4f4f-8119-5c0102d72b99" />

Day #22

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/893e5a43-5e4a-4e2a-a2cb-27a4de5a7599" />

Here's the lapse of today's session: [PATRA-LPS-17-D38](https://lapse.hackclub.com/timelapse/6Sx4q91ksQql)

**Total time spent: 3h 00m**

---

# Day 39 — 18.06.2026: Writing Past Missed Journals

Journaled the days #22 (full), #23, #24, #25 (partly) and #26 (partly).

Day #22

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6cde43d5-46a1-423a-b3e4-3a570bd38a49" />

Day #23

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/da957ffe-f0e9-4b27-bb77-de02ad8ddcc6" />

Day #24

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5cab2b1c-b6e3-4cd2-b64d-f16a70fe80ab" />

Day #25

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b8af7074-8278-4a82-9223-4ac7f6d5f827" />

Day #26

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c04849e2-8456-40a7-afae-205e38184f2c" />

Here are the lapses of today's session: [PATRA-LPS-19-D39-1](https://lapse.hackclub.com/timelapse/UA4UIbZiE68q), [PATRA-LPS-19-D39-2](https://lapse.hackclub.com/timelapse/aaIH03558pYh) and [PATRA-LPS-19-D39-3]()

**Total time spent: 3h 45m**

---

# Day 40 — 20.06.2026: Writing Past Missed Journals

25 26 27 28 29

Here's the lapse of today's session: [PATRA-LPS-20-40](https://lapse.hackclub.com/timelapse/s45U_LOytKdj)

**Total time spent: 3h 15m**

---
