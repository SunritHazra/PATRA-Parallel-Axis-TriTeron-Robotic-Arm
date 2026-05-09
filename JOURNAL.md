---

**Title:** PATRA (Parallel Axis TriTeron Robotic Arm)  
**Author:** Sunrit Hazra  
**Description:** A Hybrid robot architecture of a kinematically linear 3 DOF parallel axis triteron system and a 6 DOF serial robotic arm.  
**Created on:** 2026-05-02  

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

* [This](https://www.youtube.com/watch?v=io4S9amExNM) video by Not An Engineer introduces the carriage system. I watched this multiple times specifically to understand how the X and Y axes are driven independently on the carraige.

* [This](https://www.youtube.com/watch?v=3fbmguBgVPA) pushed me toward adding a robotic arm, and gave me a ough idea of what style robotic arm I could add.

* [This](https://www.youtube.com/watch?v=MeRaYVntxMk) is a solid breakdown of the differences between serial and parallel systems. PATRA essentially combines both, which is why understanding this distinction matters.

To get started, I did focused research on the following (only this time is counted):

* **Kinematics:** Beyond just the general definition, I read articles and watched detailed videos specifically on parallel axis kinematics and kinematically linear systems. I also explicitly read [this](https://en.wikipedia.org/wiki/Kinematics) Wikipedia page, and watched [this](https://www.youtube.com/watch?v=3fbmguBgVPA).

* **Robotic Arms:** I did a deep dive into 5 DOF and 6 DOF robotic arms, studying their structure, joint arrangements, and torque requirements. I also carefully studied the Meca500 robotic arm as a size and precision reference.

* **Linear Belts:** Although I was already familiar with them, I studied motor selection, torque transmission, belt pitch types, and tensioning systems in more detail.

* **Ball Screws:** This was a completely new concept for me. I learned that ball screws offer higher precision and better load handling compared to belts, but at the cost of speed and higher complexity.

* **Aluminium Extrusions:** I knew nothing beyond 2020 and 4040 aluminium extrusion. So, for the sake of this project, I made a deep dive into JLCMC's Aluminium Extrusion Profiles, and I read their [datasheets](https://drive.google.com/file/d/1X2043j8HutSmY2QTKigUobWLhu9sI9k2/view?usp=sharing).

* **Zaber LC40:** Rudmin used [LC40 family](https://www.zaber.com/products/families/LC40) for the TriTeron, which is configurable, belt drive, t-slot profile linear stages. Prices were mostly in the $2000–$3000 range, which is consistent with industrial-grade configurable stages.

Things I Learned:

* How ball screws work internally (recirculating ball mechanism and lead mechanics)
* Differences between NEMA motor sizes and torque ratings
* Trade-offs between belt drives and screw drives
* The structure of linear actuators
* The mechanical difference between serial and parallel robotic systems
* Why rigidity and repeatability matter more than just "cool movement"
* How can I make my robotic arm modular
* A little about the LC40 family

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

**Total time spent: 7h 32m**

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

**Total time spent: 3h 55m**

---

# Day 8 — 01.05.2026: The Research for Sanity

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

**Total time spent: 4h 55m**

---

# Day 9 — 02.05.2026: The Post-Pitch-Approval Research

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

So, this is what I did: I started from the very foundation, and worked my way up till I complete the First Stage. Instead of abandoning the plan, I tried systematic verification.

1. **4040 Aluminium Extrusion** from Robokits 4040 T-Slot (Astro Industrial grade): I checked slot width (8 mm vs 10 mm variants), core wall thickness, center bore diameter, and outer corner radius. There is only a 2D drawing image provided. No tolerance specifications. No downloadable 3D model. So, I chose [this](https://www.3dprintronics.com/products/t-slot-aluminium-extrusion-4040-8mm?srsltid=AfmBOorlrQFAR1Xrt53eLpePYovKiCMCeYb2kc3UqxQDkFEoahj_P2o4YdA) from 3DPrintronics, instead.

2. **MGN15H Rail & Block** — Candidate: Robu MGN15H Sliding Block. I checked rail height (H dimension), block width (W), mounting hole pitch (C dimension), and mounting hole diameter. Only basic specifications are listed. No full dimensional drawing is available. The official HIWIN datasheet shows precise tolerances and preload classes, but Indian sellers do not specify the actual manufacturer. “MGN15H” is a size class, not a brand guarantee. So, I trusted Robu and decided to use model from JLCMC.

3. **NEMA23 PR57HS51** — Candidate: Robu NEMA23 PR57HS51. Torque is approximately 1.0–1.2 Nm. Body length varies by torque variant. I compared body length, shaft diameter, shaft length, and mounting face standard (47.14 mm square pattern). The mounting pattern is standardized. The body length is not. So, I am also trusting this.

Okay, now this is the BOM for the Foundation Structure, for now:

<img width="2340" height="132" alt="image" src="https://github.com/user-attachments/assets/52d7d490-c39b-4479-955c-b229921b5a04" />

I will continue with this for the next day, and start modelling again.

Total time spent: 3h 55m

**Total time spent: 3h 45m**

---

# Day 10 — 03.05.2026: Modelling Based on New Plan

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

**Total time spent: 3h 30m**

---

# Day 12 — 04.05.2026: Research on Linear Rail CNC Estimates

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

**Total time spent: 3h 50m**

---

# Day 13 — 08.05.2026: First Stage Progress — Part 1

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

# Day 13 — 09.05.2026: First Stage Progress — Part 2



**Total time spent: 3h 30m**

---
