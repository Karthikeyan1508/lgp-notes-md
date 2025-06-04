# Geometric Dimensioning and Tolerancing (GD&T)

## What is GD&T?

GD&T is a compilation of symbols and rules that efficiently describe and control dimensioning and tolerancing for all types of drawings, such as those for castings and machined components. It is documented in:

- **ASME Y14.5M**: Contains the symbols, rules, and simple examples.
- **ASME Y14.8**: Provides guidance specifically for casting and forging drawings.

---

## Why Should GD&T Be Used?

### a. Efficient Communication
It is a simple and efficient method for describing the tolerancing mandated by the designer of the part.

### b. Eliminates Ambiguities
GD&T eliminates ambiguities regarding:
- Which Datum features are to be contacted.
- How Datum planes or axes are to be used for locating other features.

As a result, all inspections will produce the same conclusion — whether a dimension is within or out of tolerance.

> *Figures 5-1 and 5-2 (not included here) demonstrate the difference between traditional and GD&T-based drawings.*

### c. Simplifies Inspection
- Hard gauges can often be used.
- Inspection fixtures are often mandated, which simplifies inspection for production quantities.

### d. Enhances Design Consideration
GD&T forces the designer to fully consider:
- Function
- Manufacturing processes
- Inspection methods

This results in:
- Larger tolerances that still guarantee function.
- Reduced manufacturing and inspection costs.
- Bonus or extra tolerance under certain conditions, leading to significant cost savings.
- Faster analysis when determining whether a missed dimension is acceptable.

## Engineering & Design: Geometric Dimensioning

