# Power-Distribution-CAD-4-Marine-Electrical-Design-3-Autonomous-Hybrid-EHD-Propulsion-System

This is a prototype of an automated marine solar microgrid array additionally equipped with Li Ion battery solar chargers. It implements a propellor-less ship that uses excess solar power to generate high voltage ionic wind sail. A smart onboarding power management system automatically activates an array of water generators to recharge lithium ion battery cells when there is lack of solar power using the ship's forward momentum.

**System Overview**

This proposal explains a solid-state marine vessel architecture which synthesizes state-of-the-art microgrid power routing with leading frontier atmospheric plasma dynamics. It circumvents the commonly encountered mechanical ship propulsion pitfalls of surface friction, gear transmission inefficiency and prop cavitation by employing a fully dielectric eliptic asymmetric electrohydrodynamic sail as a real-time dynamic energy buffer. The Cell Management System acts as a near-perfect closed-loop logic gate which phases the craft through three distinct thermodynamic states.

**State 1: Solar Overcharge Shunt Max Drive Activation** 

When excess charge saturates the chemical energy conduit volume and the counter-based battery pack reaches "high" state of charge (SoC) $`\text{SoC} \ge \text{SoC}_{\text{high}}`$ and refuses to accept additional electrons the BMS instantaneously isolates the solar-to-cells energy transfer pathway, unleashing the energy excess into the high-voltage step-up stage which will draw the high-voltage, low-current electric spark energized from the Sun to the asymmetry of the underpowered sail where ionic wind immediately propels the craft forward and turns electrical potential into thrust. 

**State 2: Nominal Solar Energy Harvest Cruising State** 

When the craft is cruising along in steady state operational conditions with day-light solar vector flux density operating on the arrays within nominal design specifications, with the pack power state of charge within "green" safe cruising limits $`\text{SoC}_{\text{low}} < \text{SoC} < \text{SoC}_{\text{high}}`$, then the spheroid sail asymmetry is throttled down or turned off and the solar arrays are routed directly into the pack as a charge saturation buffer and the hydro-generators are locked into a minimum-drag passive mode. 

**State 3: Hydro-Regenerative Power Recovery Mode** 

When the cells unloading rate suddenly drops to a negative power derivative due to a cloud front passing overhead, such as defined by $`\frac{dI_{\text{solar}}}{dt} < \text{Threshold}_{\text{drop}}`$, then the spheroid sail asymmetry is de-energized and extracted, the hydro-generator deployment system is engaged, (or a hull mounted regeneration circuit activated) forming a continuous bridge between the forward momentum and the generator rotor disk to sustain and resuscitate the air-to-electric conversion cycle. The ship's forward kinetic momentum $`M_{\text{ship}} \cdot v`$
drives the water past the generator, spinning the rotor to produce AC power.


_**Electrodynamic Field and Force Derivations**_

**Electric Field Asymmetry and Peek's Criterion**

To model the generation of non-equilibrium atmospheric plasma at the sail define a cylindrical coordinate system $r, \theta, z$ aligned with a single emitter wire element of radius $r_0$, situated at a distance $d$ from a planar mesh collector plate $d \gg r_0$. 

Assuming a quasi-static potential distribution where the spatial asymmetry factor $\alpha = A_{\text{collector}} / A_{\text{emitter}} \rightarrow \infty$, the electric field intensity $E(r)$ as a function of radial distance from the emitter wire axis is governed by Laplace’s equation.

$$\nabla^2 \Phi = 0 \implies E(r) = \frac{V}{r \ln(d/r_0)}$$

Where $V$ is the applied high-voltage DC potential. Air ionization occurs when $E(r)$ exceeds the local breakdown field strength $E_b$. Incorporating the air density correction factor $\delta$, the critical inception voltage $V_c$ required to trigger the Townsend avalanche is explicitly derived via Peek’s semi-empirical formulation.

