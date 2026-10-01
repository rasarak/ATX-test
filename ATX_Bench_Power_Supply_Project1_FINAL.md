# Project 1 – ATX Bench Power Supply

**Course:** Electronics Circuits Laboratory (091013107)  
**Project:** Project 1 – ATX Bench Power Supply  
**Team:** Thepnimit Onchaiya, Korn Rasarak  
**Revision:** Detailed final documentation package  
**Final delivery:** Monday 28 September, 13:00–16:00

---

## 1. Project Summary

The project converts an instructor-approved conventional PC ATX power supply into a bench power source by adding external low-voltage output distribution, protection, control, indication, and an external enclosure.

The project brief defines the source PSU as the original ATX supply selected by the team and requires the metal source PSU case to remain closed throughout the project. The completed unit is intended as a high-current source with fixed rails and one added adjustable converter; it is not a laboratory power supply with independently adjustable current limiting on every output.

### Team
| Member | Primary responsibilities | Specific contribution / evidence |
|---|---|---|
| Thepnimit Onchaiya | Hardware / electrical / testing / documentation | Hardware construction, electrical connections, output verification, measurement, enclosure/front-panel work |
| Korn Rasarak | Hardware / testing / documentation / presentation | Hardware construction, electrical connections, testing, documentation, presentation/support |

### Source PSU
| Item | Recorded information |
|---|---|
| Brand | OKER |
| Model | EB-480 |
| Rated power | 480 W Max |
| Input shown on label | 230 V / 50 Hz |
| Source PSU case | Kept closed |
| Exact source rail current limits | - |
| Exact source manufacturer document | - |

### Current evidence summary
The supplied photographs support repeated DMM measurements of the +3.3 V, +5 V, +12 V and adjustable outputs. Other required project evidence remains explicitly marked `-` where no actual record was supplied.

---

# 2. Project Requirements and Acceptance Criteria

The course acceptance structure requires a safe source PSU, fixed rails, separate branch protection, an approved adjustable converter, insulated control, indication, mechanical enclosure, unpowered checks, electrical performance evidence, documentation, and a safe demonstration.

| Requirement | Project implementation / current evidence | Status |
|---|---|---|
| Approved source PSU | OKER EB-480; label and construction photos | Documented |
| +3.3 V | External binding post; measured | Measured |
| +5 V | External binding post; measured | Measured |
| +12 V | External binding post; measured | Measured |
| -12 V | Not presented in this implementation | `-` / requires instructor acceptance |
| Separate fuse for accessible branches | Four 1 A, 250 V fuses reported | Documented |
| Adjustable output | ZK-4KX buck-boost converter | Documented |
| Protected adjustable input | Converter installed; exact branch mapping | `-` |
| Insulated PS_ON control | Panel control present | Formal verification `-` |
| Power-state indication | 5 V standby LED and 12 V illumination | Documented |
| Binding posts | Front panel | Documented |
| Strain relief | External enclosure / wiring evidence | Visual evidence |
| Secured wiring | Internal photo evidence | Visual evidence |
| Closed enclosure | External enclosure | Visual evidence |
| No-load voltage | Three repeated readings | Measured |
| Approved-load voltage | - | Not measured/supplied |
| Voltage drop | - | Not measured/supplied |
| Ripple | - | Not measured/supplied |
| Thermal | - | Not measured/supplied |
| Repeated startup | - | Not measured/supplied |
| Minimum-load behavior | User report: stable; no minimum load needed | Record evidence `-` |
| Documentation | This repository | Documented |

---

# 3. Safety Boundary, Risk Assessment and Stop-Work Rules

## 3.1 Non-negotiable safety boundary

- The ATX case remains closed.
- Construction and wiring changes are performed with AC cable removed.
- +5VSB may remain energized whenever AC is connected.
- No loose paperclip or exposed temporary jumper is used for PS_ON.
- Every accessible output branch must be insulated and protected by an approved fuse.
- A fuse is not to be bypassed or increased.
- Temperature is not measured by touch.
- If a stop condition occurs, the normal output control is used when safe, AC is removed without touching suspected wiring, the team is warned, and the instructor is asked to check the system.

## 3.2 Risk assessment

