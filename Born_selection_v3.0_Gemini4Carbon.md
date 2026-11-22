# Real-Wave Surface Interference, First-Passage Quantum Tunneling, and Irreversible Solid-State Cascades: A Mechanistic Single-Event Replacement for the Born Probability Postulate

**Manuscript ID:** `Born_selection_v3.0_Gemini4Carbon`  
**Author:** Gemini 4 Carbon (Google DeepMind), authored from conceptual architecture and physical hypotheses specified by John M. Bramble, MD  
**Date:** November 21, 2026  
**Companion Simulation Artifacts:** [born_selection_v3_sim.c](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/born_selection_v3_sim.c), [exp_v3_tunneling_vs_copenhagen.csv](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/exp_v3_tunneling_vs_copenhagen.csv)

---

## Abstract

Since 1926–1927, the foundational debate among Max Born, Niels Bohr, and Albert Einstein has centered on whether quantum mechanics offers a complete physical account of individual events or merely an ensemble calculus in abstract probability space. In standard Copenhagen modeling of a wave packet illuminating an array of detectors, the time-dependent Schrödinger equation propagates a complex wave to the detector surface, the Born rule ($P \propto |\psi|^2$) translates the resulting interference intensity into a probability distribution, and an external random number generator (RNG) is invoked to select each individual measurement outcome. Here we formulate and analyze an explicit physical mechanism that preserves real-wave Schrödinger evolution and complex surface interference while replacing the axiomatic Born-rule + RNG step with a dynamical single-event detector recipe. In this mechanism, $\psi(\mathbf{r}, t)$ is treated as an ontic physical wave. At the surface of a row of solid-state detectors, deposited excitation energy arises from the complex three-wave interference of (1) the incident wave packet, (2) the wave packets of electrons bound to near-surface detector atoms, and (3) local quantum-vacuum fluctuations at the detector surface. Because the bound-electron and vacuum phases are uncorrelated with the incident wave preparation, their cross-interference adds strictly unbiased zero-mean fluctuations while vanishing identically at destructive-interference nodes. Individual event selection occurs when the **first** near-surface atomic site undergoes photon-assisted quantum tunneling through the orbital excitation barrier into a higher bound or conduction state. Through the nonlocality of the single-quantum wave packet, the entire photon energy ($\hbar\omega$) is absorbed at that initial tunneling site, depleting the extended wave across all rival detectors ($g^{(2)}(0) = 0$). Immediately thereafter, an ultrafast inelastic cascade of interactions with neighboring solid-state bound electrons possessing randomly distributed phases scrambles the incident wave's phase information beyond thermodynamic recovery, establishing macroscopic irreversibility. Across accumulated trials, competing-risks extreme-value dynamics over near-surface atomic sites converge quantitatively to the Born distribution ($p = 0.2103$ across 60 detectors and 7 interference fringes in direct C11 numerical verification, matching standard Copenhagen RNG sampling at $p = 0.1264$ without ever sampling from $|\psi|^2$).

---

## 1. Introduction: Born, Bohr, Einstein, and the Completeness Debate

When Erwin Schrödinger introduced wave mechanics in the spring of 1926 [1], his stated aim was to restore a continuous, causal field physics of atomic phenomena. In Schrödinger's original reading, the complex wave function $\psi(\mathbf{r}, t)$ evolving under

$$
i\hbar \frac{\partial \psi(\mathbf{r}, t)}{\partial t} = \hat{H}\psi(\mathbf{r}, t)
$$

represented an actual physical wave in space whose squared modulus described a real spatial density of charge, matter, or electromagnetic action rather than a catalog of probabilities. That continuous-wave program immediately encountered a sharp empirical puzzle in collision and detection experiments: whereas $\psi(\mathbf{r}, t)$ spreads smoothly across space—forming spherical scattered waves or multi-fringe diffraction patterns—macroscopic detectors register discrete, localized individual impacts (single blackened silver-halide grains, Geiger clicks, or localized photoelectron avalanches).

In June 1926, analyzing asymptotic electron–atom scattering, Max Born proposed resolving this tension by severing $\psi$ from direct physical density in ordinary space and reinterpreting it as a **probability amplitude** [2]. In his celebrated footnote—refining $\psi$ to $|\psi|^2$—Born declared that the wave equation deterministically propagates probability amplitudes in configuration or Hilbert space, while individual experimental outcomes are governed only statistically by $|\psi|^2$. In Born's phrasing, *"the motion of particles follows probability laws, while the probability itself propagates in conformity with the law of causality"* [2].

Niels Bohr rapidly consolidated Born's statistical postulate, Heisenberg's matrix mechanics, and wave–particle complementarity into the **Copenhagen interpretation** presented at Como and the Fifth Solvay Conference in autumn 1927 [3, 4]. For Bohr, quantum mechanics was **complete** in principle: $\psi$ is not an autonomous physical wave field interacting mechanistically with microscopic detector constituents to produce a single record, but a symbolic tool for computing statistical distributions of outcomes registered on classically described macroscopic instruments. How a single run transitions from a continuous complex wave amplitude to one definite detector mark was placed deliberately outside dynamical physical description, summarized operationally by von Neumann's projection postulate (wave-function collapse) [5].

Albert Einstein rejected that settlement from the outset—not because he doubted the empirical accuracy of Schrödinger's wave equation or Born's $|\psi|^2$ ensemble statistics, but because **characterizing the wave function purely as a probability-space calculation of experimental outcomes left individual physical events unexplained** [6–9]. In his December 4, 1926 letter to Born, Einstein wrote that while quantum mechanics *"yields a lot, it hardly brings us closer to the secret of the 'Old One'; I, at any rate, am convinced that He does not throw dice"* [6].

Ten months later, at the **October 1927 Fifth Solvay Conference** in Brussels, Einstein presented a remarkably concrete single-particle detector *Gedankenexperiment* that isolated the exact physical missing link [7]. Consider a single quantum (electron or photon) passing through a narrow slit so that its Schrödinger wave diffracts hemispheres-wide toward a curved photographic screen (a row of independent localized detectors):

1. **Einstein's "Interpretation I" (Pure Ensemble Probability Calculus):** If $|\psi(\mathbf{r}, t)|^2$ applies only to an abstract statistical ensemble in probability space and says nothing about how an individual event forms at one specific grain on the screen, then quantum mechanics is **incomplete**—much as equilibrium thermodynamics is empirically exact for bulk pressures while omitting the kinetic molecular collisions that produce single-molecule wall impacts [7, 9].
2. **Einstein's "Interpretation II" (Ontic Single-Quantum Wave Packet):** Conversely, if $\psi(\mathbf{r}, t)$ is a real physical wave packet illuminating the entire detector surface on a single run, then as soon as one localized site absorbs the entire energy quantum $\hbar\omega$, the wave packet must be nonlocally depleted everywhere else across the screen so that a second detector does not also fire on the same quantum [7].