$$V_c = m_v g_0 \delta r_0 \left(1 + \frac{0.301}{\sqrt{\delta r_0}}\right) \ln\left(\frac{d}{r_0}\right)$$

Where $g_0 \approx 3 \times 10^6 \text{ V/m}$ is the intrinsic disruptive field strength of dry air, and $m_v$ ($0 < m_v \le 1$) is the wire surface roughness manifestation coefficient.

**Space-Charge Limited Current and Net EHD Thrust**

Once $V > V_c$ the region outside the immediate corona ionization zone becomes dominated by unipolar ionic drift. In this drift zone, the electric field is governed by Poisson's equation rather than Laplace's equation, accounting for the space-charge density $\rho_c$.

$$\nabla \cdot \mathbf{E} = \frac{\rho_c}{\epsilon_0}$$

The localized current density $\mathbf{J}$ is linked to ion mobility $\mu$ by.

$$\mathbf{J} = \rho_c \mu \mathbf{E}$$

Substituting the current continuity equation $\nabla \cdot \mathbf{J} = 0$ for a one-dimensional drift gap $d$ yields the Mott-Gurney integration for the space-charge-limited current density.

$$J = \frac{9}{8} \epsilon_0 \mu \frac{V^2}{d^3}$$

The electrohydrodynamic body force per unit volume $\mathbf{f}_e$ acting on the fluid medium is the sum of the Coulomb force and the dielectrophoretic force.

$$\mathbf{f}_e = \rho_c \mathbf{E} - \frac{1}{2}E^2 \nabla \epsilon$$

Because the protective insulation matrix provides a constant relative permittivity ($\nabla \epsilon = 0$) within the active air gap, the dielectrophoretic term drops out. Integrating the remaining Coulomb volume force $\rho_c \mathbf{E}$ over the entire active volume of the sail gap yields the net macroscopic EHD thrust vector $\mathbf{F}_{\text{thrust}}$.

$$\mathbf{F}_{\text{thrust}} = \int_{\mathcal{V}} \rho_c \mathbf{E} \, d\mathcal{V} = \int_{0}^{d} \frac{J}{\mu} A_{\text{sail}} \, dx = \frac{I \cdot d}{\mu} \hat{\mathbf{x}}$$

Where $I$ is the total electrical current consumed by the emitter matrix, and $\hat{\mathbf{x}}$ is the unit vector pointing along the longitudinal centerline of the vessel's bow.

_**Fluid Momentum and Hydrodynamic Boundary Conditions**_

To solve for the steady-state cruise velocity of the vessel the atmospheric momentum transferred by the sail must balance the hydrodynamic skin-friction and wave-making drag of the hull. 

**Navier-Stokes Air Coupling**

The ionized air velocity vector $\mathbf{u}$ within the sail envelope is modeled by adding the electrodynamic body force to the incompressible Navier-Stokes formulation.

$$\rho_{\text{air}} \left( \frac{\partial \mathbf{u}}{\partial t} + (\mathbf{u} \cdot \nabla)\mathbf{u} \right) = -\nabla p + \mu_{\text{visc}} \nabla^2 \mathbf{u} + \frac{\mathbf{J}}{\mu}$$

This acceleration creates a continuous pressure differential $\Delta p$ across the plane of the highly porous collector mesh transforming electrical energy into a net mass flow rate $\dot{m}_{\text{air}}$ exiting the sternward face of the sail assembly.

**Hydrodynamic Drag Equilibrium**

The hull encounters a total hydrodynamic resistance $R_{\text{total}}$ as a non-linear function of vessel velocity $v$:

$$R_{\text{total}}(v) = \frac{1}{2} \rho_{\text{water}} v^2 A_{\text{wetted}} \left[ C_f(v) + C_w(v) \right]$$