| Hazard | Possible consequence | Control / mitigation |
|---|---|---|
| Mains / primary side of ATX PSU | Electric shock / injury | Do not open or probe primary side; keep original PSU case closed |
| Energized +5VSB | Unexpected energized circuit | Treat the PSU as energized whenever AC is connected |
| Output short circuit | High current, heating, damage | Separate branch protection; insulated terminals; controlled tests |
| Wrong polarity | Load or instrument damage | Verify polarity with DMM before connecting approved load |
| Excessive branch current | Heating / fuse operation | Compare current to fuse, conductor, connector, switch, terminal and source limits |
| Converter overload | Heating / shutdown / damage | Stay within approved converter input/output/current/power limits |
| Oscilloscope grounding | Accidental short circuit | Use only approved COM/reference method after grounding checkpoint |
| Loose wire/crimp | Intermittent / high-resistance joint | Secure terminations and perform tug check |
| Sharp enclosure edge | Insulation damage | Deburr/protect the external enclosure |
| Blocked ventilation | Heating | Maintain ventilation/airflow and do not block the PSU fan/exhaust |

## 3.3 Stop conditions

Stop immediately if:
- connector or pin direction is unclear,
- case/cable/insulation/fuse/terminal is damaged or missing,
- a rail is missing, unstable, or repeatedly cycles,
- current, ripple, or temperature is outside an approved limit,
- there is unusual smell, sound, smoke or heat,
- the oscilloscope reference connection is not clear,
- an instructor checkpoint has not been completed.

## 3.4 Signed checkpoint status

| Checkpoint | Result / revision required | Instructor/TA | Signature | Date/time |
|---|---|---|---|---|
| Source PSU and connector approval | - | - | - | - |
| Design review | - | - | - | - |
| Unpowered safety | - | - | - | - |
| Authorization to connect AC | - | - | - | - |
| Authorization for approved load | - | - | - | - |
| Load/ripple/thermal sign-off | - | - | - | - |
| Final acceptance | - | - | - | - |

---

# 4. Technical Reference and ATX Connector Record

The course identifies Intel's ATX Version 3 Multi Rail Desktop Platform Power Supply Design Guide, version 2.1a, as the main ATX reference, while requiring the exact selected PSU label and manufacturer documentation for source-specific limits.

## 4.1 Standard conventional 24-pin ATX logical map

The course reference identifies the following conventional signals:

| Pin | Signal | Typical color | Pin | Signal | Typical color |
|---:|---|---|---:|---|---|
| 1 | +3.3 V | orange | 13 | +3.3 V / optional sense return | orange / brown |
| 2 | +3.3 V | orange | 14 | -12 V | blue |
| 3 | COM | black | 15 | COM | black |
| 4 | +5 V | red | 16 | PS_ON | green |
| 5 | COM | black | 17 | COM | black |
| 6 | +5 V | red | 18 | COM | black |
| 7 | COM | black | 19 | COM | black |
| 8 | PWR_OK | gray | 20 | reserved / no connection | none |
| 9 | +5VSB | purple | 21 | +5 V | red |
| 10 | +12V1 | yellow | 22 | +5 V | red |
| 11 | +12V1 | yellow | 23 | +5 V | red |
| 12 | +3.3 V | orange | 24 | COM | black |

**Source-specific verification status:** `-`.

Color is a cross-check only. The exact connector, keying, pin number, signal, view orientation, and unplugged continuity should be verified against the selected source PSU documentation.

---

# 5. Source PSU Label, Connector View and Source Evidence

## 5.1 Label transcription

- Manufacturer/brand: **OKER**
- Model: **EB-480**
- Rated power: **480 W Max**
- Input shown: **230 V / 50 Hz**
- Exact +3.3 V current limit: **-**
- Exact +5 V current limit: **-**
- Exact +12 V current limit: **-**
- Exact -12 V current limit: **-**
- Combined-rail limits: **-**
- Manufacturer datasheet: **-**

## 5.2 Connector evidence

Supplied evidence:
-  — internal source PSU / harness evidence
- <img width="500" height="550" alt="ด้านในซัพพาย" src="https://github.com/user-attachments/assets/58786dfe-fb0f-4586-8bb0-916a9e5ea86d" /> 

- — front panel / +3.3 V measurement
<img width="300" height="400" alt="3V" src="https://github.com/user-attachments/assets/8dbc38de-f389-4b4b-8e08-4b352292ba58" />

Exact verified connector mapping for the selected physical PSU: .

---

