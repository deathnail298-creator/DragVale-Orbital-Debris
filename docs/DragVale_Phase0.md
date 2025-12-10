DragVale – Phase Zero Architecture Document

Author: Nathan Rudloff
Status: Phase Zero Concept Framework
License: Kaizen Open License (see repository root)

1. Mission Overview
1.1 Purpose

DragVale is a low-cost, low-complexity orbital debris drag system designed around a single host drone deploying an ultra-light “puff-veil” in low Earth orbit. The system introduces minimal drag to the host, while imposing significant drag penalties on passing debris, accelerating natural orbital decay without requiring active targeting, capturing, or rendezvous maneuvers.

This Phase Zero document defines the architecture, constraints, and design logic required for a first-generation demonstrator that small engineering teams, contractors, research labs, or commercial entities can prototype without high-budget aerospace infrastructure.

The goals of Phase Zero:

Define the mission concept and operational logic.

Establish the baseline demonstrator configuration (1 drone, 1 veil).

Provide a buildable architecture with no unnecessary complexity.

Enable Phase One refinement, analytics, and multi-drone scaling.

This is not a flight program specification. It is the skeletal blueprint from which flight programs can branch.

1.2 Mission Objectives

Demonstrate orbital drag enhancement using an ultra-low-mass veil.

Validate survivability of veil material, frame geometry, and deployment method.

Confirm negligible drag impact on the host drone’s orbital lifetime.

Measure statistical drag influence on small debris passing through the veil volume.

Provide a scalable proof-of-concept that can later expand to multi-veil chains.

1.3 Constraints & Design Philosophy

DragVale conforms to the broader Phase-Zero principles:

Simplicity first. Fewer subsystems, fewer failure modes.

No moving parts unless unavoidable.

Low mass, low power, low cost.

Small-team buildability. Must be feasible for a handful of engineers.

COTS-first approach. Use commercial hardware whenever possible.

Fork-friendly architecture. Open design intended for modification and iteration.

This system does not attempt active debris capture, precision interception, or high-thrust maneuvers. It is a passive drag amplifier, not a hunter.

1.4 Phase Zero vs. Phase One

Phase Zero (this document):

Establishes the demonstrator concept.

Specifies single-drone operational geometry.

Defines subsystem roles at the architectural level.

Provides cost estimates and feasibility ranges.

Outlines the necessary performance expectations.

Phase One (future document):

Expands to multi-veil drag chains (3-drone chain).

Adds analytics, orbit determination refinement, and materials validation.

Introduces scalability models for commercial systems.

Defines modular variants (LEO, VLEO, specialty orbits).

1.5 Success Criteria

Phase Zero success is defined by:

The veil successfully deploys to its operational geometry.

The drone maintains stable orbit with no significant lifetime penalty.

The veil remains structurally intact under thermal cycling and micrometeoroid exposure.

Sensor or ODR (orbit determination) data confirms debris-induced drag interactions.

Total system cost remains within projected ranges.

A Phase Zero mission can succeed without direct imaging of debris impacts; orbital decay statistics and veil survivability alone validate the concept.

2. System Requirements

This section defines the non-negotiable requirements for the Phase Zero demonstrator. Requirements are intentionally minimal and avoid unnecessary subsystem entanglement.

2.1 Host Drone Requirements

R1. Mass Ceiling:
The total wet mass of the demonstrator shall not exceed 10 kg (CubeSat-class acceptable).

R2. Power Budget:
The drone shall operate within <10 W average power, with peak loads <25 W including comms.

R3. Attitude Control:
Minimal ACS sufficient to:

Maintain veil alignment

Prevent uncontrolled tumbling

Keep comm antennas oriented for downlink

Reaction wheels optional; magnetorquers sufficient for Phase Zero.

R4. Comms:
Must support periodic downlink of:

Basic telemetry

Veil state

Orbit determination data

No high-bandwidth systems required.

2.2 Puff-Veil Requirements

R5. Veil Area:
Operational deployed area must be ≥ 8–20 m² to ensure meaningful drag amplification.

R6. Veil Mass:
Total veil mass shall not exceed 100–250 g, including support frame.

R7. Deployment Complexity:
Deployment mechanism shall use:

No motors

No hinges

No articulated mechanisms

Acceptable:

Passive inflation

Passive unfurling

Stored-spring tension

Thermal release

R8. Structural Survivability:
Veil must remain intact under:

Thermal cycling (–120°C to +120°C)

Minor micrometeoroid impacts

Solar UV exposure

R9. Drag Impact Differential:
Veil must introduce <3% orbital lifetime reduction to the host but produce ≥20–50% drag influence on debris passing through it (statistical regime).

2.3 Operational Requirements

R10. Orbit:
Phase Zero shall operate in LEO (400–700 km) for accessible atmospheric decay rates.

R11. Deployment:
Veil deployment must be fully autonomous and require no ground intervention.

R12. Mission Duration:
Host drone shall survive ≥ 3 months to accumulate drag interaction statistics.

R13. Safety:
No subsystem may create debris or fragmentation risks.
All components must obey existing LEO mitigation guidelines.

3. Architecture Summary
3.1 System Overview

DragVale consists of two primary subsystems:

Host Drone (HD) – a small, self-contained orbital platform providing power, communications, attitude control, and structural anchoring for the veil.