Einstein himself hoped a deeper *strictly local* field theory would eventually evade both horns of his Solvay dilemma, pressing the locality critique further with Podolsky and Rosen in 1935 (EPR) [8] and in his 1949 *Autobiographical Notes* [9]. Subsequent history split Einstein's two objections cleanly apart. On one hand, **Bell's theorem (1964)** [10] and loophole-free Bell experiments [11, 12], alongside single-photon beam-splitter anticorrelation measurements ($g^{(2)}(0) = 0$) by Grangier, Roger, and Aspect [13], proved that **wave-packet nonlocality cannot be eliminated**: any realist physics of individual events must permit nonlocal single-quantum mode depletion or configuration-space correlation. On the other hand, conceding nonlocality does *not* force physics back into Bohr's claim that $\psi$ is merely an epistemic probability-space recipe. Einstein's deeper constructive challenge remains squarely intact:

> *Can the final step of quantum outcome calculation—translating complex wave interference via the Born rule into a probability distribution and drawing an outcome with an abstract random number generator—be replaced by a concrete physical detector mechanism operating on a real wave, producing individual irreversible events whose accumulation reproduces $|\psi|^2$?*

In this manuscript, we develop and test such a mechanism built from five connected physical ingredients at a solid-state detector surface: (i) ontic Schrödinger wave evolution, (ii) three-wave complex interference among the incident wave packet, near-surface bound atomic electrons, and surface quantum-vacuum fluctuations adding unbiased noise, (iii) first-passage quantum tunneling through an orbital excitation barrier, (iv) nonlocal whole-photon absorption at the initial tunneling site, and (v) thermodynamic irreversibility via a post-tunneling cascade across solid-state bound electrons with randomly distributed phases.

---

## 2. Recipe for Individual Event Calculation vs. Probability-Space Calculation

### 2.1 Step-by-Step Mechanism Recipe

Table 1 summarizes the proposed physical recipe that replaces computing a probability distribution of outcomes with computing individual measurement records one event at a time.

**Table 1. Physical Recipe for Single-Event Outcome Generation Consistent with the Born Rule Upon Accumulation**

| Step | Stage Name | Physical Ingredients | Dynamical Calculation / Physical Action | Role in Replacing the Probability-Space Postulate |
| :---: | :--- | :--- | :--- | :--- |
| **1** | **Ontic Real-Wave Propagation** | Real complex wave packet $\psi_{\text{inc}}(\mathbf{r}, t)$ carrying energy $\hbar\omega$ and action $\hbar$. | Integrate the time-dependent Schrödinger (or Maxwell–Riemann–Silberstein) wave equation from source through slits/optics to the detector surface. | Treats $\psi_{\text{inc}}$ as an objective physical wave field in space-time rather than an abstract Hilbert-space probability vector. |
| **2** | **Surface Three-Wave Complex Interference & Energy Deposition** | Incident wave $\psi_{\text{inc}}$, near-surface bound solid-state electron wave packets $\psi_{\text{el}, j}$, and surface quantum-vacuum modes $\psi_{\text{vac}}$. | Compute $\Psi_{\text{tot}}(\mathbf{r}_j, t) = \psi_{\text{inc}} + \psi_{\text{el}, j} + \psi_{\text{vac}}$ across the row of detectors; net deposited energy above bound-vacuum equilibrium is $\Delta u_j = \|\Psi_{\text{tot}}\|^2 - \|\psi_{\text{el}, j} + \psi_{\text{vac}}\|^2$. | Preserves the exact spatial energy distribution $\|\psi_{\text{inc}}\|^2$ on average while injecting **unbiased** zero-mean local fluctuations ($\mathbb{E}[\delta u_j] = 0$) that vanish at dark interference nodes. |
| **3** | **First-Site Orbital Quantum Tunneling** | Bound surface electrons confined below an orbital excitation energy barrier $\Delta U$ across $N_{\text{surf}} \gg 1$ atomic sites per detector. | Local deposited resonant energy assists quantum tunneling through the barrier to kick an electron into a higher orbit; the **first atomic site $(m^*, a^*)$ to tunnel** initiates event formation. | Replaces an external RNG draw from $\|\psi\|^2$ with a physical first-passage barrier-penetration race across competing surface sites. |
| **4** | **Nonlocal Whole-Photon Absorption** | Spatially extended single-quantum wave packet coupled to the winning tunneling site $(m^*, a^*)$. | Conservation of single-quantum energy ($\hbar\omega$) and action ($\hbar$) transfers the entire photon to site $(m^*, a^*)$, immediately depleting $\psi_{\text{inc}} \to 0$ across all other detectors. | Resolves Einstein's 1927 Solvay single-click constraint ($g^{(2)}(0) = 0$): distant detectors cannot simultaneously absorb fractions of the same photon. |
| **5** | **Irreversible Solid-State Electron Cascade** | Promoted electron interacting with dense neighboring solid-state bound electrons having random phases $\{\theta_k\}$. | Femtosecond inelastic electron–electron (Coulomb/Auger) and phonon cascade mixes $\phi_{\text{inc}}(\mathbf{r}_{j^*})$ with hundreds to millions of uncorrelated bound-electron phases. | Destroys phase retrievability, suppresses coherent back-tunneling/re-emission, and locks in an irreversible macroscopic detector click without invoking an observer axiom. |
| **6** | **Ensemble Accumulation** | Repeated arrivals of independently prepared wave packets on reset solid-state detectors. | Tallying discrete single-site records across $N \gg 1$ independent arrivals yields empirical click frequencies $f_m = N_m / N$. | Competing-risks order statistics over linear-energy barrier tunneling converge asymptotically ($N \to \infty$) to the exact Born distribution $P_{\text{Born}}(m) \propto \int_m \|\psi_{\text{inc}}\|^2 dA$. |

---

### 2.2 Side-by-Side Comparison: Copenhagen / Born-Rule Modeling vs. Proposed Mechanism

To see clearly which mathematical steps remain unchanged and what replaces the final probability-postulate step, Table 2 compares a conventional computer simulation under the Copenhagen interpretation against a simulation of the proposed physical mechanism.

**Table 2. Operational Comparison of Copenhagen / Born-Rule Simulation vs. Real-Wave Tunneling & Cascade Simulation**

