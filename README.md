# DragVale – Phase Zero Orbital Debris Drag System

Possible NASA SBIR: This Phase Zero architecture could be applied to NASA SBIR topics related to orbital debris mitigation and passive drag-enhancement systems, particularly those focused on low-mass, non-propulsive deorbiting technologies.

Estimated Costs

Development (Phase 1 → flight-ready):
≈ $0.5M – $1.0M
This includes subsystem engineering, veil development, CubeSat bus integration, prototyping, ground testing, regulatory filings, and program overhead.

Production (per operational unit):
≈ $130k – $280k
This includes hardware, structure, avionics, veil assembly, and integration/testing.

These ranges reflect small-team, low-complexity design assumptions consistent with Phase Zero philosophy. Major aerospace primes would cost an order of magnitude more, but this architecture is intentionally designed to be built by a lean team using commercial hardware.

**Status:** Phase Zero concept framework  
**Author:** Nathan Rudloff  
**License:** See `LICENSE` (Kaizen Open License)

---

## 1. What is DragVale?

DragVale is a **simple, low-mass orbital debris drag system** built around:

- A small **host drone** in low Earth orbit.
- An ultra-thin, **puff-veil** of material deployed behind the drone.
- A design philosophy of **minimal complexity**, **no moving parts where possible**, and **garage-buildable prototypes**.

The veil adds **almost no meaningful drag** to the drone itself, but it presents a **large, ultra-low-mass surface** that debris can pass through. Debris gets slowed; the drone basically doesn’t care.

---

## 2. Problem Statement

Small, untracked debris is hard to remove:

- Objects are too small to justify big, complex capture systems.
- Many proposed solutions require **precision mechanisms**, **active targeting**, or **insane budgets**.
- Most don’t scale down to “a small team with a modest launch” reality.

DragVale targets the **“annoying but dangerous”** regime: debris that’s big enough to hurt hardware, but small enough that nobody wants to build a billion-dollar system just to grab it.

---

## 3. Phase Zero Scope (This Repository)

This repo is **Phase Zero** only. It does **not** pretend to be a finished flight design. It gives:

- A **clean, readable architecture** for a one-drone, one-veil demonstrator.
- Enough structure that real engineers can fork it and fill in:
  - Detailed materials and mass budgets  
  - Attitude/orbit control specifics  
  - Flight software and GNC details  
- A licensing model that keeps the ideas open while allowing commercial use under defined terms.

**Canonical Phase Zero demonstrator:**

- **1× host drone**
- **1× puff-veil**
- Single low-Earth orbit.
- Focus on: “Can this be built cheaply and tested in the real world?”

---

## 4. Architecture Overview (High Level)

**Host Drone**

- Small satellite bus in LEO.
- Provides:
  - Orbit insertion and basic station-keeping
  - Power, comms, and minimal on-board control
- Designed to be **replaceable**, not sacred.

**Puff-Veil**

- Ultra-light, high-area material deployed behind the drone.
- Behaves like a **drag curtain**:
  - The drone sees **tiny additional drag**.
  - Passing debris sees **meaningful drag** and loses velocity.
- Intentional design: **low cost to the operator, high drag penalty to debris**.

**Operational Concept (Phase Zero)**

1. Launch and insert the DragVale drone into the target orbit.
2. Deploy the puff-veil to its operational geometry.
3. Maintain basic orbit and attitude; let debris intersect the veil over time.
4. Monitor orbital decay effects statistically over the mission.

No harpoons, nets, thrusters on sticks, or Gundam arms. Just a drone and a smart piece of fabric.

---

## 5. Scaling Beyond Phase Zero

The **production-grade** deployment (documented in Phase 1 later) is:

- A **three-drone chain** along the same orbit.
- Three sequential puff-veils.
- Debris passes veil #1 → slowed.  
  Passes veil #2 → slowed more.  
  Passes veil #3 → pushed deep into natural decay.

However:

- **Phase 0 and this repo focus on the single-drone, single-veil demonstrator.**
- Multi-drone chains are treated as **scaling options**, not prerequisites.

This keeps the barrier to entry low enough that small teams can prototype it.

---

## 6. Design Philosophy

DragVale follows the same general rules as my other Phase Zero projects:

- **Simplicity first.** If a mechanism can be removed or made passive, it should be.
- **No moving parts where possible.** Fewer things to seize, jam, or freeze.
- **Buildable by small teams.** A handful of competent engineers with a modest budget should be able to make a prototype.
- **Fork-friendly.** This repo is meant to be cloned, modified, and improved.

If you’re looking for polished vendor CAD, you’re early.  
If you’re looking for a starting point you can actually build from, you’re in the right place.

---

## 7. Repository Layout

Planned structure:

- `README.md` – You are here. High-level overview and orientation.
- `LICENSE` – Kaizen Open License terms governing use and commercialization.
- `docs/DragVale_Phase0.md` – Phase Zero design document (architecture, modes, ACS2 diagrams, etc.).
- `docs/DragVale_Phase1.md` – Phase One scaling & deployment notes (three-drone chain, multi-veil networks).
- `figures/` – ACS2 diagrams and schematics.
- `notes/` – Non-canonical scratch notes and experiments.

---

## 8. How to Use This Repo

- **Engineers / contractors:** Treat this as a **concept skeleton**. Fork it, run your own numbers, and replace all the hand-wavy bits with actual analysis and hardware.
- **Academics:** Use it as a baseline architecture in papers or student projects, and attack it with simulations and models.
- **Space raccoons:** Clone away. Just read the license before you start selling satellites.

Pull requests, forks, and serious criticism are all welcome.
# DragVale-Orbital-Debris
