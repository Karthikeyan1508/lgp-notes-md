## HEAT TRANSFER UNIT-1
## Introduction

Heat is the form of energy that can be transferred from one system to another as a result of
temperature difference. A thermodynamic analysis is concerned with the amount of heat transfer as a
system undergoes a process from one equilibrium state to another. The science that deals with the
determination of the rates of such energy transfers is the heat transfer.

Heat can be transferred in three different modes: conduction, convection, and radiation. All modes
of heat transfer require the existence of a temperature difference and all modes are from the hightemperature medium to a lower-temperature one.

## Three Modes of Heat Transfer

There are three modes of heat transfer: conduction, convection, and radiation. Any energy exchange
between bodies occurs through one of these modes or a combination of them. Conduction is the transfer
of heat through solids or stationery fluids. Convection uses the movement of fluids to transfer heat.
Radiation does not require a medium for transferring heat; this mode uses the electromagnetic radiation
emitted by an object for exchanging heat.

## Heat Transfer by Conduction

**Conduction** is the transfer of heat through solids or still fluids. For example, when you touch a hot object, heat moves through your skin by conduction.

### In Solids:
Heat is transferred in two ways:
- **Lattice Vibration**: Atoms on the hot side vibrate more and pass energy to neighboring atoms.
- **Particle Collision**: Particles collide and transfer heat energy.

### In Stationary Fluids:
Heat is mainly transferred by **molecular collisions**.

Over time, the heat spreads evenly, and the material reaches the same temperature throughout.