![image](https://github.com/user-attachments/assets/119138cb-3532-423e-909d-f4c1ddf302b7)

## Datum Reference Frame (DRF)

The Datum Reference Frame (DRF) is a core concept in GD&T. It establishes three mutually perpendicular planes (X, Y, and Z axes) used to manufacture and inspect parts consistently. These planes act like a Cartesian coordinate system and are formed using **Datum Simulators**—tools like surface plates, chucks, or gage pins.

These simulators interact with imperfect **Datum Features** on the part, helping both manufacturers and inspectors get consistent, accurate measurements. Aligning manufacturing and inspection setups to the same DRF eliminates the need for layout steps and improves process reliability.

---

## Primary, Secondary, and Tertiary Datums

- **Primary Datum**: First feature contacted (at least 3 points).
- **Secondary Datum**: Second feature contacted (at least 2 points).
- **Tertiary Datum**: Third feature contacted (at least 1 point).

Together, they define the DRF by forming three perpendicular datum planes. For cylindrical features, a **datum axis** is formed, and additional planes are used to fix orientation.

**Feature Control Frames (FCF)** specify datum precedence (left to right):
- First letter = Primary
- Second = Secondary
- Third = Tertiary

> This structure ensures that the part is properly oriented and measured with respect to the intended functional design.

![image](https://github.com/user-attachments/assets/077e309e-a0c5-42d5-8d5b-d13a72c0585e)

## Datum Feature vs Datum Plane

- **Datum Features** are the actual surfaces on a part that are contacted by datum simulators during inspection or manufacturing.  
  - Represented by a **capital letter** in a box (e.g., A, B, C), avoiding letters I, O, and Q.
  - Selection depends on function, accessibility, clarity, and adequate size.

- **Datum Planes** are **theoretical planes** established by **datum simulators** like a surface plate.  
  - They provide the reference for measurements and align the part in space.

---

## Datum Plane vs Datum Axis

- A **Datum Plane** is formed by flat surfaces of simulators like a surface plate.
- A **Datum Axis** is formed by cylindrical simulators like a 3-jaw chuck or expandable collet.

> While infinite planes can intersect a datum axis, only **one set** of mutually perpendicular planes is needed to define the **Datum Reference Frame (DRF)** and stabilize the part.

This stabilization ensures consistent inspection results across different setups by using the same origin and orientation for measurements.

![image](https://github.com/user-attachments/assets/39515dca-415b-4857-922f-2509e41a1cb6)
![image](https://github.com/user-attachments/assets/c05c676c-927d-450b-8b1a-2a6185ca11f5)
![image](https://github.com/user-attachments/assets/e3c5925d-787f-4154-a476-151337a4cfd0)

## Material Conditions

In GD&T, **features of size** (including datum features) have size tolerances, meaning the **material condition**—or amount of metal—can vary between:

- **Maximum Material Condition (MMC)**
- **Least Material Condition (LMC)**
- **Regardless of Feature Size (RFS)**

When geometric tolerances control center planes or axes of features of size, a **modifying symbol** can be applied in the **Feature Control Frame (FCF)** to indicate which material condition the tolerance applies to.

If **no symbol** is specified, the default is **RFS** — the tolerance applies regardless of material condition.

---

## Maximum Material Condition (MMC)

- **MMC** is the state of a feature containing the **most material**:
  - Largest size for **external features** (e.g., shafts).
  - Smallest size for **internal features** (e.g., holes).

- **Symbol**: `Ⓜ` (capital M inside a circle)

### Key Points:
- The specified tolerance in the FCF applies **only** at the MMC size.
- If the actual feature deviates from MMC, **bonus tolerance** is allowed.
  - **Virtual Condition** = MMC size ± geometric tolerance  
    - **External features**: MMC size **plus** tolerance  
    - **Internal features**: MMC size **minus** tolerance

- **Benefits of MMC**:
  - Ensures **assemblability**.
  - Enables the use of **hard gauges** (e.g., "Go" gauges) for quick inspection.
  - Geometric tolerance is independent of local size — only overall envelope matters.

> Example: MMC applied to a position tolerance enables manufacturing flexibility while guaranteeing fit and function.

![image](https://github.com/user-attachments/assets/f2367be7-5735-4ee6-97bf-fc481d5fed16)
![image](https://github.com/user-attachments/assets/0343bb4b-86a7-432f-b850-f0f3daace0f7)

## Regardless of Feature Size (RFS)

**RFS** applies when neither **MMC** nor **LMC** is specified.  
- It means the geometric tolerance applies **regardless of the feature’s actual size**.

- **Symbol**: *None* in ASME Y14.5 (1994); previously `Ⓢ` in 1982 standard.

### Key Points:
- Tolerance is limited strictly to the value specified in the **Feature Control Frame (FCF)**.
- If applied to **datum features of size**, the **actual axis or center plane** must be established without any bonus tolerance.
- **Always used** for:
  - **Runout**
  - **Concentricity**
  - **Symmetry**
- Used when **targets** are defined to establish datum axes or center planes.
- Helps control **wall thickness variation** between internal and external features.
- **Hard gages cannot be used**, as no additional tolerance is available.

> RFS ensures tight control by removing variability due to size changes — especially critical in precision features.
![image](https://github.com/user-attachments/assets/d5f34e66-b5f9-4ba5-a23e-56b42a9cac6e)
## Position, Concentricity, and Symmetry Tolerances

These tolerances are used to control the **location** and **alignment** of features, typically in reference to **datums**—answering the question: *"Located from what?"*

---

### 9.1 Position Tolerance

**Position tolerance** is the most widely used geometric control in GD&T.

#### Applications:
- Locates **features of size** (e.g., holes, slots) from **datum planes or axes**.
- Controls **coaxiality** of features (e.g., shafts to bores).
- Controls **center distances** between features and groups.

#### Key Concepts:
- Defines a **tolerance zone** where the axis or center plane of a feature may vary.
- Based on the **true position**—the ideal, perfect location of the feature.
- Actual location is allowed to **deviate** within the defined zone.
- Defined using **basic dimensions** (enclosed in a rectangular box) and referenced from **datum features**.

> Position tolerance ensures proper fit and function, even when parts are not manufactured perfectly.

## Concentricity & Symmetry Tolerances

These tolerances control the **median points** of a feature of size:

- **Concentricity (ⓒ):** Applied to **circular features**.
- **Symmetry (Ⓢ):** Applied to **non-circular features**.

Both require that the median points of the controlled feature, regardless of its size, lie within the specified **tolerance zone**:
- **Cylindrical zone** for concentricity.
- **Two parallel planes** for symmetry.

The tolerance zones are equally disposed about the **datum axis** (for concentricity) and **datum plane** (for symmetry).

### Usage Notes:
- These controls are **not often used** because establishing median points is difficult due to form irregularities.
- They are mainly used to control **out-of-balance conditions** when the mass center is not close to the axis of rotation or center plane.

*Examples of concentricity and symmetry control can be found in Figures 5-14 and 5-15 respectively.*

## Run Out Tolerances

Run out tolerances control the relationship of a feature relative to a **datum axis**, which is established from one (1) or two (2) diameters separated axially (see Fig. 5-19).

- The **material condition** applied to both the feature and datum is always **Regardless of Feature Size (RFS)**, because inspection requires a full 360° rotation.
- If targets are not specified to establish the datum axis, the entire datum feature must be contacted, which may be impractical.

### Types of Run Out Controls

1. **Circular Run Out (⦿)**
   - Controls cumulative variation of **circularity** (roundness) and **coaxiality** of features constructed around a datum axis.
   - Controls circular elements of surfaces angled to the datum axis (controls wobble).
   - Measured as **Full Indicator Movement (FIM)** for each circular element independently as the part is rotated 360°.
   - The dial indicator is reset after each full rotation to a new location.

2. **Total Run Out (⊕)**
   - Controls the **entire surface simultaneously**.
   - Controls cumulative variations in **circularity, coaxiality, straightness, taper, angularity**, and **profile** of the surface.
   - The dial indicator remains in contact during continuous 360° rotation.
   - For angled surfaces, it controls angular variation (wobble) and flatness (concavity or convexity).