Puff-Veil Assembly (PVA) – an ultra-light, high-area drag surface deployed behind the host to interact with passing debris while imposing minimal drag on the host itself.

The system operates entirely through passive drag amplification and does not require active targeting, intercept maneuvers, or capture mechanisms. DragVale’s fundamental purpose is to create a localized region of elevated drag in orbit without creating additional hazards or increasing system complexity.

3.2 Host Drone Subsystem

The Host Drone (HD) functions as the operational backbone of the DragVale system. It is responsible for:

Maintaining veil alignment

Providing the necessary structural interface for veil deployment

Performing basic attitude stabilization

Transmitting telemetry to ground stations

Managing power, thermal, and health-status operations

Key Architectural Characteristics

Form Factor: CubeSat-/SmallSat-class bus, 3U–6U scale acceptable.

Attitude Control:

Magnetorquers preferred for simplicity.

Reaction wheels optional but not required for Phase Zero.

Propulsion:

None required for Phase Zero beyond minor housekeeping, if any.

DragVale is not maneuvering-intensive.

Power:

Body-mounted solar panels sufficient.

Low-power avionics consistent with long-duration deployments.

Thermal Management:

Passive thermal design preferred.

No moving radiators or active cooling loops.

The HD is deliberately minimal, serving primarily as a stable platform for the veil rather than a maneuvering spacecraft.

3.3 Puff-Veil Assembly Subsystem

The Puff-Veil Assembly (PVA) is the core functional element of DragVale. It acts as a large, ultra-low-mass surface that debris passes through, resulting in increased atmospheric drag on the debris while the host remains largely unaffected.

Functional Requirements

Large Surface Area:
Nominal deployed area between 8–20 m², depending on material and frame geometry.

Ultra-Low Mass:
The veil must remain orders-of-magnitude lighter than conventional drag sails to avoid imposing a significant drag penalty on the host.

Passive Deployment:
The PVA must be deployable without motors, hinges, or actuators, using:

Stored strain energy

Passive unfurling

Thermal-triggered release mechanisms

Tensioned filaments or memory-fabric geometry

Structural Stability:
Must maintain operational shape without rigid booms or articulated supports.

Material Considerations

The veil material must demonstrate:

High UV resistance

Low areal density

Adequate tear resistance

Survivability under thermal cycling

Predictable drag coefficient in LEO

Candidate materials include ultra-thin polymer films, aerogel mesh composites, or reinforced nanofiber membranes (Phase Zero does not mandate a specific material).

3.4 Deployment Architecture

The PVA deploys behind the host drone relative to orbital velocity. Deployment must:

Occur autonomously once the spacecraft reaches operational orbit

Avoid sudden dynamic loads

Prevent fragment release or partial deployment hazards

Achieve stable geometric shape suitable for drag interaction

Deployment is achieved by packaged-to-expanded transition driven by passive mechanisms. No active separation, explosive bolts, or motorized booms are required for Phase Zero.

3.5 Drag Interaction Mechanism

DragVale operates by creating a zone of increased atmospheric interaction through the veil’s extended, low-density structure.

Host vs. Debris Drag Impact

Host Drone:
Experiences a negligible drag increase (<3% lifetime reduction in typical LEO conditions).

Orbital Debris:
Debris passing through the veil encounters significantly increased drag due to:

Larger effective cross-sectional interaction

Momentum transfer with veil fibers/material

Increased collision probability with high-area, low-mass surfaces

The system relies on natural orbital mechanics to:

Decelerate debris

Lower perigee

Accelerate natural re-entry

No direct energy input or active control is required.

3.6 Survivability Considerations

The architecture is designed to withstand:

Repeated thermal cycles between –120°C and +120°C

UV degradation over multi-month missions

Minor impacts from micrometeoroids

Structural tension loads induced by veil deployment

Long-duration vacuum exposure

DragVale does not attempt to endure catastrophic impacts or fragmentation events; instead, it minimizes risk by avoiding rigid structural members that could generate debris.

3.7 No-Moving-Parts Justification

Minimizing moving parts:

Reduces failure modes

Shortens development cycles

Makes the architecture accessible to small teams

Increases survivability in space environments where lubricants, bearings, and actuators are failure-prone

Simplifies deployment, testing, and manufacturing

DragVale adheres to the principle that simplicity equals resilience.

3.8 Orbital Behavior Summary

During operations, the system exhibits:

Stable veil orientation via host ACS

Passive drag amplification on debris

Minimal perturbations to host attitude and orbit

No requirement for reaction-wheel desaturation burns (if wheels are used)

No requirement for post-deployment maneuvering

DragVale functions as a stationary drag-enhancement node in orbit rather than a mobile interceptor.

4. Subsystem Descriptions

This section defines the major subsystems of the DragVale Phase Zero demonstrator. Each subsystem is described in terms of function, constraints, interfaces, and required behaviors.

4.1 Host Drone (HD)
4.1.1 Function

The Host Drone provides structural support, power, communication, and attitude stabilization for the Puff-Veil Assembly (PVA). It maintains proper veil orientation relative to orbital velocity and ensures the spacecraft remains controllable and communicative throughout the mission.

4.1.2 Constraints

Minimal mass structure (CubeSat-class preferred).

Low average power consumption.

Passive or semi-passive thermal design.

Attitude control sufficient to maintain veil alignment.

4.1.3 Interfaces

Mechanical interface to veil anchoring points.

Electrical interfaces for PVA sensors (optional for Phase Zero).