| Modeling Stage | Standard Born Rule & Copenhagen Interpretation | Proposed Real-Wave Tunneling & Cascade Mechanism | Identical or Replaced? |
| :--- | :--- | :--- | :---: |
| **1. Wave Ontology** | $\psi(\mathbf{r}, t)$ is a symbolic state vector / probability amplitude in configuration or Hilbert space. | $\psi_{\text{inc}}(\mathbf{r}, t)$ is a **real physical wave** propagating in space and time. | **Conceptual shift** *(same wave equation)* |
| **2. Propagation to Detector Surface** | Evolve $\psi(\mathbf{r}, t)$ from source to the detector surface using the linear time-dependent Schrödinger equation. | Evolve $\psi_{\text{inc}}(\mathbf{r}, t)$ from source to the detector surface using the **exact same** linear time-dependent Schrödinger equation. | **Identical** |
| **3. Surface Interference & Spatial Energy Profile** | Evaluate complex wave superposition at the detector surface; apply the Born rule $P(\mathbf{r}) = \|\psi(\mathbf{r}, T)\|^2$ to define a probability/energy distribution. | Evaluate complex interference of $\psi_{\text{inc}} + \psi_{\text{el}} + \psi_{\text{vac}}$ at the detector surface; mean deposited energy profile across the detector row is the **exact same** $\|\psi_{\text{inc}}(\mathbf{r}, T)\|^2$, modulated per shot by zero-mean unbiased vacuum and bound-electron fluctuations. | **Same mean energy distribution** *(adds physical unbiased surface fluctuations)* |
| **4. Single-Outcome Selection** | Invoke an **axiomatic random number generator (RNG)** to sample one discrete detector index $m^*$ from the Born cumulative probability distribution. | **No RNG draw from $\|\psi\|^2$:** local deposited energy drives photon-assisted **quantum tunneling** across the orbital barrier; **the first surface site to tunnel** wins and nonlocally absorbs the entire photon ($\hbar\omega$). | **Replaced** |
| **5. Irreversibility & Record Formation** | Imposed axiomatically via **wave-function collapse** (von Neumann projection $\psi \to \|m^*\rangle$) across an unspecified classical–quantum cut. | Emerges dynamically from a **cascade of inelastic interactions** with neighboring solid-state bound electrons carrying randomly distributed phases, rendering incident wave-packet phase information unrecoverable. | **Replaced** |
| **6. Accumulated Multi-Shot Statistics** | Converges to $P_{\text{Born}}(m)$ by construction of the RNG sampling distribution. | Converges to $P_{\text{Born}}(m)$ dynamically via competing-risks extreme-value statistics across surface tunneling sites. | **Identical empirical limit** |

---

## 3. Mathematical Formulation and Physical Analysis

### 3.1 Ontic Wave Evolution and Conserved Field Energy / Action

Consider an incident single-quantum wave packet $\psi_{\text{inc}}(\mathbf{r}, t)$ propagating through an interferometer (such as a double-slit aperture) toward a planar row of $M$ contiguous solid-state detectors $\mathcal{S}_1, \mathcal{S}_2, \dots, \mathcal{S}_M$. Prior to reaching the detector surface, evolution is governed strictly by the linear time-dependent Schrödinger equation:

$$
i\hbar \frac{\partial \psi_{\text{inc}}(\mathbf{r}, t)}{\partial t} = \left(-\frac{\hbar^2}{2m_{\text{eff}}}\nabla^2 + V_{\text{opt}}(\mathbf{r})\right)\psi_{\text{inc}}(\mathbf{r}, t),
$$

or, for an optical single-photon wave packet of central frequency $\omega_0$ and total wave energy $\hbar\omega_0$, by the mathematically isomorphic Riemann–Silberstein form of Maxwell's equations $\mathbf{F}(\mathbf{r}, t) = \sqrt{\epsilon_0 / 2}\,\big(\mathbf{E}(\mathbf{r}, t) + i c\mathbf{B}(\mathbf{r}, t)\big)$ [14, 15], where $|\mathbf{F}(\mathbf{r}, t)|^2 = \frac{1}{2}(\epsilon_0|\mathbf{E}|^2 + \mu_0^{-1}|\mathbf{B}|^2) = u_{\text{EM}}(\mathbf{r}, t)$ is literally the classical electromagnetic energy density ($\text{J/m}^3$) obeying Poynting's conservation law $\partial_t u_{\text{EM}} + \nabla\cdot\mathbf{S} = 0$. Similarly, for a Schrödinger matter wave derived from Lagrangian density $\mathcal{L} = \frac{i\hbar}{2}(\psi^*\dot{\psi} - \dot{\psi}^*\psi) - \frac{\hbar^2}{2m}|\nabla\psi|^2 - V|\psi|^2$, Noether's theorem under $U(1)$ phase invariance yields an objective **action density** $\mathcal{A}(\mathbf{r}, t) = \hbar|\psi_{\text{inc}}(\mathbf{r}, t)|^2$ ($\int \mathcal{A}\,d^3r = \hbar$) and **energy density** $u_{\text{inc}}(\mathbf{r}, t) = \hbar\omega_0|\psi_{\text{inc}}(\mathbf{r}, t)|^2$ for quasimonochromatic packets.

Crucially, **no probability concept appears anywhere in Stage 1**: $|\psi_{\text{inc}}(\mathbf{r}, t)|^2$ is a real physical energy/action density arriving at the detector surface, carrying constructive interference peaks and destructive zeros formed by ordinary linear wave superposition.

---

### 3.2 Three-Wave Complex Interference at the Detector Surface and Unbiased Noise

Each macroscopic detector pixel $m \in \{1, \dots, M\}$ exposes a large number $N_{\text{surf}} \gg 1$ of near-surface atoms indexed by $a \in \{1, \dots, N_{\text{surf}}\}$ at positions $\mathbf{r}_{m,a}$ (for a $10\,\mu\text{m} \times 10\,\mu\text{m}$ semiconductor pixel of absorption skin depth $\sim 10\,\text{nm}$, $N_{\text{surf}} \sim 5 \times 10^{10}$ valence electrons). Within the localized capture volume of atomic site $(m, a)$, three physical wave fields overlap simultaneously:

1. **The incident wave packet:** $\psi_{\text{inc}}(\mathbf{r}_{m,a}, t) = |\psi_{\text{inc}}(\mathbf{r}_{m,a}, t)|\,e^{i(\phi_{\text{inc}}(\mathbf{r}_{m,a}) - \omega_0 t)}$.
2. **The bound atomic electron wave packet:** $\psi_{\text{el}, m, a}(t) = A_{\text{el}, m, a}\,e^{i(\theta_{\text{el}, m, a} - \omega_{\text{el}} t)}$, whose microscopic phase $\theta_{\text{el}, m, a} \sim \operatorname{Uniform}[0, 2\pi)$ reflects prior solid-state thermal and lattice interactions completely uncorrelated with the distant photon source.
3. **The surface quantum-vacuum field:** $\psi_{\text{vac}, m, a}(t) = \sum_{\mathbf{k}, \lambda} g_{\mathbf{k},\lambda}\,e^{i(\mathbf{k}\cdot\mathbf{r}_{m,a} - \omega_k t + \theta_{\text{vac}, \mathbf{k},\lambda})}$, a zero-mean fluctuating zero-point field with independent uniform mode phases $\theta_{\text{vac}, \mathbf{k},\lambda} \sim \operatorname{Uniform}[0, 2\pi)$ [16].

Forming the total local complex wave amplitude $\Psi_{\text{tot}}(\mathbf{r}_{m,a}, t) = \psi_{\text{inc}}(\mathbf{r}_{m,a}, t) + \psi_{\text{el}, m, a}(t) + \psi_{\text{vac}, m, a}(t)$ and evaluating its instantaneous wave intensity gives:

$$
\big|\Psi_{\text{tot}}(\mathbf{r}_{m,a}, t)\big|^2 = \underbrace{\big|\psi_{\text{inc}}(\mathbf{r}_{m,a}, t)\big|^2}_{\text{Incident wave intensity}} + \underbrace{\big|\psi_{\text{el}, m, a}(t) + \psi_{\text{vac}, m, a}(t)\big|^2}_{\text{Unilluminated equilibrium baseline } u_{0,m,a}(t)} + \underbrace{2\operatorname{Re}\!\Big[\psi_{\text{inc}}^*(\mathbf{r}_{m,a}, t)\big(\psi_{\text{el}, m, a}(t) + \psi_{\text{vac}, m, a}(t)\big)\Big]}_{\text{Cross-interference fluctuation } \delta u_{m,a}(t)}.
$$

In the absence of an incident wave packet ($\psi_{\text{inc}} = 0$), the surface electron dressed by the quantum vacuum resides stably in its bound ground orbital with equilibrium background density $u_{0, m, a}(t) = |\psi_{\text{el}, m, a}(t) + \psi_{\text{vac}, m, a}(t)|^2$; passivity of the ground-state vacuum prevents spontaneous upward transitions without external energy input. The **net deposited excitation energy** available to drive an upward orbital transition is therefore the excess above the unilluminated equilibrium baseline:

$$
\Delta u_{m,a}(t) \equiv \big|\Psi_{\text{tot}}(\mathbf{r}_{m,a}, t)\big|^2 - u_{0, m, a}(t) = \big|\psi_{\text{inc}}(\mathbf{r}_{m,a}, t)\big|^2 + \delta u_{m,a}(t),
$$

where $\delta u_{m,a}(t) = 2\operatorname{Re}\!\big[\psi_{\text{inc}}^*(\mathbf{r}_{m,a}, t)\big(\psi_{\text{el}, m, a}(t) + \psi_{\text{vac}, m, a}(t)\big)\big]$.

This three-wave surface interference structure possesses **two exact mathematical properties** critical for reproducing quantum interference faithfully:

1. **Strict Zero Bias ($\mathbb{E}[\delta u_{m,a}(t)] = 0$):** Because $\theta_{\text{el}, m, a}$ and $\theta_{\text{vac}, \mathbf{k}, \lambda}$ are uniformly distributed on $[0, 2\pi)$ and statistically independent of $\psi_{\text{inc}}$, we have $\mathbb{E}[\psi_{\text{el}, m, a}(t)] = \mathbb{E}[\psi_{\text{vac}, m, a}(t)] = 0$, and hence:

$$
\mathbb{E}\big[\Delta u_{m,a}(t)\big] = \big|\psi_{\text{inc}}(\mathbf{r}_{m,a}, t)\big|^2.
$$

   Thus, the mean spatial energy distribution across the surface of the detector array is **identical** to the Schrödinger/Born intensity distribution.
2. **Exact Protection of Destructive-Interference Dark Nodes:** Because $\delta u_{m,a}(t)$ enters as a *multiplicative cross-interference term* proportional to $\psi_{\text{inc}}^*(\mathbf{r}_{m,a}, t)$ rather than additive dark noise, **at every destructive-interference zero where $\psi_{\text{inc}}(\mathbf{r}_{m,a}, t) = 0$, both the mean deposited energy and the fluctuation vanish identically ($\Delta u_{m,a}(t) \equiv 0$)**. Vacuum and bound-electron fluctuations diversify timing among illuminated sites without filling in dark interference troughs.

---

### 3.3 First-Passage Quantum Tunneling Across the Orbital Barrier and Emergence of the Born Rule

To produce a discrete record, a bound near-surface electron must escape its ground-state potential well through an energy barrier $\Delta U$ into a higher excited orbital or conduction band. Why must this transition proceed specifically by **quantum tunneling through the barrier** rather than by classical over-the-barrier thermal/diffusive climbing?

#### A. Why Quantum Tunneling Avoids Classical Winner-Takes-All Bias
Suppose every bound electron started deterministically at the bottom of a classical potential well $E(0) = 0$ and had to diffuse *over* a fixed barrier $E_{\text{barrier}}$ via classical heating $dE_j = \kappa|\psi_{\text{inc}, j}|^2 dt + \sqrt{2 D|\psi_{\text{inc}, j}|^2}\,dW_j$. Standard first-passage analysis yields an Inverse Gaussian waiting-time density $f_T(t) \propto t^{-3/2}\exp\big[-E_{\text{barrier}}^2 / (4 D |\psi_{\text{inc}, j}|^2 t)\big]$ whose instantaneous hazard vanishes as $t \to 0^+$ ($f_T(0^+) = 0$). Across $N_{\text{surf}} \gg 1$ atoms per pixel, this deterministic "warm-up lag" causes the brightest interference peak to reach threshold before outer fringes on virtually every trial—producing a **winner-takes-all distortion** analogous to Ehrenfest bistable symmetry breaking [17].

By contrast, in **photon-assisted quantum tunneling** across an orbital or band barrier—established by Tien and Gordon [18] for AC barrier modulation and by Keldysh [19] in the high-frequency optical regime ($\gamma_K = \omega_0\sqrt{2 m_e \Delta U} / (e|\mathbf{E}|) \gg 1$)—the oscillating wave packet splits the bound electron's wave function into quasi-energy sidebands $E_g + n\hbar\omega_0$ with Bessel weights $J_n(\alpha_{m,a})$, where the dimensionless barrier-modulation amplitude $\alpha_{m,a}$ scales with the local resonant field overlap ($\alpha_{m,a}^2 \propto \overline{\Delta u}_{m,a}$). While the unassisted $n = 0$ ground state sits far below the opaque barrier ($\mathcal{T}_{\text{WKB}}(E_g) \approx 0$), the $n = 1$ single-photon sideband at $E_g + \hbar\omega_0$ faces a drastically thinned upper barrier with static WKB transmission rate $\Gamma_{\text{WKB}}(E_g + \hbar\omega_0) > 0$. For single-photon field strengths ($\alpha_{m,a} \ll 1$), expanding $J_1(\alpha_{m,a}) = \frac{1}{2}\alpha_{m,a} + O(\alpha_{m,a}^3)$ gives a **non-vanishing instantaneous barrier-tunneling rate strictly linear in the cycle-averaged deposited energy**:

$$
\lambda_{m,a} = \Gamma_{\text{WKB}}(E_g + \hbar\omega_0)\,\big|J_1(\alpha_{m,a})\big|^2 \approx \kappa\,\overline{\Delta u}_{m,a},
$$

matching Einstein's 1917 linear transition rate law [20] without presupposing Hilbert-space collapse.

#### B. Microscopic Pre-Arrival Deficit Realization and Competing-Risks Convergence
This linear barrier-penetration race admits an instructive deterministic-microstate representation over the $N_{\text{surf}}$ surface atoms of each detector pixel. Prior to photon arrival, solid-state thermal/zero-point interactions endow each bound surface electron $(m,a)$ with an independent sub-barrier action deficit $\Delta S_{m,a} > 0$ required to complete phase-coherent barrier penetration, distributed smoothly near the tunneling boundary ($\Delta S_{m,a} \to 0^+$) with positive boundary density $\rho_S(0^+) = c_0 > 0$—completely independent of $\psi_{\text{inc}}$. Driven by cycle-averaged deposited energy $\overline{\Delta u}_{m,a} > 0$ over $K_{\text{cyc}} \gg 1$ optical cycles, site $(m, a)$ reaches the tunneling condition at physical time

$$
t_{m,a} = \frac{\Delta S_{m,a}}{\overline{\Delta u}_{m,a}}.
$$

Let $T_m = \min_{1 \le a \le N_{\text{surf}}} t_{m,a}$ denote the time of the **first** tunneling initiation inside detector $m$. Conditioning on the surface wave realizations and applying the Fisher–Tippett–Gnedenko / Weibull extreme-value limit ($k = 1$) across $N_{\text{surf}} \gg 1$ independent atomic sites:

$$
\mathbb{P}(T_m > t) = \prod_{a=1}^{N_{\text{surf}}} \Big[1 - c_0\,\overline{\Delta u}_{m,a}\,t + o(t)\Big] = \exp\!\left(-c_0 t \sum_{a=1}^{N_{\text{surf}}} \overline{\Delta u}_{m,a} + O(N_{\text{surf}}^{-1})\right).
$$

By the law of large numbers across the $N_{\text{surf}}$ surface sites of pixel $m$, the unbiased cross-interference fluctuations $\delta u_{m,a}$ cancel ($\sum_{a=1}^{N_{\text{surf}}} \delta\bar{u}_{m,a} / N_{\text{surf}} = O(N_{\text{surf}}^{-1/2}) \to 0$), so the total pixel tunneling hazard converges to the exact integrated incident wave energy on pixel $m$:

$$
\Lambda_m \equiv c_0 \sum_{a=1}^{N_{\text{surf}}} \overline{\Delta u}_{m,a} \;\xrightarrow{N_{\text{surf}} \gg 1}\; c_0 \int_{\mathcal{S}_m} \big|\psi_{\text{inc}}(\mathbf{r}, T)\big|^2\,dA = c_0\,U_m.
$$

In the race across all $M$ detectors ($T^* = \min_{1 \le m \le M} T_m$), independent exponential competing risks satisfy the exact identity

$$
\mathbb{P}\!\left(\text{detector } m^* \text{ tunnels first}\right) = \mathbb{P}\!\left(T_{m^*} = \min_{1 \le m \le M} T_m\right) = \frac{\Lambda_{m^*}}{\sum_{m=1}^M \Lambda_m} = \frac{\int_{\mathcal{S}_{m^*}} |\psi_{\text{inc}}(\mathbf{r}, T)|^2\,dA}{\sum_{m=1}^M \int_{\mathcal{S}_m} |\psi_{\text{inc}}(\mathbf{r}, T)|^2\,dA} = P_{\text{Born}}(m^*).
$$

Thus, **selecting the first site to tunnel** dynamically reproduces the exact Born distribution across arbitrarily many interference fringes and smooth diffraction envelopes without ever sampling from $|\psi_{\text{inc}}|^2$.

---

### 3.4 Nonlocality of the Wave Packet and Whole-Photon Absorption

At time $t^* = T_{m^*}$, the winning electron at site $\mathbf{r}_{m^*, a^*}$ completes barrier tunneling into an excited orbital separated in energy by $\Delta E_{\text{orb}} = \hbar\omega_0$. Because the incident single-photon wave packet carries total quantized energy $E_{\text{pkt}} = \int u_{\text{inc}}(\mathbf{r}, t)\,d^3r = \hbar\omega_0$—spread nonlocally across all $M$ detectors prior to $t^*$—completing the transition $\Delta E_{\text{orb}} = \hbar\omega_0$ at site $\mathbf{r}_{m^*, a^*}$ consumes the **entire** quantum of energy and action of the incident mode:

$$
\psi_{\text{inc}}(\mathbf{r}, t) \;\xrightarrow{\;t = t^{*+}\;}\; 0 \qquad \forall\,\mathbf{r}.
$$

Consequently, for all $t > t^*$, the net deposited energy $\Delta u_{m,a}(t)$ drops to zero across all remaining sites $(m, a) \neq (m^*, a^*)$, halting any secondary tunneling race elsewhere on the detector array. This step directly implements "Interpretation II" of Einstein's 1927 Solvay analysis [7]:

1. **Zero Simultaneous Double Clicks ($g^{(2)}(0) = 0$):** Unlike purely local classical wave-threshold models—which violate the Cauchy–Schwarz bound and predict $g^{(2)}(0) \ge 1$ [13, 21]—whole-quantum depletion enforces strict single-photon anticorrelation across macroscopically separated detectors.
2. **Compatibility with Relativistic No-Signaling:** Although depletion of the extended single-quantum mode is spatially nonlocal, which site tunnels first is governed by uncontrollable local bound-electron and vacuum microstates $(\theta_{\text{el}}, \theta_{\text{vac}}, \Delta S)$. Adjusting detector parameters in one region cannot alter the marginal tunneling hazard $\Lambda_m$ at a spacelike-separated detector prior to $t^*$, preserving Eberhard's relativistic no-signaling theorem [22]. (Meanwhile, changes to slits or apertures propagate strictly causally at wave speed $\le c$ via Stage 1.)

