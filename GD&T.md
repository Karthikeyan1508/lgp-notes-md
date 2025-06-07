**Types of Lines:**

1. ***Continuous Thick Line (Visible Object Line)***

- Use: Represents visible edges and outlines of objects

- Appearance: Solid, thick line

- Example: External edges of a solid block

 2. ***Continuous Thin Line***
Use:

- Dimension lines

- Extension lines

- Leader lines

- Hatching

- Appearance: Solid, thin line

- Example: Size indicators, hatching for section views

3. ***Dashed Thin Line (Hidden Line)***
   
- Use: Represents hidden edges not visible in the current view

- Appearance: Thin, short dashes

 - Example: Hole or feature on the back side of an object

4. ***Chain Thin Line (Center Line)***
   
- Use: Represents center axis of symmetrical objects (holes, cylinders)

- Appearance: Alternating long and short dashes

- Example: Axis of a shaft or bolt hole

5. ***Chain Thick Line (Cutting Plane Line)***
   
- Use: Indicates cutting plane in section views

- Appearance: Thick line with long dash–short dash pattern

- Example: Section A–A or B–B

6. ***Continuous Thin Freehand Line***
   
- Use: For short break lines

- Appearance: Thin, wavy freehand line

- Example: Break in a shaft or pipe to show detail

7. ***Continuous Thin Zigzag Line***
   
- Use: Long break lines

- Appearance: Thin zigzag line

- Example: Break in a long component like a beam

8. ***Chain Thin Line with Thick Ends***
   
- Use: Used to indicate special features like surfaces to be machined

- Appearance: Thin line with thick ends or dashes

 - Example: Specific surface treatments

**Dimensions:**

- Dimensioning is the process of annotating a drawing with measurements to define the size, location and features of an object.

1. ***Types of Dimensions***
   
A. ***Linear Dimensions***

- Measure lengths, widths, and heights (straight-line distances).

Includes:

- Horizontal dimensions

- Vertical dimensions

Aligned dimensions (along inclined surfaces)

B. ***Angular Dimensions***

- Measure angles between two lines or surfaces.

- Shown using an arc with degree value (°).

C. ***Radial Dimensions***

- Used to dimension circles and arcs.

Includes:

- Radius (R)

- Diameter (⌀)

***Types of Planes:***

 ***Principal Planes***

 A. ***Horizontal Plane (HP)***
 
- A plane that lies flat like the top of a table.

- Used to represent the Top View (TV) of an object.

B. ***Vertical Plane (VP)***

- A standing plane like a wall.

- Used to show the Front View (FV) of an object.

C. ***Profile Plane (PP) or Side Plane***

- Perpendicular to both HP and VP.

- Used to show the Side View (SV) (usually the right side).

B. ***Auxiliary Planes***
  
- Used when an object is inclined to the principal planes.

- Helps in showing true shape and size.

C. ***Inclined Planes***

- Planes inclined to either HP or VP.

- Do not show true shape in standard views.

D. ***Oblique Planes***

- Inclined to both HP and VP.

- Complex projection; used in advanced drawings.

***View Representation from Planes:***

| Plane | View            | Placement        |
| ----- | --------------- | ---------------- |
| HP    | Top View (TV)   | Below XY         |
| VP    | Front View (FV) | Above XY         |
| PP    | Side View (SV)  | Right/Left of FV |


**INTRODUCTION TO PROJECTION** 

- Projecting the image of an object to the plane of projection is known as projection. The
object may be a point, line, plane, solid, machine component or a building. Consider the
following illustration to project the image of an object on to a plane.

- Vertical plane (VP) which is assumed to be placed vertically. The front view of the
object is projected onto this plane.

- Horizontal plane (HP) which assumed to be placed horizontally. The top view of the
object is projected onto this plane.