Power and data pathways for avionics and comms.

4.1.4 Required Behaviors

Maintain stable attitude during and after veil deployment.

Provide continuous low-rate telemetry.

Survive launch loads, deployment sequence, and orbital environment.

Avoid generating debris under any operational condition.

4.2 Puff-Veil Assembly (PVA)
4.2.1 Function

The PVA is the primary functional component responsible for increasing drag on passing debris while imposing minimal drag on the host. It forms an extended, ultra-light, high-area surface trailing behind the HD.

4.2.2 Constraints

Deployed area: 8–20 m² nominal.

Mass: Must remain significantly below 1% of total spacecraft mass to avoid affecting host dynamics.

Deployment: Fully passive, no actuators.

Rigidity: Must maintain operational geometry without rigid booms or articulated structures.

4.2.3 Material Requirements

High UV resistance.

Tolerant of thermal cycling (–120°C to +120°C).

Low areal density.

Tear-resistant under minor debris interactions.

Predictable drag coefficient in LEO.

4.2.4 Required Behaviors

Deploy cleanly and predictably.

Maintain stable orientation relative to orbital ram direction.

Avoid shedding fragments under stress.

Operate as a passive drag enhancement surface throughout mission duration.

4.3 Deployment Mechanism
4.3.1 Function

The deployment mechanism transitions the PVA from its stowed configuration to its operational geometry without active actuation.

4.3.2 Constraints

No motors, hinges, or powered actuators.

Deployment must not generate debris.

Deployment must not impart destabilizing torque onto the host.

Mechanism must be tolerant of launch vibrations and vacuum conditions.

4.3.3 Acceptable Mechanisms

Examples include (but are not limited to):

Stored-strain or memory-material “pop-out” frames

Passive unfurling with tensioned filaments

Thermal-release restraints

Spring-frame expansion with damped rates

4.3.4 Required Behaviors

Deploy autonomously post-orbit insertion.

Achieve correct geometry without ground commands.

Avoid partial or asymmetrical deployment states.

Maintain deployed configuration without active stabilization.

4.4 Attitude Control System (ACS)
4.4.1 Function

ACS maintains the correct orientation of the HD/PVA system to ensure the veil trails correctly behind the host and remains aligned with orbital velocity.

4.4.2 Constraints

Low power requirements.

Minimal moving components.

Magnetorquer-based control acceptable as sole attitude actuator.

4.4.3 Required Behaviors

Compensate for minor torques induced by veil drag.

Maintain pointing stability for comms and orientation.

Avoid uncontrolled tumbling during or after deployment.

Operate continuously throughout the mission with minimal intervention.

4.5 Power Subsystem
4.5.1 Function

Provides electrical power to avionics, ACS, comms, and onboard sensors (if any).

4.5.2 Architecture

Body-mounted solar panels for generation.

Small battery pack for eclipse operations.

Simple power regulation and distribution.

4.5.3 Required Behaviors

Support continuous low-power loads.

Maintain sufficient charge during eclipse.

Provide stable power during deployment sequence.

Avoid thermal runaway or over-discharge conditions.

4.6 Communications Subsystem
4.6.1 Function

Transmit telemetry, health, and orbit data to ground operators.

4.6.2 Constraints

Low-bandwidth link acceptable.

Omnidirectional or wide-beam antenna preferred.

Minimal pointing requirements.

4.6.3 Required Behaviors

Periodically downlink basic telemetry.

Provide veil-deployment confirmation data (sensor or attitude-based).

Support end-of-life reporting.

4.7 Thermal Control Subsystem
4.7.1 Function

Maintain component temperatures within allowable operating ranges.

4.7.2 Architecture

Passive thermal design preferred.

Use of coatings, insulation, and radiative balancing.

4.7.3 Required Behaviors

Prevent overheating of avionics.

Ensure veil materials remain structurally stable across thermal cycles.

Avoid thermal gradients that could torque the veil or induce structural misalignment.

4.8 Structural Subsystem
4.8.1 Function

Provide mechanical integrity, attachment points, and vibration survivability for launch and deployment.

4.8.2 Required Behaviors

Survive launch loads without deformation.

Maintain veil anchoring without creep or fatigue.

Ensure mass distribution does not induce ACS instability.

Avoid sharp edges or failure modes that could generate foreign object debris.

5. Operational Concept

This section defines the mission flow, operational phases, expected behaviors in orbit, and the passive logic governing DragVale’s performance. The operational concept is intentionally simple to reduce failure modes and enable small-team implementation.

5.1 Mission Phases Overview

DragVale operates through the following sequential phases:

Launch & Ascent

Orbital Injection

Initialization & Checkout

Autonomous Veil Deployment

Operational Drag Phase

Monitoring & Telemetry

Degradation & End-of-Life

Each phase is described below.

5.2 Phase 1 – Launch & Ascent
Objective

Deliver the Host Drone (HD) to its planned rideshare deployment orbit.

Expected Behavior

HD remains stowed in its standardized deployer or launch mount.

PVA is secured by passive restraints with no chance of premature release.

All electrical systems remain unpowered, except for the deployment inhibit hardware required by launch provider specifications.

No operations occur in this phase.

5.3 Phase 2 – Orbital Injection
Objective

Enter the designated mission orbit (typically 400–700 km LEO).

Expected Behavior

HD separates from the deployer using a standard CubeSat rail or clamp-band mechanism.