![image](https://github.com/user-attachments/assets/c2f1c12d-e070-46f1-91e4-e95f1101b97b)

## Heat Transfer by Convection

**Convection** is the transfer of heat through the movement of fluids (liquids or gases). A hot surface warms the nearby fluid, which moves away and is replaced by cooler fluid. This continuous motion increases the rate of heat transfer.

### Types of Convection:

- **Natural Convection**: Fluid moves on its own due to temperature differences. Warm fluid becomes lighter and rises, while cooler fluid takes its place, creating a circular flow.

- **Forced Convection**: Fluid movement is caused by external sources like fans or wind. For example, a windy day feels colder because moving air removes body heat faster.

### Convection Coefficient (h):

- Measures how effectively a fluid transfers heat by convection.
- Units: W/m²·K
- Depends on fluid properties like **density**, **viscosity**, and **velocity**.
- Faster moving fluids (like strong winds) have higher `h` values, leading to more heat transfer.

![image](https://github.com/user-attachments/assets/8c1564e7-0ac4-43b4-ae90-4ebcd7e7ef0a)

![image](https://github.com/user-attachments/assets/49f6a2fb-930e-4273-b10b-1afcfad1c7f9)

## Heat Transfer by Radiation

**Radiation** transfers heat through electromagnetic waves and **does not need a medium**, making it the only form of heat transfer that works in a vacuum (like space).

Any object above **0 Kelvin (-273°C)** emits radiation. The hotter the object, the more energy it emits. For example, we feel warmer in sunlight due to **solar radiation** being absorbed by our skin.

### Key Concepts:

- **Electromagnetic Radiation** travels at the speed of light.
- Common types (from short to long wavelengths):  
  `Gamma rays > X-rays > UV > Visible light > Infrared (IR) > Microwaves > Radio waves`
- **Shorter wavelengths = more energy** (e.g., X-rays are more energetic than visible light).
- **Longer wavelengths** can penetrate materials more easily (e.g., radio waves pass through walls).

### Emission of Radiation:

- All objects emit radiation based on their **temperature (T)** and **emissivity (ε)**.
- The amount of radiation emitted is given by the **Stefan-Boltzmann Law**:

![image](https://github.com/user-attachments/assets/8193804a-9586-40da-906f-5dce4c305f7c)


### Absorption of Radiation:

- Radiation hitting a surface can be **reflected**, **absorbed**, or **transmitted**.
- Only the **absorbed part** contributes to heating the object.
- **Absorptivity (α)** = fraction of radiation absorbed.
- Net heat absorbed:

![image](https://github.com/user-attachments/assets/13b1e5e7-fe92-4fec-94d4-6bedc2a0d1f3)


### Example:

- The **Sun (~5800 K)** emits visible and UV radiation.
- A **hot stove** mostly emits **infrared radiation**.

## Heat Conduction Equation – Energy Balance for a Volume Element

The general energy balance for a small volume element is:

![image](https://github.com/user-attachments/assets/62682892-cda5-4dab-b8a0-cfa8b57d8e8c)
![image](https://github.com/user-attachments/assets/1c47d2ce-02b2-43a8-9e6f-62eda93d5160)


### **Total Heat Inflow + Internal Heat Generation = Heat Stored**

Or,

**(A) + (B) = (C)**

---

### Definitions:

- **Q** = Rate of heat flow (W)  
- **Q'** = Total heat flow over time `dt` → `Q' = Q × dt`
- **q<sub>g</sub>** = Internal heat generation per unit volume (W/m³)  
- **ρ** = Density (kg/m³)  
- **c** = Specific heat (J/kg·K)  
- **T** = Temperature (K)  
- **k** = Thermal conductivity (W/m·K)

---

### A. Heat Inflow by Conduction (Rectangular Coordinates)

Heat enters and leaves the small volume element from all directions (x, y, z).

Using **Fourier’s Law**:


---

### B. Internal Heat Generation



### C. Heat Stored in the Element



### Final Heat Conduction Equation:

Substituting all into the energy balance and dividing by `dx·dy·dz·dt`, we get:



---

### Coordinate Systems

Heat conduction equations vary slightly based on coordinate system:

- **(a) Rectangular** → (x, y, z)
- **(b) Cylindrical** → (r, φ, z)
- **(c) Spherical** → (r, φ, θ)

Each coordinate system has its own form of the Laplacian operator `∇²T`.

---
## Heat Conduction through Composite Wall UNIT - 2

# Heat Conduction in Cylinders and Spheres (Steady-State)

---

## Scenario: Hot Water Pipe

- Heat is lost radially from the hot fluid inside the pipe to the cooler outside.
- The pipe wall separates two fluids (hot inside, cold outside).
- Heat flows in the radial direction only → modeled as one-dimensional conduction in cylindrical coordinates.

**Assumptions:**
- Steady-state: No temperature change with time.
- One-dimensional radial heat flow: Temperature T = T(r), no variation in angular or axial direction.
- No internal heat generation.
- Constant thermal conductivity (k).

---

## General Energy Balance

At steady state:
![image](https://github.com/user-attachments/assets/04733cfc-1dab-4c55-8772-eb322027b8b1)
![image](https://github.com/user-attachments/assets/ee3ff293-da59-4a14-bb9d-597c2f5ec721)
![image](https://github.com/user-attachments/assets/9202c1c2-39fc-45dc-883f-a0a552dd93a3)
![image](https://github.com/user-attachments/assets/6de66132-5d49-4063-9428-72d13d24bbd0)
![image](https://github.com/user-attachments/assets/7ce49c00-f344-433c-a8ef-2c750ddd944d)
![image](https://github.com/user-attachments/assets/5ef384a1-ba27-484c-94aa-3c5c0cd862c7)
![image](https://github.com/user-attachments/assets/69b7239c-39ea-472d-bfa6-38d91cb97b55)
![image](https://github.com/user-attachments/assets/cab5c8a9-e2ec-4209-a420-4260c30f6538)

## Heat Transfer in Extended Surface (Fins) UNIT-II

# Introduction to Convection and Extended Surfaces (Fins)

## Convection

Heat transfer between a **solid surface** and a **moving fluid** is governed by **Newton’s Law of Cooling**:

  

### Methods to Increase Convective Heat Transfer:
1. **Increase the temperature difference**
2. **Increase the convection coefficient** \  
   - Achieved by increasing the fluid velocity (e.g., a cooling fan)
3. **Increase the contact surface area**  
   - Achieved using **fins** or **extended surfaces**

![image](https://github.com/user-attachments/assets/6462f2c9-b32c-4d6f-b738-ef0131676166)


When:
- Temperature difference is fixed
- Convective coefficient \( h \) is at its practical limit  
Then the only remaining option is to **increase the surface area** — and this is where **fins** come in.

---

## Fins and Extended Surfaces

**Fins** are **protrusions** attached to the surface to **enhance heat dissipation** by increasing the contact area with the fluid.

### Common Applications of Fins:
- Air-cooled engines (motorcycles, portable generators)
- Electronic components (CPU heat sinks)
- Radiators in automobiles
- Condensers in air conditioning systems

---

## Fin Analysis

A fin is attached to a **hot base surface** at temperature , and is surrounded by a **coolant** at temperature, with a convective coefficient.

![image](https://github.com/user-attachments/assets/aa077ba7-99fc-4431-b366-b2b067b8fb3c)

### Parameters:
- **Cross-sectional area**:  
- **Length of the fin**: 

As heat is **conducted along the fin**, some of it is **lost through the sides** by convection. Therefore, the **heat flow is not uniform** — it **varies along the length** of the fin.

Although the actual heat transfer is **two- or three-dimensional**, for simplification, an **equivalent one-dimensional model** is often used.

> This one-dimensional model introduces **heat sinks (negative heat sources)** along the fin, which simulate the energy loss due to convection from the sides.

---

## Differential Element Consideration

To analyze heat flow in the fin, consider a **differential element** of the fin along its length \( dx \):

- Heat enters the element by **conduction** from one side
- Some of it leaves by **conduction** to the next element
- The rest is **lost by convection** from the lateral surface area

This sets up a **differential energy balance**, which ultimately leads to the fin equation used in 1D analysis.

---

![image](https://github.com/user-attachments/assets/db75dde0-bf3f-4a6e-81c4-e735992f3582)

![image](https://github.com/user-attachments/assets/f6fc7c16-fcb7-4bb5-bdd2-1f4356d98d9f)

![image](https://github.com/user-attachments/assets/5dfcd758-7be7-4848-beff-5648abc256e7)

![image](https://github.com/user-attachments/assets/d6e0b3db-d2d9-458a-aa00-f20862e1759c)

## Boiling and condensation UNIT-IV
![image](https://github.com/user-attachments/assets/6c171141-6a31-4a6d-91cd-602eef89595c)

![image](https://github.com/user-attachments/assets/df186df5-69f6-4493-96a0-f6f60ade49f1)

![image](https://github.com/user-attachments/assets/fff382d7-a65e-4e1c-902b-c16c1edab78f)

![image](https://github.com/user-attachments/assets/ee9f50b6-155e-448a-bde8-40aaa6a8bdae)

![image](https://github.com/user-attachments/assets/9554c71e-99f0-4224-a1c0-7fd245f9673f)
![image](https://github.com/user-attachments/assets/5ef8c75d-a9ea-458f-884f-ab1495bcd3f5)
![image](https://github.com/user-attachments/assets/7b86fd99-0add-4134-bb12-2325943e1d1d)

## Radiation Heat Transfer UNIT-V
![image](https://github.com/user-attachments/assets/550d628f-bc38-42be-890b-edabaf21fd86)
![image](https://github.com/user-attachments/assets/b19103af-2e42-4c64-bdd2-459286f0c2d9)

# View Factor in Radiation Heat Transfer

Radiation heat transfer between surfaces depends on:

- The **orientation** of the surfaces relative to each other  
- Their **radiation properties**  
- Their **temperatures**

For example:  
- A camper on a cold night maximizes warmth by standing **close to the fire** and **facing it directly** rather than sideways, thus maximizing the radiation received.  
- A person sunbathing lies **on their back** to maximize solar radiation exposure instead of standing upright.

---

## Definition of View Factor

To account for the effect of orientation on radiation heat transfer between two surfaces, we define the **view factor** (also called: shape factor, configuration factor, or angle factor).

- It is a **purely geometric quantity**  
- It is **independent of surface properties and temperatures**

---

## Types of View Factors

- **Diffuse View Factor**:  
  Assumes surfaces are **diffuse emitters and diffuse reflectors**  
- **Specular View Factor**:  
  Assumes surfaces are **diffuse emitters but specular reflectors**

> In this context, we consider only **radiation exchange between diffuse surfaces**, so "view factor" here means **diffuse view factor**.

---

![image](https://github.com/user-attachments/assets/1d1922bc-f360-494e-aaad-fd6bca9be6b9)
![image](https://github.com/user-attachments/assets/1e0cf771-fd29-4a47-a946-6b09feda4901)

# Absorptivity, Reflectivity, and Transmissivity

Everything around us constantly emits radiation. The **emissivity** of a body represents its emission characteristics.

This means:

- Every body, including ourselves, is constantly bombarded by radiation coming from all directions and over a range of wavelengths.
- The radiation flux incident on a surface is called **irradiation** and is denoted by \( G \).

---

## Interaction of Radiation with a Surface

When radiation strikes a surface, it can:

- Be **absorbed**
- Be **reflected**
- Be **transmitted** (if the surface is partially transparent)

This is illustrated in Figure 11-31.

---

## Definitions

- **Absorptivity** \(\alpha\):  
  The fraction of the incident radiation (irradiation) that is **absorbed** by the surface.

- **Reflectivity** \(\rho\):  
  The fraction of the incident radiation that is **reflected** by the surface.

- **Transmissivity** \(\tau\):  
  The fraction of the incident radiation that is **transmitted** through the surface.

---

![image](https://github.com/user-attachments/assets/db1aeaf6-50b5-4d7b-a523-127ffdc05dda)

where G is the radiation energy incident on the surface, and Gabs, Grefs and G
are the absorbed, reflected, and transmitted portions of it, respectively. The
first law of thermodynamics requires that the sum of the absorbed, reflected,
and transmitted radiation energy be equal to the incident radiation. That is,
abs Gref + Gu
Dividing each term of this relation by G yields
![image](https://github.com/user-attachments/assets/5bdbbadf-c3d9-4209-83fd-8d98ef17965a)
![image](https://github.com/user-attachments/assets/8c76591c-cab0-49a1-b162-27bbbc0f8b83)
![image](https://github.com/user-attachments/assets/e34e730e-0c58-4db4-a5e8-647d38d48599)
![image](https://github.com/user-attachments/assets/77e0f81d-862b-4a91-8b9d-04aa72439a0e)