![image](https://github.com/user-attachments/assets/cd71c3cf-92b6-4bea-b94b-1eb46cbb215f)

- When an object is assumed to be placed in first quadrant, the projection method followed is
called as first angle projection. In this method, the object is placed between the observer and
the plane of projection.

**First Angle Method:**

 1.The object lies In between the observer and the plane of projection. The plane of
projection Is always behind the object.

2. The object is assumed to be placed in first quadrant.
   
3. The front view or the elevation Is always above the top view or the plan.
 
4. The right hand end view/side view Is drawn to the left and left hand end view Is drawn to
the right.

5. The plane of projection may or may not be transparent

**Third Angle Method:**

1. Between the observer and the object ore transparent planes of projection. The plane of
projection Is always In front of the object.

2. The projections are drawn assuming that Uie object Is situated In third quadrant.
  
3. The front view Is always below the top view.
 
4. The right hand end view is drawn to the right and left hand end view Is drawn to the left.
  
5. The plane of projection Is always transparent.

![image](https://github.com/user-attachments/assets/f821cf45-b138-4cff-b573-7d1b218b0a4d)


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

![image](https://github.com/user-attachments/assets/b9ee295a-7388-4388-92ba-21f7a14669c5)
![image](https://github.com/user-attachments/assets/cf4ed84d-516e-45e9-9af2-e89fca084b84)

## Orientation Tolerances

There are **three (3)** separate orientation tolerances, but two of these are specific cases of the general tolerance called **angularity**.

- The two specific tolerances are:
  - **Perpendicularity (⊥):** 90° to a datum
  - **Parallelism (∥):** 180° to a datum

These tolerances control the orientation of features relative to a **datum plane or axis**.

### Angularity (∠)

- Controls a surface (non-feature of size), a center plane, or an axis of a feature of size at a specified angle.
- The tolerance zone can be:
  - Two parallel planes at the specified basic angle from a datum plane or axis within which the surface, center plane, or axis must lie.
  - Or a cylindrical zone within which the axis of the considered feature must lie.

### Material Condition Modifiers

- If angularity tolerance is specified for a feature of size, the material condition modifiers **m** (MMC) or **l** (LMC) may be specified.
- If neither modifier is specified, **Regardless of Feature Size (RFS)** applies.

## Straightness

- The symbol for straightness is **⎯**.
- There are **two kinds of straightness controls** which differ significantly:
  1. **Line elements of surfaces:** The Feature Control Frame (FCF) is attached to the surface.
  2. **Axis or median plane of features of size:** The FCF is attached to the size tolerance.

- The axis or median plane control **relaxes the form control** provided by Rule #1 because a perfect form boundary at MMC can be violated if the **m** (MMC) symbol is specified.

- **Figures:**
  - Fig. 5-24 shows control of **line straightness**.
  - Fig. 5-25 and Fig. 5-26 show control of **axis** and **median plane straightness** respectively.

- The **surface straightness tolerance** applies only to **line elements in the view** where the FCF is attached.
![image](https://github.com/user-attachments/assets/7ab629c1-8a14-4f6d-a2fd-f4525edcaa7c)
![image](https://github.com/user-attachments/assets/e22b381c-14cf-4ed8-ad91-17a43fd615cc)

## Flatness  
- Controls the distance between the high and low points of a surface.  
- The tolerance zone is defined by two parallel planes with no specific orientation.  
- **All elements of the entire surface must lie between these planes.**  
- Symbol: ⏤  
- Difference from straightness: flatness controls the **entire surface** (all views), while straightness controls only **line elements** in the view where the control applies.  


---

## Circularity (Roundness)  
- Controls each circular element of a cylinder independently.  
- Circular elements in a plane perpendicular to the axis must lie between two concentric circles whose radii differ by the specified tolerance.  
- Symbol: ○  


---

## Cylindricity  
- Controls the **entire surface** of a cylinder.  
- Tolerance zone: two concentric cylinders parallel to the axis of the actual mating envelope.  
- Radii of the concentric cylinders differ by the specified tolerance in the Feature Control Frame (FCF).  
- It is a **composite tolerance** controlling circularity, straightness, and taper.  
![image](https://github.com/user-attachments/assets/1f61edd6-3a47-4509-861a-88f3b2b99cf0)
![image](https://github.com/user-attachments/assets/30ec9b0e-5525-40eb-823f-9753fa59ad5b)
![image](https://github.com/user-attachments/assets/e168581f-2003-477a-ac53-84cc461c6f60)
![image](https://github.com/user-attachments/assets/547a57d4-6da9-402b-bc30-eba29c6b768a)

## Conversion of Position Tolerance Zone to/from Coordinate Tolerance Zone

Figure 5-34 is a chart for converting position tolerance zones to coordinate tolerance zones, and for converting coordinate tolerance zones to position tolerance zones.

When looking at the conversion chart in Fig. 5-34:

- Coordinate tolerance zones are listed across the top of the grid, increasing from left to right.
- On the right side of the grid, coordinate tolerance zones increase from bottom to top.
- Position tolerances are listed on the left side of the grid and increase from bottom to top.
- The position tolerances follow an arced line across the grid.

The diameter of a position tolerance is given on the drawings, but the diameter of a coordinate tolerance is given by the length of the diagonal line.

A diagonal line is drawn from the lower-left corner of the grid at a 45° angle to the upper-right corner of the chart. The diameter is calculated using the Pythagorean theorem:

\[
A^2 + B^2 = C^2
\]

In Figure 5-33:

- **A** is the total length of the horizontal line at the bottom connected to the circle, squared.
- **B** is the total length of the vertical line at the left or right edge connected to the circle, squared.
- The square root of the sum of these two sides equals the diameter **C**.

### Example Conversion

Suppose you want to convert a 0.010 diameter position tolerance to a coordinate tolerance:

1. Locate the 0.01 position tolerance on the left side of the chart.
2. Follow the corresponding arced line until it crosses the diagonal line.
3. From the intersection point, follow the horizontal line across to the right side of the chart.
4. The number on the right side corresponds to the appropriate **bilateral coordinate tolerance**.

In this example, the bilateral tolerance is approximately **± 0.0035**.

### Quick Verification

To verify this conversion quickly:

- Multiply the coordinate tolerance by **0.7** to get the total coordinate tolerance.
- Divide that total coordinate tolerance by **2** to obtain the bilateral coordinate tolerance.

This matches the value obtained from the chart.
![image](https://github.com/user-attachments/assets/30018eeb-87d2-433f-af72-e7009c0f6476)

The number obtained from the conversion chart and the number obtained by using the multiplier should be approximately the same.

Suppose it was desired to convert a coordinate tolerance such as **0.007** to a position tolerance.

- To use the conversion chart in Fig. 5-34, the coordinate tolerance must be in **bilateral coordinates**, so:

  \[
  0.007 \div 2 = \pm 0.0035
  \]

- Next, locate the number **0.0035** on the left side of the conversion chart.
- Follow the corresponding horizontal line across to the **left** until it intersects the diagonal line.
- At this intersection, follow the intersecting arced line all the way across and to the **left**.
- The number corresponding to that arced line on the left of the chart gives the associated **position tolerance**.

If done correctly, the position tolerance identified on the chart should be **0.010**.

This can be double-checked by using the multipliers on page 5-31.

---

To convert between position tolerancing and coordinate tolerance, either the **conversion table** identified in Fig. 5-34 or the **multiplication factor** 