# 6. Design Package and As-Built Documentation

## 6.1 Required schematic content

The final schematic must show:
- ATX main connector with verified pin numbers and signal names,
- every fixed rail and all COM returns used,
- +5VSB, PS_ON and PWR_OK,
- switches and indicators,
- one fuse and fuse rating for every exposed output branch,
- adjustable module input/output/return relationship,
- adjustable controls and display,
- protection,
- binding posts and other output connectors,
- conductor identifiers / net labels matching physical labels,
- test points and measurement reference,
- any special sense connection that must remain intact,
- any minimum-load circuit, marked not fitted unless approved.

### Final as-built schematic

<img width="500" height="300" alt="pic kicad project1 complete" src="https://github.com/user-attachments/assets/f5cc8450-93ab-4c3c-b956-3fe698409896" />


No schematic drawing has been fabricated in this report.

## 6.2 Front-panel / enclosure drawing

The course requires front-panel and internal-layout drawings with dimensions, terminal spacing, insulation behind terminals, fuse access, module mounting, ventilation/fan space, wire support, strain relief, feet, labels, and protection against debris entering the source PSU.

### Recorded physical dimensions

- Overall front width: approximately **34 cm**
- Overall front height: approximately **16.5 cm**
- Adjustable display: approximately **72 × 39 mm**
- Banana jack hole: approximately **Ø7 mm**
- Fuse-holder hole: approximately **Ø12 mm**
- DC/cigarette socket hole: approximately **Ø29 mm**
- DC socket marking: **12 V, 120 W max**

### Final front-panel / internal layout drawing

<img width="300" height="450" alt="กัปตันวาด" src="https://github.com/user-attachments/assets/cab19cc2-a8f5-4a38-9d30-cdaddf856407" />

<img width="500" height="300" alt="พอสวาด" src="https://github.com/user-attachments/assets/b71de8d1-8f7e-463a-9ff9-ef6b14866159" />


---

# 7. Protection and Wiring Schedule

The course requires branch protection before exposed output wiring and specifically states that a branch fuse protects the wire and hardware after the fuse. Fuse selection must be approved for type, current rating, voltage rating, interrupt rating and speed.

| Branch | Planned load | Design current | Fuse/type | Wire | Connector | Limit | Approval |
|---|---:|---:|---|---|---|---|---|
| +3.3 V | - | - | 1 A, 250 V | - | Binding post | - | - |
| +5 V | - | - | 1 A, 250 V | - | Binding post | - | - |
| +12 V | - | - | 1 A, 250 V | - | Binding post | - | - |
| -12 V | - | - | 1 A, 250 V | - | - | - | - |
| Adjustable input | - | - | 1 A, 250 V | - | Converter input | - | - |
| +5VSB / indicator | - | - | - | - | - | - | - |

**Known installed fuse information:** four fuses, each **1 A, 250 V**.

**Exact branch-to-fuse mapping, wire gauge, connector current rating, switch rating and approval record:** `-`.

---

# 8. Bill of Materials

The course requires part identifiers, ratings, datasheets and cost/source. The exact approved design controls the final BOM.

| Item | Identifier / model | Rating / specification | Qty | Datasheet / source | Cost | Status |
|---|---|---|---:|---|---:|---|
| Source PSU | OKER EB-480 | 480 W Max; 230 V/50 Hz label | 1 | - | - | Used |
| Buck-boost converter | ZK-4KX | Input 5–30 V; output 0.5–30 V (module label) | 1 | - | - | Used |
| Fuse | - | 1 A, 250 V | 4 | - | - | Used |
| Fuse holder | - | Panel mount | 4 | - | - | Used |
| Binding post | - | Insulated panel terminal | - | - | - | Used |
| DC socket | - | Marked 12 V, 120 W max | 1 | - | - | Used |
| Standby LED | - | 5 V | 1 | - | - | Used |
| LED strip | - | 12 V, warm white | 1 | - | - | Used |
| PS_ON switch | - | Maintained insulated switch | 1 | Exact rating - | - | Used |
| IEC inlet/outlet | - | Panel type | - | Exact rating - | - | Used |
| Internal wire | Various | Various sizes according to branch | - | Exact gauges - | - | Used |
| Ferrules/crimp/heat shrink | - | - | - | - | - | Used / exact data - |
| Cable strain relief | - | - | - | - | - | Used / exact data - |
| Fasteners/standoffs | - | - | - | - | - | Used / exact data - |
| Enclosure | - | Approx. 34 × 16.5 cm front dimensions | 1 | - | - | Used |
| DMM | UNI-T UT33A+ | DC voltage measurement | 1 | UNI-T documentation | - | Test instrument |