HD executes initial detumble, if required, using magnetorquers.

Deployment inhibits remain active until system health is confirmed.

The HD transitions into a stable attitude before any further actions occur.

5.4 Phase 3 – Initialization & Checkout
Objective

Verify system functionality prior to veil deployment.

Steps

Boot onboard avionics.

Verify power system health (solar input, battery status).

Confirm thermal limits.

Establish first communications link with ground.

Verify ACS functionality (magnetorquer authority, attitude solution).

Execute small attitude slews to confirm stability.

Deployment will not proceed if critical health checks fail.

5.5 Phase 4 – Autonomous Veil Deployment
Objective

Transition the Puff-Veil Assembly (PVA) from stowed configuration to operational geometry.

Trigger Conditions

Deployment begins when all the following are true:

Deployment inhibits lifted by internal logic.

HD is stable and detumbled.

Solar charging nominal.

Temporary ground-command inhibit (if included) cleared.

Deployment Behavior

Passive release mechanism activates (thermal release, tensioned filament, memory-material frame, etc.).

PVA unfurls or expands to full operational shape.

Momentum from deployment is absorbed through HD’s ACS.

Post-Deployment Settling

The system will:

Stabilize attitude with magnetorquers.

Confirm deployment via telemetry (geometry, ACS load signatures).

Enter operational mode.

No ground intervention needed.

5.6 Phase 5 – Operational Drag Phase
Objective

Perform the primary mission: increase drag on passing debris while maintaining stable host orbit.

Behavior Characteristics

PVA trails behind the HD relative to orbital ram direction.

HD maintains attitude with minimal ACS effort.

The veil induces negligible additional drag on the HD.

Debris passing through or interacting with the veil experiences increased deceleration.

Data Products

Attitude logs

Orbital decay measurements

Thermal behavior

Structural stability indications

Deployment health metrics

Optional PVA strain/load sensor data (not required for Phase Zero)

Autonomy Model

The system does not:

Track debris

Maneuver to intercept

Modify its orbit

It acts purely as a stationary drag-enhancement node.

5.7 Phase 6 – Monitoring & Telemetry
Objective

Provide periodic updates to evaluate mission health and performance.

Expected Telemetry

Battery voltage, charge rate, solar input

ACS torque commands and performance

Temperature readings

Deployment state confirmation

Position and orbit determination solutions

General health and fault flags

Data rate is intentionally low to reduce system complexity.

5.8 Phase 7 – Degradation & End-of-Life (EOL)
Objective

Ensure safe termination of mission without generating debris or uncontrolled behavior.

Natural Degradation Behavior

Veil slowly degrades under UV exposure and thermal cycling.

HD experiences slow orbital decay consistent with its ballistic coefficient.

System continues transmitting until power or comms degrade beyond operational thresholds.

EOL Requirements

System must not shed hazardous fragments.

System must comply with standard LEO orbital decay guidelines (typically <25 years).

No active disposal mechanism required due to low mass and passive decay behavior.

5.9 Failure Modes (High-Level)

DragVale is designed to fail safely. The primary failure modes are:

(1) Non-Deployment of Veil

System continues as a passive CubeSat.

No additional debris risk.

Mission fails gracefully without hazards.

(2) Partial or Asymmetric Deployment

ACS maintains stability to the extent feasible.

Drag remains minimal.

Mission likely degraded but safe.

(3) ACS Failure Post-Deployment

Veil may tumble with host.

System will naturally decay without hazard due to low mass and flexible structures.

(4) Communications Loss

Mission can continue without ground interaction.

No active systems require intervention.

All failure states default to passive safety.

6. Safety & Risk Profile

This section outlines the safety rationale, expected risk behaviors, and mitigation strategies at the architectural level. DragVale is designed to operate as a low-mass, low-energy, passive system that minimizes the creation of hazards in all mission scenarios.

6.1 Safety Philosophy

DragVale adheres to three core safety principles:

No new debris.
The system must not generate debris during launch, deployment, operations, or end-of-life.

Passive-safe failure modes.
Any subsystem failure must default to a benign configuration that does not endanger other spacecraft or orbital operations.

Low stored energy.
The architecture avoids high-tension structures, explosive actuators, pressurized vessels, and moving mechanical components.

These principles ensure the system remains compliant with current and anticipated LEO debris-mitigation standards.

6.2 Fragmentation Avoidance

Fragmentation risk is addressed structurally and operationally:

Ultra-low-mass veil:
The PVA consists of thin films or mesh materials that cannot meaningfully fragment into hazardous debris.

No rigid booms or articulations:
Eliminates failure-induced shattering or hinge breakage.

Damped deployment:
Passive expansion mechanisms prevent high-velocity material release.

Minimal stored strain energy:
Memory-material elements or spring frames are designed to operate well below energetic thresholds.

No pyrotechnics or pressurized systems:
Removes the primary fragmentation vectors typical in conventional space deployments.

6.3 Deployment Safety

Deployment is a critical safety phase. DragVale reduces deployment risk through:

Passive mechanisms:
No motors or actuators that can jam or misfire.

Slow kinematic transitions:
Ensures no unintended forces are imparted to the host or detached components.

Internal damping:
Prevents oscillations that could destabilize the host or cause structural strain.

Redundant inhibit logic:
Deployment only initiates after detumble, power stabilization, and basic health checks.

