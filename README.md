This is a prototype of an automated marine microgrid integrating solar overcharge driven electrohydrodynamic thrust with hydro-regenerative battery balancing.

**System Overview**

This project presents a novel solid-state marine vessel architecture that synthesizes advanced microgrid power routing with frontier atmospheric plasma dynamics. The system eliminates traditional mechanical propulsion vulnerabilities like friction, transmission loss and propeller cavitation by utilizing a fully insulated, asymmetric electrohydrodynamic sail as a dynamic energy buffer.

The Battery Management System acts as a central closed-loop logic gate switching the vessel through three discrete thermodynamic states.

**Mode 1: Solar Overcharge Shunt Max Drive Trigger**

Battery pack reaches peak capacity $\text{SoC} \ge \text{SoC}_{\text{high}}$ and cannot accept more current. The BMS completely disconnects the solar-to-battery charging circuit to prevent thermal runaway; it closes the circuit feeding the high-voltage step-up stage routing the excess solar exergy to the asymmetric sail. The resulting ionic wind drives the ship forward converting excess electrical potential into kinetic work.

**Mode 2: Nominal Solar Harvest Cruising Trigger** 

Solar arrays are operating under standard daylight and batteries are in a safe charging window $`\text{SoC}_{\text{low}} < \text{SoC} < \text{SoC}_{\text{high}}`$. The EHD sail is throttled down or turned off. The solar array is routed purely to the battery pack to saturate the chemical energy pool. The hydro-generators remain retracted or locked in a passive minimum-drag configuration.

**Mode 3: Hydro-Regeneration Energy Recovery Trigger**

The BMS tracks a sudden negative power derivative from the solar array $$`\frac{dI_{\text{solar}}}{dt} < \text{Threshold}_{\text{drop}}`$$
due to cloud cover. The EHD sail is fully deactivated. The BMS commands a deployment system to drop the water turbine into the flow or activates the regeneration circuit on a hull-integrated unit. The ship's forward kinetic momentum $`M_{\text{ship}} \cdot v`$
drives the water past the generator, spinning the rotor to produce AC power. 
This AC passes through an onboard rectifier, converting it back to clean DC to replenish the batteries.