---

# 9. Construction Procedure and Evidence

Construction is required to be performed with the AC cable physically removed.

### Construction record

1. Photograph the intact source PSU, label, connectors and cable condition; assign project revision.
2. Compare the 20/24-pin connector with source PSU documentation; label every used wire/breakout terminal and insulate unused wires.
3. Assemble the external enclosure, binding posts, fuse holders, switches, indicators, converter, guards and strain relief without the PSU connected.
4. Wire one branch at a time according to the approved schematic using the specified conductor, termination, insulation and restraint.
5. Perform a tug check on each crimp or terminal.
6. Wire the maintained PS_ON-to-COM control and indicators, keeping the control path distinct from fused load branches.
7. Wire the adjustable converter input through its approved branch fuse and confirm input/output polarity and common-return arrangement.
8. Fit approved fuses only after checking every downstream branch.
9. Inspect loose strands, sharp edges, damaged insulation, exposed metal, labels, loose hardware, blocked airflow and metal debris.
10. Close the external enclosure. No student-accessible live conductor should remain exposed during operation.
11. Update the as-built schematic and photograph the work before first power.
12. Record every deviation from the approved design before proceeding.

### Construction evidence
The supplied photos are stored in 

<img width="200" height="250" alt="สีขาว" src="https://github.com/user-attachments/assets/1b0edb18-3f39-4052-a160-885c704d3c47" />  <img width="200" height="250" alt="สายไฟปลอก" src="https://github.com/user-attachments/assets/dbc347c3-e024-4aa2-a1cd-25bd7bc08b2d" />  <img width="200" height="250" alt="อุปกรณ์" src="https://github.com/user-attachments/assets/a30de203-ad6d-4740-ba46-cdb5d5ec29c1" />  <img width="300" height="200" alt="LINE_ALBUM_1102569 BE_261001_4" src="https://github.com/user-attachments/assets/561a6692-7799-4114-8a92-71cdd68314de" />  <img width="200" height="250" alt="พันสายไฟ" src="https://github.com/user-attachments/assets/60ef1c15-702d-47de-98bc-50d7eac5026b" />  <img width="300" height="200" alt="LINE_ALBUM_1102569 BE_261001_6" src="https://github.com/user-attachments/assets/a76e001e-1f32-469d-8dd8-bb501e717f4a" />  <img width="200" height="250" alt="LINE_ALBUM_1102569 BE_261001_3" src="https://github.com/user-attachments/assets/36ef05d0-2bbd-4d99-b42a-eb5c92f25316" />  <img width="200" height="250" alt="3V" src="https://github.com/user-attachments/assets/fae05e63-f52d-4f75-b9a6-d9a644075555" />  <img width="200" height="250" alt="5V" src="https://github.com/user-attachments/assets/ae709ea0-ed9b-49f7-aa2c-643fceda1e80" />  <img width="200" height="250" alt="12 V เอาอันนี้ไปใส่" src="https://github.com/user-attachments/assets/da5a55c3-aeb6-4709-8abb-692cfdb5924f" />  <img width="200" height="250" alt="22 V" src="https://github.com/user-attachments/assets/e457f6a9-fec2-42f9-83fd-bf533e86c122" />  











---

# 10. Unpowered Inspection and First-Power Gate

## 10.1 Unpowered inspection checklist

Performed with AC disconnected and all loads removed:

| Check | Expected / required condition | Measured / observed | Pass | Initials |
|---|---|---|---|---|
| Source PSU / revision / schematic | Match | - | - | - |
| +3.3 V path to connector | Correct | - | - | - |
| +5 V path to connector | Correct | - | - | - |
| +12 V path to connector | Correct | - | - | - |
| -12 V path to connector | Correct if used | - | - | - |
| Rail-to-rail shorts absent | No unintended continuity | - | - | - |
| Resistance output-to-COM | Explained by indicators/capacitors if low/changing | - | - | - |
| PS_ON switch operation | Connects to COM only when commanded | - | - | - |
| Adjustable input/output polarity | Correct | - | - | - |
| Binding posts / polarity labels | Correct and separated | - | - | - |
| Enclosure / labels / insulation | Secure | - | - | - |
| Ventilation / restraint / strain relief | Secure and clear | - | - | - |
| Fuse type/rating | Matches schedule | Four 1 A, 250 V reported | - | - |
| Authorization to connect AC | Instructor/TA | - | - | - |

