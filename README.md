This is a prototype of an automated marine microgrid integrating solar overcharge driven electrohydrodynamic thrust with hydro-regenerative battery balancing.

**System Overview**
This project presents a novel solid-state marine vessel architecture that synthesizes advanced microgrid power routing with frontier atmospheric plasma dynamics. The system eliminates traditional mechanical propulsion vulnerabilities like friction, transmission loss and propeller cavitation by utilizing a fully insulated, asymmetric electrohydrodynamic sail as a dynamic energy buffer.

### Core Operational Workflow
1. **Solar Primacy & Saturation:** Under optimal daylight, the photovoltaic arrays supply clean DC power to the main battery bank. 
2. **Exergy Salvage (Thrust Mode):** When the Battery Management System (BMS) detects that the batteries are saturated (overcharge threshold reached), it shunts all excess solar exergy directly to a high-voltage step-up stage. This power fires an asymmetric electrode grid on the sail, generating a continuous ionic wind that drives the ship forward.
3. **Automated Hydro-Regeneration:** When cloud cover or nighttime causes a sudden drop in solar current, the BMS instantly senses the negative power derivative. It deactivates the sail and engages a hull-mounted hydrogenerator, converting the ship's forward fluid momentum back into DC electrical energy to recharge the batteries and maintain baseline electronics.
4. **Environmental Isolation:** The entire hull, onboard circuitry, and conductor paths are encapsulated within a seamless, high-dielectric hydrophobic material. This solves the historic "marine grounding dilemma" by preventing humid, salty sea air and conductive seawater from short-circuiting or bleeding away the high-voltage fields.

---

## 2. Detailed Physics & Thermodynamic Foundations

### A. Electrohydrodynamic (EHD) Thrust Generation
The solid-state sail operates via non-equilibrium atmospheric plasma actuation. To generate net forward momentum, the electric field ($\mathbf{E}$) must be highly non-uniform, achieved via an extreme spatial asymmetry between the electrodes.

#### 1. Corona Ignition (Peek's Law)
The charging electrode (emitter) is designed with an incredibly small radius of curvature ($r_0$), utilizing sub-millimeter micro-wires or laser-sharpened conductive ribbon edges. This forces the electric field gradient to exceed the critical dielectric breakdown threshold of air ($V_c$):

$$V_c = m_v g_0 r_0 \left(1 + \frac{0.301}{\sqrt{\delta r_0}}\right) \ln\left(\frac{d}{r_0}\right)$$

Where:
* $m_v$ = Wire surface irregularity factor
* $g_0$ = Disruptive electric field of air ($\approx 3 \times 10^6 \text{ V/m}$)
* $\delta$ = Air density factor
* $d$ = Distance between emitter and collector

#### 2. Ionic Space-Charge Drift (Mott-Gurney Law)
The downstream collector electrode is larger than the emitter by a massive geometric factor (e.g., a highly porous, wide-gauge metallic honeycomb mesh). This distributes the charge, lowering the local gradient to prevent sparking. The resulting space-charge-limited current density ($J$) follows the Mott-Gurney relationship:

$$J = \frac{9}{8} \epsilon_0 \mu \frac{V^2}{d^3}$$

Where $\epsilon_0$ is vacuum permittivity and $\mu$ is the ion mobility of air ($\approx 1.6 \times 10^{-4} \text{ m}^2/\text{V}\cdot\text{s}$). The net macroscopic thrust force ($\mathbf{F}_{\text{thrust}}$) produced by these accelerated ions colliding with neutral air molecules is directly proportional to total current ($I$) and electrode spacing ($d$):

$$\mathbf{F}_{\text{thrust}} = \frac{I \cdot d}{\mu}$$

### B. Fluid Dynamics & Maxwell's Stress Tensor
To translate this electrical field into a physical force moving the hull, we integrate Maxwell's Stress Tensor ($\mathbf{T}$) over the closed surface area of the sail ($A_{\text{sail}}$):

$$\mathbf{F}_{\text{thrust}} = \oint_{A_{\text{sail}}} \mathbf{T} \cdot d\mathbf{a}$$

Because the system is purely electrostatic ($B=0$), the tensor simplifies to a function of the structured geometric asymmetry of the electric fields ($E_i E_j$). This field introduces an electrostatic body force term ($\mathbf{f}_e$) directly into the Navier-Stokes Fluid Momentum Equation for the air moving across the sail surface:

$$\rho_{\text{air}} \left( \frac{\partial \mathbf{u}}{\partial t} + (\mathbf{u} \cdot \nabla)\mathbf{u} \right) = -\nabla p + \mu_{\text{visc}} \nabla^2 \mathbf{u} + \mathbf{f}_e$$

$$\mathbf{f}_e = \rho_c \mathbf{E} - \frac{1}{2} E^2 \nabla \epsilon$$

Where:
* $\rho_c \mathbf{E}$ = Coulomb force (accelerating the ion cloud)
* $-\frac{1}{2} E^2 \nabla \epsilon$ = Dielectric dielectrophoretic force (activated by variations in the sail's specialized material permittivity $\epsilon$)

### C. Open-System Thermodynamics & System Constraints
The entire vessel behaves as an open thermodynamic control volume ($\mathcal{V}$). The system obeys the First Law of Thermodynamics, balancing all power inputs against kinetic work, storage, and irreversible entropy losses:

$$P_{\text{solar}}(t) + P_{\text{kinetic\_stored}}(t) = P_{\text{ehd\_thrust}}(t) + P_{\text{loads}}(t) + P_{\text{thermal\_losses}}(t) + \frac{dE_{\text{battery}}}{dt}$$

The maximum useful work (Exergy) available from the solar array is governed by the Petela Efficiency limit:

$$\eta_{\text{Petela}} = 1 - \frac{4}{3}\left(\frac{T_0}{T_{\text{sun}}}\right) + \frac{1}{3}\left(\frac{T_0}{T_{\text{sun}}}\right)^4$$

By implementing seamless hydrophobic dielectric encapsulation ($\epsilon_r$), the system enforces rigid boundary conditions ($\nabla \cdot \mathbf{D} = \rho_{\text{free}}$) at the saltwater interface. This drives the electrical leakage term ($P_{\text{thermal\_losses}}$) toward zero, ensuring that excess solar energy is converted directly into forward hydrodynamic velocity rather than being dissipated as waste heat into the sea.