Even in a partial deployment scenario, structural and aerodynamic behavior remains benign.

6.4 Operational Safety

During operations, DragVale exhibits the following safety characteristics:

Low ballistic coefficient of veil:
Any detached veil segment (unlikely) would deorbit rapidly.

Minimal drag impact on host:
Prevents accidental reentry acceleration.

Low-cross-section host bus:
Reduces collision probability with tracked debris or satellites.

No intercept attempts:
The system does not maneuver to chase debris; all interactions are incidental and non-energetic.

Stable trailing orientation:
ACS maintains alignment, preventing the veil from pitching or flapping unpredictably.

Operationally, DragVale functions as a passive orbital node with predictable dynamics.

6.5 Environmental Compatibility

The system is designed to survive without contributing new hazards in the following environments:

Thermal cycling:
PVA materials are rated for high-cycle durability, minimizing tear or fold failures.

Micrometeoroid environment:
Veil can tolerate perforations without catastrophic tearing due to low-stress tensioning.

Solar UV exposure:
Material degradation over time does not cause fragmentation; veil gradually weakens but remains coherent.

Atomic oxygen (AO):
Material selection ensures slow, predictable erosion without flaking or hazardous shedding.

6.6 End-of-Life Safety

DragVale’s end-of-life (EOL) behavior is inherently safe:

Natural deceleration:
Both host and veil decay passively with no intervention required.

No propellant:
Eliminates risk of tank rupture or residual thrust events.

No high-energy components:
Batteries are small and thermally stable.

Compliance with standard LEO disposal guidelines:
Designed to meet the <25-year decay rule.

Graceful failure:
Regardless of veil condition at EOL, nothing in the system becomes a fragmentation hazard.

6.7 Risk Classification (Phase Zero)

DragVale falls within a low-to-moderate risk class for small spacecraft, characterized by:

Low collision risk due to minimal cross-sectional mass.

Low fragmentation risk due to absence of energetics.

Low operational risk because no maneuvers or dynamic operations occur.

Moderate deployment risk (common to all deployables), mitigated through passive design.

Low end-of-life risk due to natural decay compliance.

This makes DragVale suitable for rideshare launch opportunities and for operation in common LEO bands without imposing significant hazard burdens on other space assets.

7. System Diagrams (ACS2 Architecture)

This section defines the DragVale Phase Zero system using a text-mode ACS2 diagram. ACS2 (Architecture Control Structure – Level 2) provides a clear representation of subsystem nodes, information flow, structural linkages, and operational relationships without requiring graphical schematics.

The diagram below is canonical for the Phase Zero demonstrator (single host drone, single veil).

7.1 ACS2 Node Definitions

HOST_DRONE – Primary spacecraft bus; provides power, comms, ACS, and structural interface.
ADCS – Attitude Determination and Control Subsystem (magnetorquers + sensors).
PWR – Power subsystem (solar arrays + battery + regulation).
COMMS – Communications subsystem (radio, antenna, RF front-end).
THERM – Thermal regulation subsystem (passive coatings, insulation).
AVIONICS – OBC, sensor interfaces, deployment logic.
DEPLOY_UNIT – Passive veil deployment mechanism.
PVA_FRAME – Structural tension frame or edge support for veil geometry.
PVA_MESH – Ultra-light veil material providing drag enhancement.
DEPLOY_INHIBIT – Logic and physical restraints preventing premature deployment.
SENSORS – Minimal sensor suite (IMU, temperature sensors, sun sensor); optional strain sensing on PVA.
GND_LINK – Ground communication pathway.

7.2 ACS2 Edges (Relationships & Flows)

Edges define the structural and functional relationships:

HOST_DRONE ↔ ADCS
Orientation commands and sensor feedback loop.

HOST_DRONE ↔ PWR
Power distribution to all subsystems.

HOST_DRONE ↔ COMMS
Telemetry uplink and command downlink path.

HOST_DRONE ↔ THERM
Passive thermal interaction; no active control.

HOST_DRONE ↔ AVIONICS
Data handling, deployment logic, health monitoring.

AVIONICS → DEPLOY_INHIBIT
Inhibit release triggered only after initialization and detumble.

DEPLOY_INHIBIT → DEPLOY_UNIT
Physical release path for passive deployment.

DEPLOY_UNIT → PVA_FRAME
Controlled extension or unfurling of structural frame.

PVA_FRAME → PVA_MESH
Provides tensioning and operational geometry to the veil material.

PVA_MESH ↔ ORBIT_ENV
Primary functional interaction — drag enhancement on debris.

ADCS ↔ PVA_FRAME
Attitude stabilization compensates for drag-induced torque.

SENSORS → AVIONICS
Telemetry data for health monitoring, deployment confirmation.

AVIONICS → GND_LINK → GROUND
Health/status transmission.

7.3 ACS2 System Topology (Text Diagram)

Below is the full ACS2 representation.
This is the canonical topology for DragVale Phase Zero.

NODES:
  HOST_DRONE
  ADCS
  PWR
  COMMS
  THERM
  AVIONICS
  SENSORS
  DEPLOY_INHIBIT
  DEPLOY_UNIT
  PVA_FRAME
  PVA_MESH
  ORBIT_ENV
  GND_LINK
  GROUND