---

# 11. Controlled First Power and Repeated-Start Test

The course procedure calls for:
1. project control OFF;
2. connect DMM to +5VSB and COM with AC disconnected;
3. apply AC and verify +5VSB and standby indication;
4. request main rails using PS_ON;
5. observe fan/state and verify PWR_OK if used;
6. measure fixed rails at zero external load;
7. measure adjustable output before load;
8. turn main rails off and disconnect AC before wiring/setting changes requiring contact;
9. repeat three controlled starts and record abnormal shutdown, delay, overshoot or inconsistency.

### Repeated-start record

| Start | +5VSB | +3.3 V | +5 V | +12 V | -12 V | PWR_OK | Adj. V | Pass |
|---|---:|---:|---:|---:|---:|---|---:|---|
| 1 | - | - | - | - | - | - | - | - |
| 2 | - | - | - | - | - | - | - | - |
| 3 | - | - | - | - | - | - | - | - |

**Authorization for approved load tests:**  
Instructor/TA: `-`  
Signature: `-`  
Date/time: `-`

---

# 12. Minimum-Load Evidence

The user reports:

- **Stable without external minimum load:** YES
- **Minimum load required:** NO

However, the actual measurement record / source-specific evidence supporting the minimum-load conclusion is:

**-**

---

# 13. Measured No-Load Output Voltage

The supplied photos show a UNI-T UT33A+ DMM in DC-voltage mode.

| Run | +3.3 V | +5 V | +12 V | Adjustable |
|---|---:|---:|---:|---:|
| 1 | 3.44 V | 5.24 V | 11.93 V | 22.00 V |
| 2 | 3.43 V | 5.24 V | 11.92 V | 21.99 V |
| 3 | 3.44 V | 5.23 V | 11.93 V | 22.00 V |

### Average values

- +3.3 V: **3.437 V ≈ 3.44 V**
- +5 V: **5.237 V ≈ 5.24 V**
- +12 V: **11.927 V ≈ 11.93 V**
- Adjustable: **21.997 V ≈ 22.00 V**

### Repeatability

| Output | Minimum | Maximum | Range |
|---|---:|---:|---:|
| +3.3 V | 3.43 V | 3.44 V | 0.01 V |
| +5 V | 5.23 V | 5.24 V | 0.01 V |
| +12 V | 11.92 V | 11.93 V | 0.01 V |
| Adjustable | 21.99 V | 22.00 V | 0.01 V |

The three displayed readings for each output are within a 0.01 V range.

---

# 14. Fixed-Rail Load and Voltage-Drop Test

The course requires, for each accessible rail, no-load and approved-load measurements at the binding post and, when accessible without defeating the enclosure, at the upstream breakout test point.

### Formula

$$
% \Delta V = \frac{V_{load}-V_{no-load}}{V_{no-load}}\times100%
$$

$$
V_{drop}=V_{upstream}-V_{post}
$$

### Test table

| Rail | Source PSU limit | Fuse | No-load V | Load A | Loaded V | %ΔV | Upstream V | Post V | Drop V | Pass |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| +3.3 V | - | 1 A | 3.437 V avg | - | - | - | - | - | - | - |
| +5 V | - | 1 A | 5.237 V avg | - | - | - | - | - | - | - |
| +12 V | - | 1 A | 11.927 V avg | - | - | - | - | - | - | - |
| -12 V | - | 1 A | - | - | - | - | - | - | - | - |

---

# 15. Adjustable-Output Test

The course requires testing the **minimum, middle and maximum approved output settings**, staying within planned voltage/current/power limits, and recording DMM voltage, display voltage, load current, converter input voltage/current, temperature, and CV/CC state when applicable.

### Test table

| Setting | DMM V | Display V | Load A | Input V/A | Temp. | CV/CC | Pass |
|---|---:|---:|---:|---|---:|---|---|
| Minimum | - | - | - | - | - | - | - |
| Middle | - | - | - | - | - | - | - |
| Maximum / recorded no-load setting | 22.00 V | - | - | - | - | - | - |