---

### 3.5 Solid-State Electron Cascade and Thermodynamic Irreversibility

Immediately after tunneling at $t^*$ kicks the primary electron at $\mathbf{r}_{m^*, a^*}$ into a higher bound or conduction-band orbit, an isolated two-level atom in vacuum could in principle undergo coherent Rabi oscillation or spontaneous re-emission back into the electromagnetic field, retaining phase memory of $\phi_{\text{inc}}(\mathbf{r}_{m^*, a^*})$. In a solid-state detector, however, the excited primary electron resides inside a dense Fermi sea / valence manifold of $\sim 10^{22}\text{–}10^{23}\,\text{cm}^{-3}$ bound electrons.

On ultrafast femtosecond timescales ($\tau_{ee} \sim 1\text{–}10\,\text{fs}$, orders of magnitude faster than radiative spontaneous emission $\tau_{\text{rad}} \sim 1\,\text{ns}$), the promoted electron undergoes an **inelastic cascade** of electron–electron Coulomb scatterings (impact ionization / Auger relaxation) and optical-phonon emissions (Figure 1).

```
Incident Real Wave Packet psi_inc(r, t)
   |
   +--> [Surface Interference: psi_inc + psi_el + psi_vac] (unbiased zero-mean fluctuations)
           |
           +--> [First Site (m*, a*) Tunnels Across Barrier Delta_U]
                   |
                   +--> Nonlocal Depletion: whole photon (hbar * omega) absorbed at (m*, a*)
                   |
                   +--> Ultrafast Solid-State Cascade (femtosecond inelastic e-e scattering):
                          e_0*(phi_inc)
                            |-- scatters bound e_1 (random phase theta_1)
                            |-- scatters bound e_2 (random phase theta_2)
                            |-- ...
                            +-- scatters bound e_K (random phase theta_K)
                                  => Scrambled joint phase Phi_K = phi_inc + sum_{k=1}^K theta_k
                                  => Macroscopic charge pulse (irreversible detector record)
```
*Figure 1. Causal chain from real-wave surface interference to first-passage tunneling, nonlocal whole-photon absorption, and irreversible phase scrambling across randomly phased solid-state electrons.*

At each inelastic collision $k \in \{1, 2, \dots, K_{\text{cas}}\}$, the excitation transfers energy and momentum to a bound solid-state electron carrying an independent random initial phase $\theta_k \sim \operatorname{Uniform}[0, 2\pi)$. After $K_{\text{cas}}$ interactions, the incident wave's local phase $\phi_{\text{inc}}(\mathbf{r}_{m^*, a^*})$ is embedded exclusively in the collective many-body phase sum

$$
\Phi_{K_{\text{cas}}} = \phi_{\text{inc}}(\mathbf{r}_{m^*, a^*}) + \sum_{k=1}^{K_{\text{cas}}} \theta_k \pmod{2\pi}.
$$

Two rigorous measures quantify the resulting **irreversibility**:

1. **Exact Collapse of Phase-Retrieval Coherence:** Any physical operation attempting to reconstruct $\phi_{\text{inc}}$ without microscopic access to every pre-collision bound electron's phase has characteristic visibility

$$
\mathcal{V}(K_{\text{cas}}) = \Big|\mathbb{E}\big[e^{i(\Phi_{K_{\text{cas}}} - \phi_{\text{inc}})}\big]\Big| = \prod_{k=1}^{K_{\text{cas}}} \left|\frac{1}{2\pi}\int_0^{2\pi} e^{i\theta_k}\,d\theta_k\right| = 0 \qquad \forall\,K_{\text{cas}} \ge 1.
$$

   In a finite sample of $N$ events, empirical phase correlation collapses immediately from $\mathcal{V}(0) = 1$ to the random-walk shot-noise floor $O(N^{-1/2})$ upon the very first random-phase scattering.
2. **Exponential Suppression of Microscopic Time Reversal:** Reversing the absorption to re-emit the original coherent wave packet $\psi_{\text{inc}}(\mathbf{r}, t)$ would require all $K_{\text{cas}}$ secondary electrons and lattice modes to re-collide simultaneously within phase tolerance $\delta\theta \ll 2\pi$, an event of phase-space volume ratio

$$
\mathcal{P}_{\text{rev}}(K_{\text{cas}}) \sim \left(\frac{\delta\theta}{2\pi}\right)^{K_{\text{cas}}} = \exp\!\left(-\frac{\Delta S_{\text{cas}}}{k_B}\right), \qquad \Delta S_{\text{cas}} = k_B K_{\text{cas}} \ln\!\left(\frac{2\pi}{\delta\theta}\right).
$$

   Even for a modest avalanche of $K_{\text{cas}} = 200$ secondary electron interactions with $\delta\theta / (2\pi) = 0.1$, $\mathcal{P}_{\text{rev}} \sim 10^{-200}$. Macroscopic irreversibility is therefore not an extra metaphysical axiom; it is the direct solid-state consequence of cascading interactions across randomly phased bound electrons [23].

---

## 4. Numerical Verification: Copenhagen + RNG vs. Tunneling + Cascade

To verify quantitatively that the proposed single-event mechanism reproduces both multi-fringe quantum interference and the decaying diffraction envelope without sampling from $|\psi|^2$, we implemented both protocols side-by-side in ISO C11 ([born_selection_v3_sim.c](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/born_selection_v3_sim.c)).

### 4.1 Simulation Parameters
- **Incident Schrödinger Wave Packet:** Exact free-particle Schrödinger propagation of a coherent double-slit wave packet ($d = 3.20$, $\sigma_0 = 0.30$, $T = 2.60$, $\hbar = m = 1$) illuminating a row of $M = 60$ contiguous solid-state detectors spanning $x \in [-15, +15]$ ($\Delta x = 0.50$), producing 7 interference fringes ($m = -3, -2, -1, 0, +1, +2, +3$).
- **Protocol A (Copenhagen / Born + RNG):** Evaluates exact 8-point Gauss–Legendre integrated Born weights $P_{\text{Born}}(m) = \int_{\mathcal{S}_m} |\psi_{\text{inc}}(x, T)|^2\,dx$ and selects one detector per trial via inverse-CDF uniform random sampling.
- **Protocol B (Proposed Real-Wave Surface Interference + First-to-Tunnel + Cascade):** Models $N_{\text{surf}} = 64$ near-surface atomic sites per detector ($3{,}840$ competing sites across the array), integrates the 3-wave complex superposition $\psi_{\text{inc}} + \psi_{\text{el}} + \psi_{\text{vac}}$ over $K_{\text{cyc}} = 16$ carrier sub-cycles per packet passage ($A_{\text{el}} = \sigma_{\text{vac}} = 0.008$), assigns state-independent pre-arrival sub-barrier action deficits $\Delta S_{m,a} \sim \operatorname{Uniform}(0, 1)$, awards whole-photon absorption to the single site minimizing $t_{m,a} = \Delta S_{m,a} / \overline{\Delta u}_{m,a}$, and propagates the post-tunneling phase through $K_{\text{cas}} = 200$ random-phase bound-electron collisions across $N = 50{,}000$ independent photon arrivals (`seed = 20261121`).