EDGES:
  HOST_DRONE → ADCS
  ADCS → HOST_DRONE

  HOST_DRONE → PWR
  PWR → HOST_DRONE

  HOST_DRONE → COMMS
  COMMS → HOST_DRONE

  HOST_DRONE → THERM
  THERM → HOST_DRONE   (passive influence)

  HOST_DRONE → AVIONICS
  AVIONICS → HOST_DRONE

  AVIONICS → DEPLOY_INHIBIT
  DEPLOY_INHIBIT → DEPLOY_UNIT

  DEPLOY_UNIT → PVA_FRAME
  PVA_FRAME → PVA_MESH

  PVA_MESH → ORBIT_ENV
  ORBIT_ENV → PVA_MESH

  ADCS → PVA_FRAME        (attitude stabilization)
  PVA_FRAME → ADCS        (drag torque feedback)

  SENSORS → AVIONICS
  AVIONICS → GND_LINK
  GND_LINK → GROUND

7.4 Topology Interpretation
Structural Chain

HOST_DRONE → DEPLOY_UNIT → PVA_FRAME → PVA_MESH

Control Chain

SENSORS → AVIONICS → ADCS → HOST_DRONE attitude response

Mission Interaction Chain

PVA_MESH ↔ ORBIT_ENV → debris drag effects → passive system response

Communications Chain

AVIONICS → GND_LINK → GROUND (telemetry only; no maneuvering commands required)

7.5 Notes on ACS2 Constraints

ACS2 explicitly avoids specifying geometry or physical dimension; Phase Zero restricts itself to functional relationships.

No subsystem has authority to induce propulsion or maneuvering.

PVA_MESH is modeled solely as an orbital interaction node with no actuation.

ADCS handles all drag-induced perturbations, but Phase Zero design keeps these forces minimal.

DEPLOY_UNIT is a one-way transition node; no retraction path exists.

8. Materials, Lifetimes, and Survivability

This section defines the material expectations, environmental tolerances, and survivability requirements for DragVale’s Phase Zero demonstrator. The system is intentionally low-mass and low-stiffness, requiring careful selection of materials that can survive the orbital environment without contributing to debris generation or structural instability.

8.1 Material Selection Philosophy

Material choices for DragVale prioritize:

Low areal density
Ensures minimal drag impact on the host and safe degradation behavior.

Environmental resilience
Must remain functional under temperature extremes, UV exposure, atomic oxygen, and micrometeoroids.

Controlled degradation
Materials should weaken predictably over time without fragmenting or shedding debris.

Manufacturability
Accessible to small-team fabrication using standard film-handling and tensioning techniques.

Non-hazardous failure modes
No brittle fracturing, splintering, or delamination that could generate orbital debris.

8.2 Puff-Veil Material Requirements

The PVA (Puff-Veil Assembly) material is the key performance driver of DragVale. It must satisfy the following Phase Zero criteria:

8.2.1 Areal Density

Target range: 0.1–1.0 g/m²

Ultra-light to ensure:

Negligible drag influence on host

Rapid deorbit of veil fragments if damaged

Low launch mass

8.2.2 Mechanical Properties

Must tolerate minor tears without propagating (anti-run characteristics).

Must maintain tension without rigid supports.

Must not deform plastically under nominal thermal loading.

8.2.3 Thermal Endurance

Operable range: –120°C to +120°C

Expected to undergo several thousand thermal cycles over mission life.

8.2.4 UV & Atomic Oxygen Resistance

Material shall:

Resist embrittlement under extreme UV exposure.

Exhibit predictable, slow AO erosion without surface flaking.

Candidate classes include:

Polyimide films (AO-resistant coatings recommended)

Nano-fiber mesh composites

Aerogel-supported ultra-thin membranes

Metallized polymer micro-films (with protective overcoats)

Phase Zero does not mandate a single material; selection is left to implementing teams.

8.3 PVA Frame and Edge Support Materials

While the system avoids rigid booms, the veil may require:

Elastic frame edges

Tension filaments

Memory-material perimeter elements

Material expectations:

Low-modulus, fatigue-resistant polymers or composite fibers

No metallic hinges, deployment arms, or telescoping structures

Memory materials must store limited strain energy to avoid dynamic release events

Must survive launch vibrations without micro-cracking or creep

These components must degrade slower than the veil material to avoid early structural collapse.

8.4 Host Drone Material Requirements
8.4.1 Structure

HD structure may use standard CubeSat materials:

Aluminum alloys (e.g., 6061, 7075)

Composite panels (aluminum honeycomb, CFRP skins)

Non-fragmenting polymers for brackets and restraints

8.4.2 Environmental Endurance

Structural and surface materials must withstand:

Vibration loads during launch

LEO thermal environment

Atomic oxygen exposure

UV radiation

Micrometeoroid flux (low incidence)

8.4.3 Thermal Considerations

Coatings and surface finishes must prevent uncontrolled heat absorption.

No reliance on active cooling loops in Phase Zero.

Solar-panel adhesives and encapsulants must resist UV-induced delamination.

8.5 Mission Lifetime Expectations
8.5.1 Veil Operational Lifetime

Nominal operational lifetime: 3–12 months

PVA is expected to gradually degrade and lose structural integrity due to environmental stressors.

Full-lifetime survivability is not required for mission success; statistical drag enhancement early in the mission provides principal value.

8.5.2 Host Drone Lifetime

Expected operational lifetime: 6–24 months, depending on orbit, power generation, and component aging.

Extended host lifetime does not guarantee veil survivability.