**Important:** The 22.00 V value is an actual recorded output setting. It is not presented here as a maximum-current or full-load performance result.

---

# 16. Ripple Measurement

The course requires oscilloscope testing only after the Lab 6 grounding checkpoint, using the approved COM point and a safe short probe ground connection. The record must include instrument model, probe, attenuation, coupling, bandwidth limit, vertical scale, timebase, measurement point, load and capture method.

### Ripple record

| Rail | Load | Instrument/probe | Settings | Ripple mVpp | Capture file | Pass |
|---|---:|---|---|---:|---|---|
| +3.3 V | - | - | - | - | - | - |
| +5 V | - | - | - | - | - | - |
| +12 V | - | - | - | - | - | - |
| -12 V | - | - | - | - | - | - |
| Adjustable | - | - | - | - | - | - |

**No ripple data were supplied.** No simulated mVpp values are included.

---

# 17. Thermal Test

The course requires an approved temperature instrument, an agreed test load, at least 10–15 minutes after readings stabilize, and measurement of the fuse holder, highest-loss connector/terminal, converter, approved load resistor if used, and enclosure exhaust. Room temperature, elapsed time, load and stop limit must be recorded. Touch is prohibited as temperature evidence.

| Location | Load | 0 min | 5 min | 10 min | 15 min | Stop limit | Pass |
|---|---:|---:|---:|---:|---:|---:|---|
| Fuse holder | - | - | - | - | - | - | - |
| Output post / terminal | - | - | - | - | - | - | - |
| Converter | - | - | - | - | - | - | - |
| Other hotspot / exhaust | - | - | - | - | - | - | - |

**Room temperature:** `-`  
**Temperature instrument:** `-`  
**Actual test load:** `-`

---

# 18. Engineering Calculations

## 18.1 Fixed-rail regulation

Required:  

%ΔV = [(V_load - V_no-load) / V_no-load] * 100%

Current measured no-load averages:

- +3.3 V: 3.437 V
- +5 V: 5.237 V
- +12 V: 11.927 V

Because loaded values were not supplied:

- +3.3 V regulation = `-`
- +5 V regulation = `-`
- +12 V regulation = `-`

## 18.2 Branch voltage drop

$$
V_{\text{drop}} = V_{\text{upstream}} - V_{\text{post}}
$$

Actual upstream and post measurements are:

`-`

Therefore calculated branch drop is not reported.

## 18.3 Output power

$$
P_{\text{out}} = V_{\text{out}} I_{\text{out}}
$$

At the recorded adjustable output:

- Vout = 22.00 V
- Iout = `-`
- Pout = `-`

## 18.4 Converter loss

$$
P_{\text{loss}} = P_{\text{in}} - P_{\text{out}}
$$

Actual converter input current and measured efficiency:

`-`

Therefore P_loss = `-`.

## 18.5 Current and power limits

The required comparison is:

**source PSU rail limit → combined rail power → fuse → wire → connector → switch → terminal → converter → temperature limit**

Exact source limits, conductor gauges, connector/switch ratings and measured input current are:

`-`

No unsupported current/power limit is claimed.

## 18.6 Thermal

No temperature measurements were supplied, so no thermal loss estimate or temperature acceptance result is calculated.

---

# 19. Construction Photographs

| Photo | Evidence description |
|---|---|
|  | Source PSU / internal low-voltage harness evidence |
|   <img width="350" height="400" alt="3V" src="https://github.com/user-attachments/assets/48e2d517-f783-4d58-b183-1dec78078f6f" /> | +3.3 V DMM measurement |
|   <img width="350" height="400" alt="5V" src="https://github.com/user-attachments/assets/81362bf1-ef1b-4f5f-ae87-043e233f33a5" /> | +5 V DMM measurement |
|   <img width="350" height="400" alt="12 V เอาอันนี้ไปใส่" src="https://github.com/user-attachments/assets/5ca300eb-75e2-42c5-9a38-0c53f3083b7d" /> | +12 V DMM measurement |
|   <img width="350" height="400" alt="22 V" src="https://github.com/user-attachments/assets/2e34741d-8148-4313-84e0-0e97fb413fd0" /> | Adjustable output / 22.00 V DMM measurement |