Where:
* $\rho_{\text{water}}$ = Seawater density ($\approx 1025 \text{ kg/m}^3$)
* $A_{\text{wetted}}$ = Total wetted surface area of the insulated hull
* $C_f$ = Froude-dependent skin friction coefficient
* $C_w$ = Wave-making resistance coefficient

Setting $`\mathbf{F}_{\text{thrust}} = R_{\text{total}}(v)`$ establishes the steady-state kinematic equilibrium equation.

$$\frac{I \cdot d}{\mu} = \frac{1}{2} \rho_{\text{water}} v^2 A_{\text{wetted}} \left[ C_f(v) + C_w(v) \right]$$


_**Open-System Thermodynamic Conservation Equations**_

The vessel is evaluated as a rigid control volume $\mathcal{V}$ experiencing unsteady state-switching transients governed by the first and second laws of thermodynamics.

**The Control Volume Energy Balance**

The first law energy balance equation for the control volume is written as.

$$\frac{dE_{\mathcal{V}}}{dt} = \dot{Q} - \dot{W} + \sum \dot{m}_{\text{in}} \left(h + \frac{1}{2}u^2\right)_{\text{in}} - \sum \dot{m}_{\text{out}} \left(h + \frac{1}{2}u^2\right)_{\text{out}}$$

Expanding the internal energy derivative $\frac{dE_{\mathcal{V}}}{dt}$ into its constituent chemical (battery storage) and mechanical (vessel mass inertia) components yields.

$$V_{\text{bus}} I_{\text{batt}}(t) + M_{\text{ship}} v \frac{dv}{dt} = \eta_{\text{mppt}} P_{\text{solar}}(t) - P_{\text{loads}} - I^2 R_{\text{internal}} - R_{\text{total}}(v)v$$

Where $V_{\text{bus}}$ is the nominal DC bus voltage, $I_{\text{batt}}$ is the battery terminal current, and $R_{\text{internal}}$ is the lump-sum internal resistance of the cells.

**State-Dependent Energy Routing Matrices**

**Mode A Saturated Storage Shunt $\text{SoC} \ge \text{SoC}_{\text{high}}$**

When the chemical storage is full, the battery charging current is forced to zero $I_{\text{batt}} = 0$. The energy routing matrix shifts the entire solar output through the high-voltage transformer stage (operating at conversion efficiency $\eta_{\text{hv}}$), which modifies the open-system equation to.

$$\eta_{\text{hv}} P_{\text{solar}}(t) - P_{\text{loads}} = \left( \frac{I \cdot d}{\mu} \right) v + \dot{Q}_{\text{thermal}}$$

Where $`\dot{Q}_{\text{thermal}}`$ represents the irreversible Joule heating losses inside the emitter-collector matrix $`
\int_ {\mathcal{V}} \mathbf{J} \cdot \mathbf{E} \, d\mathcal{V}`$.

**Mode B: Negative Derivative Solar Intercept $`\frac{dI_{\text{solar}}}{dt} \le \text{Threshold}_{\text{drop}}`$**

When solar irradiance drops below the critical threshold, the BMS decouples the sail array $`I = 0`$ and deploys the hydrogenerator. The hydrogenerator extracts a mechanical torque $`T_{\text{mech}}`$ from the water velocity gradient, converting it to electrical charging power through the generator alternator windings $`\eta_{\text{gen}}`$.

$`V_{\text{bus}} I_{\text{batt}}(t) = \eta_{\text{gen}} \cdot T_{\text{mech}} \cdot \omega - P_{\text{loads}}`$

The extraction torque acts as an intentional hydrodynamic brake augmenting the total resistance profile.

$`R_{\text{total\_regen}}(v) = R_{\text{total}}(v) + \frac{T_{\text{mech}}}{r_{\text{turbine}}}`$

This forces a controlled decrescendo of the vessel's kinetic energy reservoir $`M_{\text{ship}} v \frac{dv}{dt}`$ to preserve electrical system functionality in the absence of solar exergy inputs.