8.5.3 End-of-Life Decay

Both veil and host will naturally deorbit following structural degradation and orbital decay.

No intervention required.

8.6 Survivability Against Impact Events
8.6.1 Micrometeoroid and Debris Impacts

PVA is designed to tolerate perforations without catastrophic tearing.

Frame elements must prevent tear propagation.

HD structure will follow standard CubeSat impact survivability expectations.

8.6.2 Drag-Induced Stress Loads

PVA experiences low dynamic pressure in LEO, but must tolerate:

Fluctuating drag forces due to density variations

Minor tension asymmetries

HD must absorb torque disturbances via ADCS.

8.7 Degradation and Failure Behavior

The system must degrade in a controlled, predictable manner:

Veil material thinning and tearing occurs gradually.

Structural edges may lose tension without catastrophic snap.

Entire assembly remains low-mass even after significant material loss.

No component failure mode shall generate rigid, fast-moving fragments.

The degradation pathway is part of the design philosophy—safe, natural decline rather than active disposal.

8.8 Material Qualification Guidelines (Phase Zero)

Phase Zero does not require exhaustive flight qualification, but materials should undergo:

Thermal vacuum cycling

UV exposure testing

AO exposure approximation (plasma chamber recommended)

Mechanical tension and tear propagation tests

Deployment-repeatability testing (for frame elements)

9. Performance Expectations

This section defines the anticipated performance characteristics of the DragVale Phase Zero demonstrator. Values are expressed as qualitative expectations and relative behaviors, not mission-specific numerical guarantees. Numerical performance will depend on veil material, deployed area, orbital altitude, local atmospheric density, and debris encounter geometry.

The Phase Zero objective is to establish performance envelopes and expected qualitative outcomes, enabling implementers to derive quantitative models appropriate for their material and orbit choices.

9.1 Performance Philosophy

DragVale’s performance hinges on one underlying goal:

Increase debris drag meaningfully while limiting drag penalty on the host.

This differential performance dictates the architecture:

Ultra-light, high-area veil

Low-mass host

Passive interaction model

Stationary drag-enhancement role

The system is not optimized for hunting debris; it is optimized for being in the right place long enough to matter.

9.2 Drag Amplification Effect

The Puff-Veil Assembly (PVA) creates a localized region of enhanced drag due to its:

High surface area

Low mass

Permeable or semi-permeable structure

Long interaction path length relative to small debris cross-sections

Expected behavior:

Debris passing through or interacting with the veil experiences increased aerodynamic drag relative to the unmodified orbital environment. This drag enhancement is expected to:

Reduce debris velocity in the along-track direction

Lower debris perigee incrementally

Accelerate natural orbital decay over repeated passes

Drag amplification magnitude depends on veil area, material coefficient of drag, and orbital density but is expected to be non-trivial compared to background drag.

9.3 Host vs. Debris Drag Differential

The system is designed so the host drone and passing debris experience significantly different ballistic impacts:

Host Drone:

Very small cross-sectional area compared to veil

Much higher mass-to-area ratio

PVA contributes trivial aerodynamic load on the host

Attitude control counters minor torque disturbances

Expected Result:
Negligible reduction in host orbital lifetime.

Debris:

Often irregularly shaped with moderate ballistic coefficients

Passes directly through or across veil material

Experiences enhanced drag forces that compound over multiple encounters

Expected Result:
Meaningful contribution to debris orbit decay over time.

This differential is the core operational principle.

9.4 Encounter Dynamics
9.4.1 Interaction Probability

The veil’s operational area increases the probability of debris intersection relative to the host alone. Over mission lifetime, debris encounters occur as a statistical process, influenced by:

Orbital inclination alignment

Debris density in the orbital shell

Relative phasing and conjunction frequency

Veil orientation relative to ram direction

DragVale does not perform active targeting. All interactions are incidental.

9.4.2 Interaction Mechanisms

Debris experiences enhanced drag through:

Direct veil impact (dominant mechanism)

Partial penetration of veil region causing drag coupling

Contact with tension fibers or mesh nodes

Momentum transfer effects from veil deformation

Even incomplete interactions yield measurable effects over sufficient mission duration.

9.5 Host Orbital Behavior
Expected Host Performance

Stable orientation maintained by ADCS

Minor torque loading from veil drag

No requirement for propulsion or orbit maintenance

Slow, predictable decay consistent with host ballistic coefficient

The host orbit remains largely unchanged relative to a non-veil CubeSat.

9.6 Veil Stability and Aerodynamic Behavior

The veil is expected to:

Trail consistently behind the host along velocity vector

Maintain quasi-steady shape due to tension and atmospheric flow

Exhibit low-frequency oscillations under density variations

Self-damp oscillations due to material compliance

Impose very small reaction torques on the host

Veil stability is a key component of predictable drag behavior.

9.7 Mission Effectiveness Envelope

DragVale performance depends on orbital altitude:

Lower LEO (350–450 km)

Highest atmospheric density

Most effective drag amplification

Shorter operational life due to faster orbital decay

Optimal for testing veil material behavior

Mid-LEO (450–600 km)

Balanced operational lifetime

Strong drag amplification effects

Suitable for long-duration missions

Upper LEO (600–800+ km)

Reduced atmospheric density

Drag amplification still present but lower

Longer host lifetime

Suitable for multi-year veil behavior assessment