**Additional evidence specifically showing insulation/resraint/strain relief/labels:** use the supplied construction photos as visual evidence; exact image-to-feature annotation: .

---

# 20. Faults, Diagnostic Evidence, Corrections and Retest

The course requires a fault log and evidence-based correction. If no actual fault was recorded, a blank entry must remain rather than inventing one.

| Fault / symptom | De-energized or controlled diagnostic evidence | Correction | Retest result | Initials/date |
|---|---|---|---|---|
| - | - | - | - | - |

---

# 21. Operating Instructions

## Before operation
1. Inspect the closed enclosure.
2. Check terminals, labels, fuse holders and accessible wiring.
3. Confirm the adjustable output is set to a safe voltage.
4. Do not connect a sensitive load until output voltage has been checked with a DMM.

## During operation
1. Apply AC only after required checks and instructor authorization.
2. Use the normal PS_ON/main control.
3. Verify the selected output and polarity.
4. Stay within approved current, fuse, conductor, connector, terminal, switch and converter limits.
5. Do not change a resistor or move a current-meter lead while power is on.
6. Stop the test if a stop condition occurs.

## Fuse replacement
1. Turn the project output off.
2. Remove AC.
3. Allow stored energy and hot parts to become safe.
4. Identify and correct the reason for fuse operation.
5. Replace only with the same approved fuse type and rating.
6. Never bypass the fuse or install a higher value to continue testing.

## Shutdown
1. Use the normal control to turn the output off.
2. Remove the load when appropriate.
3. Remove AC before any wiring, fuse or setting change requiring contact with the circuit.
4. Close and secure the enclosure.

## Storage
Store the unit:
- disconnected from AC,
- with outputs unloaded,
- with the enclosure closed,
- with wiring protected,
- with the adjustable output left at a safe setting.

---

# 22. Limitations

1. This unit is an ATX-derived high-current bench source, not a full laboratory power supply with independent current limiting on every output.
2. The project report currently contains verified no-load voltage measurements but does not contain approved-load, ripple, voltage-drop or thermal measurements.
3. Exact source PSU rail current limits are not yet transcribed from the nameplate.
4. Exact wire gauges, connector ratings, switch ratings and branch mapping are not documented here.
5. The -12 V external-output implementation is not documented in the supplied evidence and therefore remains `-`.
6. Formal ATX compliance is not claimed; the course states that the project is not a formal ATX compliance test.

---

# 23. Individual Contribution

## Thepnimit Onchaiya
- Hardware construction
- Electrical connections
- Output verification
- Measurement
- Documentation
- Enclosure/front-panel work

## Korn Rasarak
- Hardware construction
- Electrical connections
- Testing
- Documentation
- Presentation/support

Both students are expected to understand the complete system and safe operation.

---

# 24. Week/Milestone Record

| Milestone | Required evidence | Team record |
|---|---|---|
| Briefing | Safety boundary; possible source PSU; team members | Completed/documented |
| Source PSU and team approval | Team list; contribution plan; source PSU label/case/connector evidence | - |
| Design review | Requirements; schematic; calculations; protection schedule; enclosure/test plan | - |
| Construction | Approved parts; workmanship photos; as-built revision; unpowered checks | Photos available; formal sign-off - |
| Load/ripple/thermal sign-off | Signed tables; captures; fault log; acceptance decision | - |
| Supervised completion | Final construction; inspection; retest; rehearsal | - |
| Final assessment | Prototype; GitHub document; evidence; presentation | - |

---

# 25. Final Acceptance and Operating Record

| Final item | Pass / limitation / evidence reference | Initials |
|---|---|---|
| External construction | Visual evidence available | - |
| Fixed rails, fuses, labels, polarity | No-load voltage evidence available; full acceptance - | - |
| Adjustable output and declared current-limit behavior | 22.00 V recorded; current-limit test - | - |
| PS_ON / standby/main indication / shutdown | Visual indication; formal test - | - |
| Enclosure / insulation / restraint / strain relief / airflow | Visual evidence; formal checkpoint - | - |
| No-load and repeated-start behavior | No-load measured; repeated-start - | - |
| Approved-load voltage and branch drop | - | - |
| Ripple measurement | - | - |
| Thermal observation | - | - |
| GitHub evidence and operating instructions | Documented in repository | - |
| Demonstration and individual understanding | - | - |
| Approved operating limits and limitations | Documented; instructor conditions - | - |

