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

Section 4 Complete

Next up is Section 5 – Operational Concept, which defines:

Mission phases

Deployment timeline

On-orbit behavior

Failure modes and safeties

End-of-life logic