Phase Zero recommends 400–700 km for meaningful performance demonstration.

9.8 Survivability vs. Performance

A veil that survives longer produces more cumulative drag interactions. Expected behavior:

Gradual thinning or loss of tension reduces drag effectiveness

Partial veil loss still provides residual drag amplification

Host drone remains fully functional with degraded veil

Mission is considered complete once veil loses stable geometry

Survivability is mission-enabling but not mission-critical.

9.9 Expected Mission Outcomes (Phase Zero)

Implementers should expect:

Successful veil deployment and stable orientation

Sustained drag-enhancement behavior over months

Measurable orbital decay acceleration on small debris populations

Minimal host orbital lifetime penalty

Predictable, safe material degradation

No debris generation under nominal or degraded operation

DragVale is a persistent drag node, not a single-event mechanism. Effectiveness grows with dwell time.

10. Limitations & Open Engineering Questions

This section identifies the known limitations of the DragVale Phase Zero architecture and the open questions that are outside the scope of the current concept definition. These items do not represent flaws; they are areas requiring further study, simulation, material testing, or subsystem refinement during Phase One or beyond.

10.1 Architectural Limitations
10.1.1 Passive-Only Interaction

DragVale does not pursue or intercept debris.
It relies entirely on incidental conjunctions within a fixed orbital shell.
This inherently limits:

Encounter frequency

Debris size classes affected

Predictability of mission yield

10.1.2 No Maneuver Authority

Without propulsion, the host cannot:

Adjust altitude

Change inclination

Avoid drag-inhibiting density troughs

Optimize for debris concentration regions

Mission effectiveness depends on initial orbital placement.

10.1.3 Veil Degradation

The veil is expected to degrade over time due to:

UV exposure

Atomic oxygen erosion

Micrometeoroid perforation

Thermal cycling fatigue

As degradation increases, drag amplification decreases.
Mission lifetime is therefore bounded by veil survivability, not host endurance.

10.1.4 Limited Mechanical Stiffness

The veil has no rigid booms or support arms.
This choice improves safety but limits:

Precise geometric control

High-fidelity drag shaping

Aerodynamic predictability under extreme density variations

10.1.5 Statistical Performance

DragVale’s effectiveness is inherently statistical.
Performance cannot be guaranteed for specific debris pieces; only population-level effects can be expected.

10.2 Environmental Limitations
10.2.1 Low-Density Upper LEO

At altitudes above ~700–800 km, atmospheric density declines sharply.
Drag amplification still occurs but produces smaller net effects.

10.2.2 Solar Cycle Sensitivity

Atmospheric density varies with solar flux.
During low activity periods, drag effects diminish.
During high activity periods, veil loads increase.

10.2.3 Unpredictable Density Variation

Short-timescale density fluctuations can influence:

Veil tension

Oscillation behavior

ACS control load

Veil deformation

These variations complicate precise modeling.

10.3 Operational Limitations
10.3.1 No On-Orbit Maintenance

The system cannot be repaired or adjusted once deployed.

10.3.2 Telemetry Constraints

Low-bandwidth downlink restricts:

High-resolution structural monitoring

Real-time oscillation tracking

Detailed debris-interaction logging

10.3.3 ACS Workload Boundaries

While veil-induced torques are expected to be small, extreme density spikes or partial-tear asymmetries may:

Increase ACS duty cycle

Affect attitude stability

Shorten host operational lifetime

10.3.4 No Deorbit Control

EOL is purely natural decay.
This is acceptable for low-mass systems but limits mission timing control.

10.4 Open Engineering Questions

These items require Phase One study, material testing, or simulation.

10.4.1 Optimal Veil Material

Open questions include:

Best trade-off between AO resistance and areal density

Effect of micro-mesh vs. solid-film architectures

Tear propagation dynamics under impact

Manufacturing tolerances for ultra-thin veils

10.4.2 Deployment Geometry

Areas requiring refinement:

Circular vs. fan-shaped vs. ribbon geometries

Tension distribution patterns for stability

Memory-material perimeter performance

Deployment rate optimization to avoid host torque spikes

10.4.3 Drag Modeling Validation

Key unknowns:

Effective drag coefficient of permeable veil surfaces

Impact of oscillation modes on drag consistency

Interaction between mesh porosity and atmospheric flow

Drag coupling between veil and debris of varying sizes

10.4.4 Multi-Veil Scaling

Phase Zero only defines a single-veil system.
Open questions for future phases:

Spacing between multiple nodes

Chain performance as a statistical drag “corridor”

Interaction between sequential veils

Optimal altitude for multi-node efficacy

10.4.5 Structural Dynamics

Need further analysis for:

Veil flutter modes

Coupled HD–PVA oscillations

Long-term tension degradation

Asymmetric tear impacts on ACS load

10.4.6 Real Debris Population Impact

Requires Phase One modeling:

Probabilistic encounter rates

Predicted decay acceleration across debris size bins

Comparative benefit vs. baseline atmospheric drag

Aggregate effect on specific orbital shells over multi-year deployment

10.5 Summary of Limitations

DragVale’s simplicity is its strength, but it comes with:

Passive-only operation

Statistical effectiveness

Material-driven lifetime bounds

Environmental sensitivity

No maneuvering authority

These limitations are acceptable for Phase Zero and serve to make the system buildable, not perfect. Engineering teams engaging in Phase One can refine, extend, or augment these aspects based on mission needs.