---

# 26. Troubleshooting Guide

| Symptom | De-energized checks / controlled evidence | Prohibited response |
|---|---|---|
| No +5VSB | AC source under instructor control; PSU input switch; source condition; verified pin and DMM setup | Opening PSU or probing primary side |
| Main rails do not start | Verify PS_ON, maintained-switch continuity, COM return, source documentation | Energized paperclip jumper or repeated rapid cycling |
| PSU starts then stops | Disconnect loads; inspect shorts/polarity; review protection and minimum-load procedure | Larger fuse or random dummy resistor |
| One rail is incorrect | Stop; disconnect AC; verify connector/pin orientation, meter reference, branch path and source limits | Connecting rails together or internal adjustment |
| Voltage drops at load | Branch current; fuse/holder; wire; crimp; connector; resistance; temperature evidence | Raising allowed current without redesign |
| Adjustable output is wrong | Verify module input/output identification, polarity, control procedure, DMM | Treating unverified display as proof |
| Excessive ripple/noise | Probe reference; ground-lead length; bandwidth; load; fixture; repeatability | Moving an earth-ground clip to an arbitrary node |
| Heating or odor | Stop and remove AC; inspect loss, rating, mounting and airflow after safe cooldown | Touch test; blocked fan; continued operation |

---

# 27. References and Learning Resources

### Required/course sources
1. Electronics Circuits Laboratory — **Project 1: ATX Bench Power Supply**, `03_project01(2).pdf`.
2. Intel — **ATX Version 3 Multi Rail Desktop Platform Power Supply Design Guide**, version 2.1a, as specified by the course.
3. Exact source PSU manufacturer documentation for OKER EB-480: `-`.
4. Exact ZK-4KX module documentation used by team: `-`.
5. UNI-T UT33A+ documentation.

### Course-listed learning resources
The course also lists practical examples/resources including:
- DroneBot Workshop
- GreatScott! DIY Lab Bench Power Supply
- Matthew Beckler
- Frugha
- Beginner breakout-board build
- HowToWith GEO
- TheVDM
- Hackaday.io
- PCB Smoke
- Tom Schmidt
- SparkFun multimeter tutorial
- SparkFun voltage/current/resistance/Ohm's law
- All About Circuits fuse introduction
- Keysight bench-power-supply guidance
- Tektronix power-supply probing guidance

These examples are secondary learning resources. The course specifically states that examples involving opening the source PSU, cutting its harness, floating output common, or using a generic dummy load are outside this project's closed-case external-only procedure.

---

# 28. 3.11.2 Completeness Matrix

| 3.11.2 item | Location in this repository | Status |
|---|---|---|
| 1. Summary/team/source/revision/requirements | Sections 1–2 | Documented |
| 2. Safety/risk/stop/checkpoints | Section 3 + `evidence/checkpoints/` | Documented; signatures `-` |
| 3. Label/connector/source links | Sections 4–5 | Partially documented; exact connector/source docs `-` |
| 4. As-built schematic/front-panel drawing | Section 6 + `design/` | Template present; actual drawing `-` |
| 5. BOM | Section 8 + `bom/BOM.md` | Detailed fields present; missing identifiers/cost/docs `-` |
| 6. Protection/conductor/converter/loss/thermal calculations | Sections 7 and 18 | Detailed calculation framework; missing inputs `-` |
| 7. Construction photos | Section 19 + `evidence/photos/` | Supplied photos included |
| 8. Unpowered/start/min-load/fixed/adjustable/ripple/drop/thermal | Sections 10–17 | Full tables present; missing actual results `-` |
| 9. Faults/corrections/retest | Section 20 + `logs/` | Template present |
| 10. Operating/limitations/fuse/shutdown/storage | Section 21–22 | Documented |
| 11. Individual contribution | Section 23 | Documented |
| 12. References/exact instruments/modules | Section 27 | Documented; exact team documents `-` |

---

# 29. Measurement Integrity Statement

Only the values supported by the supplied photographs are reported as measured:
- +3.3 V ≈ 3.44 V
- +5 V ≈ 5.24 V
- +12 V ≈ 11.93 V
- Adjustable ≈ 22.00 V

No load, ripple, voltage-drop, thermal, startup, efficiency, converter-input-current, or source-rail-limit value has been invented. Where evidence was not supplied, the field remains `-`.