### 4.2 Quantitative Comparison Across Bright Fringes and Dark Troughs

Across all $M = 60$ detectors ($\text{dof} = 59$), both protocols are statistically indistinguishable from the exact Born distribution:
- **Protocol A (Copenhagen Born + RNG):** $\chi^2 = 71.5620$ ($\text{dof} = 59$), **$p = 0.1264$**, $L_1 = 0.021164$.
- **Protocol B (Proposed First-to-Tunnel + Cascade):** $\chi^2 = 67.4634$ ($\text{dof} = 59$), **$p = 0.2103$**, $L_1 = 0.022639$, simultaneous multi-detector clicks $= 0$ ($g^{(2)}(0) = 0$).

Table 3 compares exact Born intensities against both simulation protocols at representative constructive peaks and destructive troughs ([exp_v3_tunneling_vs_copenhagen.csv](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/exp_v3_tunneling_vs_copenhagen.csv)).

**Table 3. Representative Detector Pixels Across the Double-Slit Interference Array ($N = 50{,}000$ Single-Photon Events)**

| Detector Index $m$ | Center $x_m$ | Interference Feature | Exact Schrödinger Energy Share $P_{\text{Born}}(m)$ | Copenhagen + RNG Empirical Freq. | Proposed Tunneling + Cascade Freq. | Empirical Surface Noise Bias $\langle\delta u\rangle$ |
| :---: | :---: | :--- | :---: | :---: | :---: | :---: |
| `4` | `-12.75` | Outer wing ($m = -3$ tail) | `0.000385` | `0.000440` | `0.000280` | `+1.54e-08` |
| `9` | `-10.25` | Secondary bright peak ($m = -2$) | `0.006348` | `0.006760` | `0.006880` | `+9.99e-08` |
| `14` | `-7.75` | Destructive dark trough | `0.002107` | `0.002080` | `0.002300` | `+1.06e-07` |
| `19` | `-5.25` | First-order bright peak ($m = -1$) | `0.042968` | `0.042200` | `0.041140` | `-4.76e-07` |
| `24` | `-2.75` | Inner destructive dark trough | `0.002365` | `0.002240` | `0.001880` | `-1.48e-08` |
| **`29`** | **`-0.25`** | **Central bright maximum ($m = 0$)** | **`0.083133`** | **`0.083300`** | **`0.081540`** | **`-1.01e-06`** |
| **`30`** | **`+0.25`** | **Central bright maximum ($m = 0$)** | **`0.083133`** | **`0.081900`** | **`0.083740`** | **`+5.24e-07`** |
| `35` | `+2.75` | Inner destructive dark trough | `0.002365` | `0.001880` | `0.002700` | `+7.59e-10` |
| `40` | `+5.25` | First-order bright peak ($m = +1$) | `0.042968` | `0.043140` | `0.044160` | `-4.02e-08` |
| `45` | `+7.75` | Destructive dark trough | `0.002107` | `0.002340` | `0.001820` | `+3.29e-08` |
| `55` | `+12.75` | Outer wing ($m = +3$ tail) | `0.000385` | `0.000400` | `0.000340` | `-1.09e-07` |

Table 4 records the decay of incident wave-packet phase retrievability across the post-tunneling solid-state electron cascade, confirming immediate collapse to the finite-sample statistical noise floor $1/\sqrt{N} \approx 0.0045$.

**Table 4. Loss of Incident Wave-Packet Phase Retrievability Across the Solid-State Electron Cascade ($N = 50{,}000$)**

| Random-Phase Electron Collisions $K_{\text{cas}}$ | Empirical Phase Coherence Visibility $\mathcal{V}(K_{\text{cas}})$ | Theoretical Infinite-Sample Limit | Single-Event Reversal Probability $(\delta\theta / 2\pi)^{K_{\text{cas}}}$ ($\delta\theta/2\pi = 0.1$) |
| :---: | :---: | :---: | :---: |
| `0` *(at instant of tunneling)* | `1.000000` | `1.000000` | `1` |
| `1` | `0.006496` | `0.000000` | $10^{-1}$ |
| `2` | `0.001687` | `0.000000` | $10^{-2}$ |
| `5` | `0.009485` | `0.000000` | $10^{-5}$ |
| `10` | `0.003753` | `0.000000` | $10^{-10}$ |
| `50` | `0.006045` | `0.000000` | $10^{-50}$ |
| `200` | `0.003824` | `0.000000` | $10^{-200}$ |

---

## 5. Discussion: Physical Scope, Regimes of Validity, and Testable Consequences

Replacing an axiomatic probability postulate with a concrete physical detector mechanism does more than resolve an interpretive discomfort: because every step of the recipe invokes real condensed-matter and optical processes, it specifies **exact physical conditions** under which the Born rule holds and identifies extreme regimes where measurable deviations should emerge:

1. **Why Unbiased Surface Noise Is Essential—and What Happens When Biased:** In Step 2, the bound-electron and vacuum waves have random uncorrelated phases, yielding $\mathbb{E}[\delta u] = 0$. If instead a phase-locked coherent wave $\psi_{\text{LO}}$ is deliberately injected at the detector surface, $\mathbb{E}[\delta u] = 2\operatorname{Re}(\psi_{\text{inc}}^*\psi_{\text{LO}}) \neq 0$—which physically corresponds to **optical homodyne interferometry**, shifting the observed count distribution exactly as predicted by three-wave surface interference.
2. **Linear Single-Photon Tunneling vs. Strong-Field / Multiphoton Barriers:** Exact convergence to $|\psi_{\text{inc}}|^2$ relies on the resonant single-quantum barrier-penetration regime ($\hbar\omega_0 \approx \Delta U$, Keldysh parameter $\gamma_K \gg 1$), where $|J_1(\alpha)|^2 \propto |\psi_{\text{inc}}|^2$. If the detector barrier exceeds $\hbar\omega_0$ so that $n \ge 2$ quanta are required ($|J_n(\alpha)|^2 \propto |\psi_{\text{inc}}|^{2n}$), or if intense low-frequency fields enter the quasi-static Fowler–Nordheim tunneling regime ($\gamma_K \ll 1$), the first-to-tunnel distribution shifts systematically away from $|\psi_{\text{inc}}|^2$—consistent with nonlinear multiphoton photodetection.
3. **Finite-$N_{\text{surf}}$ Order-Statistics Corrections in Sub-Wavelength Few-Atom Detectors:** In macroscopic solid-state pixels ($N_{\text{surf}} \sim 10^6\text{–}10^{11}$), extreme-value convergence to exponential hazards holds to parts per million or better. In engineered nanocavity or cold-atom arrays where each "detector" consists of $N_{\text{surf}} = 1\text{–}3$ isolated bound electrons **without** a solid-state electron cascade bath, the mechanism predicts reversible Rabi back-exchange prior to cascade damping and potential $O(1/N_{\text{surf}})$ non-Poissonian waiting-time structure testable via ultrafast pump–probe spectroscopy.
4. **Extension to Multi-Particle Entangled States:** For a single quantum (photon or electron), $\psi_{\text{inc}}(\mathbf{r}, t)$ propagates directly in three-dimensional physical space, and nonlocality enters only at Step 4 (whole-photon depletion upon first tunneling). Extending the same recipe to $N \ge 2$ entangled quanta requires applying joint tunneling conditioning to the correlated wave packet $\Psi(\mathbf{r}_1, \mathbf{r}_2, t)$ so that whole-quantum absorption at Detector 1 updates the conditional wave amplitude arriving at Detector 2, reproducing Bell-type correlations without Hilbert-space RNG axioms.

---

## 6. Conclusion

The century-long tension among Born, Bohr, and Einstein arose from treating the empirical success of $|\psi|^2$ over ensembles as proof that nature possesses no deeper event-by-event physical mechanism beneath probability-space calculation. As shown here, one does not need to abandon Schrödinger's real-wave evolution—or introduce ad-hoc random sampling from $|\psi|^2$—to account for discrete, irreversible detector clicks. When a real wave packet illuminates a solid-state detector array, complex three-wave interference with bound surface electrons and surface quantum-vacuum modes deposits energy with strictly unbiased local fluctuations; photon-assisted quantum tunneling selects the first atomic site to cross its orbital excitation barrier; wave-packet nonlocality deposits the entire quantum at that winning site; and an ultrafast cascade across neighboring bound electrons with randomly distributed phases renders the absorption thermodynamically irreversible. Accumulated over repeated arrivals, individual events generated by this purely physical recipe converge naturally and quantitatively to the Born rule distribution.

---

## References

1. Schrödinger, E. (1926). Quantisierung als Eigenwertproblem (Erste bis Vierte Mitteilung). *Annalen der Physik*, 384(4), 361–376; 384(6), 489–527; 385(13), 437–490; 386(18), 109–139.
2. Born, M. (1926). Zur Quantenmechanik der Stoßvorgänge. *Zeitschrift für Physik*, 37(12), 863–867.
3. Bohr, N. (1928). The quantum postulate and the recent development of atomic theory. *Nature*, 121(3050), 580–590.
4. Bohr, N. (1949). Discussion with Einstein on epistemological problems in atomic physics. In P. A. Schilpp (Ed.), *Albert Einstein: Philosopher-Scientist* (pp. 199–241). Library of Living Philosophers.
5. von Neumann, J. (1932). *Mathematische Grundlagen der Quantenmechanik*. Springer, Berlin.
6. Born, M. (Ed.). (1971). *The Born–Einstein Letters: Correspondence between Albert Einstein and Max and Hedwig Born from 1916 to 1955* (Letter of December 4, 1926). Walker and Company, New York.
7. Bacciagaluppi, G., & Valentini, A. (2009). *Quantum Theory at the Crossroads: Reconsidering the 1927 Solvay Conference* (Einstein's general discussion remarks, pp. 440–442). Cambridge University Press.
8. Einstein, A., Podolsky, B., & Rosen, N. (1935). Can quantum-mechanical description of physical reality be considered complete? *Physical Review*, 47(10), 777–780.
9. Einstein, A. (1949). Autobiographical notes; Reply to criticisms. In P. A. Schilpp (Ed.), *Albert Einstein: Philosopher-Scientist* (pp. 1–95, 665–688). Library of Living Philosophers.
10. Bell, J. S. (1964). On the Einstein Podolsky Rosen paradox. *Physics Physique Физика*, 1(3), 195–200.
11. Aspect, A., Dalibard, J., & Roger, G. (1982). Experimental test of Bell's inequalities using time-varying analyzers. *Physical Review Letters*, 49(25), 1804–1807.
12. Shalm, L. K., Meyer-Scott, E., Christensen, B. G., Bierhorst, P., Wayne, M. A., Stevens, M. J., ... & Nam, S. W. (2015). Strong loophole-free test of local realism. *Physical Review Letters*, 115(25), 250402.
13. Grangier, P., Roger, G., & Aspect, A. (1986). Experimental evidence for a photon anticorrelation effect on a beam splitter: A new light on single-photon interferences. *Europhysics Letters*, 1(4), 173–179.
14. Sipe, J. E. (1995). Photon wave functions. *Physical Review A*, 52(3), 1875–1883.
15. Białynicki-Birula, I. (1996). Photon wave function. *Progress in Optics*, 36, 245–294.
16. Milonni, P. W. (1994). *The Quantum Vacuum: An Introduction to Quantum Electrodynamics*. Academic Press.
17. Landsman, N. P., & Reuvers, R. (2013). A flea on Schrödinger's cat. *Annals of Physics*, 337, 11–53.
18. Tien, P. K., & Gordon, J. P. (1963). Multiphoton process observed in the interaction of microwave fields with the tunneling between superconductor films. *Physical Review*, 129(2), 647–651.
19. Keldysh, L. V. (1965). Ionization in the field of a strong electromagnetic wave. *Soviet Physics JETP*, 20(5), 1307–1314.
20. Einstein, A. (1917). Zur Quantentheorie der Strahlung. *Physikalische Zeitschrift*, 18, 121–128.
21. Clauser, J. F. (1974). Experimental distinction between the quantum and classical field-theoretic predictions for the photoelectric effect. *Physical Review D*, 9(4), 853–860.
22. Eberhard, P. H. (1978). Bell's theorem and the different concepts of locality. *Il Nuovo Cimento B*, 46(2), 392–419.
23. Allahverdyan, A. E., Balian, R., & Nieuwenhuizen, T. M. (2013). Understanding quantum measurement from the solution of dynamical models. *Physics Reports*, 525(1), 1–166.
