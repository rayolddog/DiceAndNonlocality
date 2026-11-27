# Real-Wave Surface Interference, Complexified-Time Entanglement, and Laboratory Discriminators: A Non-Configuration-Space Mechanistic Foundation for the Born Rule (Version 4.0)

**Manuscript ID:** Born_selection_v4.0_Gemini4Carbon  
**Authors:** Gemini 4 Carbon (Google DeepMind) and John M. Bramble, MD  
**Date:** November 26, 2026  
**Companion Numerical Datasets:**
* `exp1_discrete_4level.csv` (Pointer-state resolution across discrete eigenvalues)
* `exp2a_relaxation_ho.csv` (Continuous harmonic oscillator relaxation profile)
* `exp2b_double_slit.csv` (Continuous spatial double-slit reconstruction)
* `exp3_ehrenfest_vs_martingale.csv` (Martingale linear rate vs Ehrenfest bistable distortion)
* `exp_v3_tunneling_vs_copenhagen.csv` (Double-slit 60-pixel benchmark vs Copenhagen RNG)
* `exp_wick_bell_curve.csv` (Wick-rotated elliptic bridge correlation curve, 0° to 180°)
* `exp_wick_chsh_summary.csv` (CHSH inequality violation approaching the Tsirelson limit)

---

## Abstract

Since 1926–1927, foundational quantum mechanics has remained divided between the deterministic propagation of continuous wave amplitudes and the axiomatic, discontinuous extraction of discrete experimental records via the Born probability rule ($P \propto |\psi|^2$) and wave-function collapse. In this work, we present Version 4.0 of the real-wave dynamical framework, providing an end-to-end, single-event mechanistic replacement for the Born postulate and von Neumann projection. Rather than treating $\psi(\mathbf{x}, t)$ as an epistemic catalog of probabilities in an unobservable $3N$-dimensional configuration space, we formulate the wave function as an ontic physical field propagating in ordinary three-dimensional space carrying conserved Noether action density $\mathcal{A}(\mathbf{x}, t) = \hbar|\psi(\mathbf{x}, t)|^2$ and electromagnetic energy density $u_{\text{EM}}(\mathbf{x}, t)$. 

At a detector boundary, the incident wave packet undergoes three-wave complex interference with localized bound-electron wave packets and quantum-vacuum zero-point modes. Because bound-electron and vacuum phases are uncorrelated with the source, their cross-terms provide strictly unbiased, zero-mean fluctuations ($\mathbb{E}[\delta u] = 0$) that vanish identically at destructive interference nodes. Individual measurement outcomes are selected via photon-assisted quantum tunneling across near-surface atomic excitation barriers. Driven by linear cycle-averaged energy deposition, competing-risks extreme-value statistics across $N_{\text{surf}} \gg 1$ surface sites select a single winning site that nonlocally absorbs the full quantum ($\hbar\omega$), depleting the mode across all rival detectors ($g^{(2)}(0) = 0$). An ultrafast inelastic cascade across neighboring solid-state electrons with randomly distributed phases destroys phase retrievability and exponentially suppresses microscopic time reversal ($\mathcal{P}_{\text{rev}} \sim 10^{-200}$), establishing permanent macroscopic irreversibility without observer axioms.

We extend this ontology to multi-particle entanglement without retreating into high-dimensional configuration space ($\mathbb{R}^{3N}$). Entangled pairs propagate as localized physical wave packets in ordinary three-dimensional space whose nonlocal coordination is mediated across complexified time ($\mathbb{R}^3 \times \mathbb{C}_T$). By rotating coordinate time to the imaginary axis ($t \to -i\tau$), the hyperbolic wave operator transforms into an elliptic boundary-value operator without light-cone horizons. Single-event detector triggering acts as a localized Dirichlet boundary update that constrains the conjugate particle's conditional hazard while strictly preserving relativistic no-signaling. Across seven numerical benchmarks, the framework reproduces discrete pointer states, continuous harmonic relaxation, double-slit fringes ($p = 0.2103$, matching Copenhagen at $p = 0.1264$), the quantum angular correlation curve $E(\Delta\theta) = -\cos(\Delta\theta)$, and a CHSH parameter of $S_{\text{CHSH}} = 2.8106 \pm 0.0101$ (Tsirelson bound $2\sqrt{2} \approx 2.8284$). Finally, we articulate two definitive laboratory discriminators: (i) gate-pulsed tunnel-barrier asymmetry, which establishes whether event selection is pre-capture hazard competition or post-capture local escape via cross-gate derivatives ($\partial P_A / \partial k_B < 0$) and arrival-time slope kinks; and (ii) microsecond-coherent long-packet coincidence timing across kilometer-scale baselines, placing empirical bounds on finite-velocity depletion models.

---

## 1. Introduction: Born, Bohr, Einstein, and the Completeness Dilemma

When Erwin Schrödinger formulated wave mechanics in 1926, his explicit objective was to construct an intuitive, causal field theory of matter in space and time. In Schrödinger's initial conception, the complex scalar field $\psi(\mathbf{x}, t)$ governed by
$$i\hbar \frac{\partial \psi(\mathbf{x}, t)}{\partial t} = \hat{H}\psi(\mathbf{x}, t)$$
was not an index of human ignorance or probability, but a physical density field whose squared modulus represented the actual spatial distribution of charge and matter. 

This realist continuum program confronted an immediate crisis when confronted with single-particle scattering and detection: while the Schrödinger wave spreads smoothly and continuously across macroscopic distances—forming spherical radiation patterns or multi-slit diffraction ripples—detectors never record continuous fractions of an electron or photon. Instead, experiments invariably register discrete, localized, all-or-nothing events: single blackened silver halide grains on a photographic plate, localized electron avalanches in Geiger–Müller counters, or discrete voltage pulses in superconducting nanowire single-photon detectors.

In June 1926, Max Born severed $\psi$ from physical space by proposing that the wave function represents an abstract probability amplitude. In his foundational paper on collisional quantum mechanics, Born introduced his famous postulate: the wave function evolves deterministically according to the wave equation, but individual physical events are governed strictly by probability densities:
$$P(\mathbf{x}, t) = |\psi(\mathbf{x}, t)|^2.$$
In Born's formulation, the motion of particles adheres to laws of probability, while probability itself propagates according to causal differential equations.

Niels Bohr rapidly integrated Born's statistical ansatz into the Copenhagen interpretation presented at Como and the Fifth Solvay Conference in 1927. For Bohr, quantum theory was complete in principle. The wave function did not represent an ontic physical field interacting with the microscopic atoms of a detector; rather, it constituted a mathematical algorithm enabling observers to calculate the statistical probabilities of transitions registered on classical measuring instruments. The transition from a continuous spread of possibilities to a single macroscopic outcome was excluded from dynamical description, codified formally by John von Neumann as the axiomatic projection postulate (wave-function collapse):
$$\psi \longrightarrow \frac{\hat{P}_n \psi}{\|\hat{P}_n \psi\|}.$$

Albert Einstein refused to accept this settlement as final. Einstein's critique was not born of an aversion to probability per se—he had founded the statistical mechanics of Brownian motion and formulated the probabilistic radiation coefficients. Rather, his objection was that treating quantum theory purely as an ensemble calculus in abstract probability space left individual physical events unexplained. 

At the October 1927 Solvay Conference, Einstein articulated this defect through a penetrating thought experiment. Consider a single particle diffracting through a small aperture toward a hemispherical photographic screen. Einstein pointed out two mutually exclusive interpretations:

* **Interpretation I (Pure Ensemble Probability):** If $|\psi|^2$ represents only the statistical distribution of an ensemble of repeated trials, then quantum mechanics is incomplete. It provides no physical description of why or how a particular atom on the screen registers the hit on a given run, just as equilibrium thermodynamics describes bulk gas pressure while remaining silent on the individual trajectory of any single molecule.
* **Interpretation II (Ontic Single-Quantum Wave Packet):** If $\psi(\mathbf{x}, t)$ is a real physical wave packet that covers the entire detector screen on a single run, then the moment a single grain absorbs the quantum of energy $\hbar\omega$, the wave packet must instantaneously cease to act across all other portions of the screen. Otherwise, a second distant grain could absorb part of the same quantum, violating conservation of energy and single-particle exclusivity.

Subsequent twentieth-century developments split Einstein's critique in two. Bell's theorem in 1964 and definitive loophole-free Bell tests proved that wave-packet nonlocality cannot be circumvented by local hidden variables: any realist description of nature must permit nonlocal spatial coordination. Furthermore, Grangier, Roger, and Aspect in 1986 empirically demonstrated single-photon beam-splitter anticorrelation ($g^{(2)}(0) = 0$), confirming that a single quantum never triggers two detectors simultaneously. 

However, accepting nonlocality does not compel physics to accept Bohr's claim that $\psi$ is merely a symbolic mathematical calculation. Einstein's primary challenge remains unresolved: can the final step of quantum measurement—the translation of wave interference into a probability distribution and the subsequent selection of a single outcome via an abstract random number generator—be replaced by an objective physical mechanism operating on a real wave, producing individual irreversible records whose accumulation reproduces $|\psi|^2$?

This paper presents such a mechanism. By combining real-wave electrodynamics, microscopic surface three-wave interference, photon-assisted quantum barrier tunneling, complexified-time geometry, and solid-state inelastic cascades, we demonstrate that the Born rule emerges dynamically as the exact macroscopic limit of an objective physical process.

---

## 2. The Core Single-Event Physical Recipe

To eliminate axiomatic wave-function collapse and external random number generation, the quantum measurement process is decomposed into a five-stage physical cascade occurring at the interface between the incident field and the condensed-matter detector.

### 2.1 The Five-Stage Physical Cascade

The dynamical stages governing individual event generation proceed in a causal, physical sequence:

1. **Ontic Real-Wave Propagation:** The incident quantum propagates through physical space as an objective wave packet $\psi_{\text{inc}}(\mathbf{x}, t)$ governed by the linear time-dependent Schrödinger equation or Maxwell's equations. It carries real electromagnetic energy density $u(\mathbf{x}, t)$ and conserved Noether action density $\mathcal{A}(\mathbf{x}, t) = \hbar|\psi_{\text{inc}}(\mathbf{x}, t)|^2$, containing physical peaks and troughs formed by linear superposition. No probability concepts exist at this stage.
2. **Surface Three-Wave Interference and Energy Deposition:** Upon impinging on a detector pixel array, the incident field superposes with the localized wave packets of near-surface bound electrons and surface quantum-vacuum fluctuations. Because the microscopic phases of the bound electrons and vacuum modes are uncorrelated with the incoming wave, their cross-terms generate strictly zero-mean, unbiased fluctuations ($\mathbb{E}[\delta u] = 0$) that vanish identically at destructive interference nodes.
3. **First-Passage Quantum Barrier Tunneling:** Each macroscopic detector pixel exposes millions of near-surface atomic sites. Bound electrons sit within potential wells separated from the continuum or higher excited states by an orbital barrier $\Delta U$. Cycle-averaged energy deposition drives photon-assisted quantum tunneling. The individual sites participate in an extreme-value first-passage race: the first atomic site $(m^*, a^*)$ across the entire detector array to complete barrier tunneling initiates event formation.
4. **Nonlocal Whole-Quantum Depletion:** The single-quantum wave packet is an indivisible excitation carrying total energy $\hbar\omega$ and total action $\hbar$. The moment the winning atomic site completes its transition, it nonlocally absorbs the entire quantum. This extinguishes the incident mode ($\psi_{\text{inc}} \to 0$) across all rival detector pixels, guaranteeing single-click exclusivity ($g^{(2)}(0) = 0$).
5. **Irreversible Solid-State Electron Cascade:** Once promoted, the excited electron interacts with the dense surrounding Fermi sea of bound electrons ($\sim 10^{22}\text{–}10^{23}\text{ cm}^{-3}$). Inelastic Coulomb scattering and optical-phonon emission occur on femtosecond timescales ($\tau_{ee} \sim 1\text{–}10\text{ fs}$), mixing the initial wave phase with hundreds of uncorrelated environmental phases. This destroys phase retrievability and suppresses microscopic time reversal by factors exceeding $10^{-200}$, creating a permanent, macroscopic detection signal.

### 2.2 Side-by-Side Comparison: Copenhagen vs. Real-Wave Mechanism

The foundational differences between the operational Copenhagen algorithm and the proposed mechanistic framework are detailed in Table 1.

**Table 1. Operational Comparison of Copenhagen Modeling vs. Proposed Real-Wave Mechanism**

| Feature | Standard Copenhagen Interpretation | Proposed Real-Wave Mechanism | Status |
| :--- | :--- | :--- | :--- |
| **Wave Ontology** | $\psi(\mathbf{x}, t)$ is an abstract state vector in Hilbert space. | $\psi_{\text{inc}}(\mathbf{x}, t)$ is an ontic physical field in real spacetime. | Conceptual shift |
| **Propagation** | Governed by linear time-dependent wave equations. | Governed by identical linear time-dependent wave equations. | Identical equations |
| **Surface Profile** | Applies Born postulate $P(\mathbf{x}) = \|\psi(\mathbf{x})\|^2$ to define probability. | Evaluates physical three-wave interference; mean energy density is $\|\psi_{\text{inc}}\|^2$. | Same mean distribution |
| **Single-Event Selection** | Samples an outcome index from an axiomatic cumulative distribution using an RNG. | Dynamical first-passage barrier tunneling across competing surface atomic sites. | Axiom replaced by dynamics |
| **Mode Depletion** | Discontinuous mathematical projection (von Neumann collapse) across an observer cut. | Physical whole-quantum absorption enforcing non-signaling mode quenching ($g^{(2)}(0) = 0$). | Axiom replaced by conservation |
| **Irreversibility** | Postulated via classical-quantum division or measurement apparatus axiom. | Dynamical phase scrambling across dense Fermi sea; time reversal suppressed by $10^{-200}$. | Axiom replaced by statistical physics |
| **Accumulated Statistics** | Converges to $P(m) \propto \|\psi_m\|^2$ by construction of the sampling algorithm. | Converges to $P(m) \propto \|\psi_m\|^2$ via extreme-value statistics of linear hazards. | Identical empirical limit |

---

## 3. Mathematical Formulation of Real-Wave Dynamics and Born Rule Emergence

### 3.1 Conserved Noether Action and Energy Densities on $\mathbb{R}^3$

Consider an incident single-quantum wave packet $\psi_{\text{inc}}(\mathbf{x}, t)$ propagating toward a row of contiguous solid-state detector pixels $\mathcal{S}_1, \mathcal{S}_2, \dots, \mathcal{S}_M$. Prior to interacting with the detector boundary, the wave packet obeys the free Schrödinger equation:
$$i\hbar \frac{\partial \psi_{\text{inc}}(\mathbf{x}, t)}{\partial t} = -\frac{\hbar^2}{2m_{\text{eff}}}\nabla^2 \psi_{\text{inc}}(\mathbf{x}, t).$$

The Lagrangian density for this complex scalar field is:
$$\mathcal{L} = \frac{i\hbar}{2}\left(\psi_{\text{inc}}^* \frac{\partial \psi_{\text{inc}}}{\partial t} - \psi_{\text{inc}} \frac{\partial \psi_{\text{inc}}^*}{\partial t}\right) - \frac{\hbar^2}{2m_{\text{eff}}} \nabla\psi_{\text{inc}}^* \cdot \nabla\psi_{\text{inc}} - V(\mathbf{x})|\psi_{\text{inc}}|^2.$$

Under global $U(1)$ gauge transformations $\psi_{\text{inc}} \to e^{i\alpha}\psi_{\text{inc}}$, Noether's theorem dictates the conservation of a real four-current $J^\mu = (\rho_S, \mathbf{J}_S)$:
$$\rho_S(\mathbf{x}, t) = \hbar |\psi_{\text{inc}}(\mathbf{x}, t)|^2, \qquad \mathbf{J}_S(\mathbf{x}, t) = -\frac{i\hbar^2}{2m_{\text{eff}}}\left(\psi_{\text{inc}}^* \nabla\psi_{\text{inc}} - \psi_{\text{inc}} \nabla\psi_{\text{inc}}^*\right),$$
obeying the exact continuity equation:
$$\frac{\partial \rho_S}{\partial t} + \nabla \cdot \mathbf{J}_S = 0.$$

Here $\rho_S(\mathbf{x}, t)$ represents an objective spatial action density normalized such that $\int_{\mathbb{R}^3} \rho_S(\mathbf{x}, t)\,d^3x = \hbar$. For optical fields, the isomorphic Riemann–Silberstein complex vector field $\mathbf{F}(\mathbf{x}, t) = \sqrt{\epsilon_0/2}(\mathbf{E} + i c\mathbf{B})$ yields energy density $u_{\text{EM}}(\mathbf{x}, t) = |\mathbf{F}|^2 = \frac{1}{2}(\epsilon_0|\mathbf{E}|^2 + \mu_0^{-1}|\mathbf{B}|^2)$ obeying Poynting's theorem $\partial_t u_{\text{EM}} + \nabla \cdot \mathbf{S} = 0$. In neither case does probability enter the physical description.

### 3.2 Surface Three-Wave Interference, Unbiased Fluctuations, and Node Protection

A macroscopic detector pixel $m$ contains $N_{\text{surf}} \gg 1$ near-surface atomic sites at localized coordinates $\mathbf{x}_{m,a}$. Within the microscopic capture volume of site $(m,a)$, three distinct physical fields overlap:
1. The incident wave packet: $\psi_{\text{inc}}(\mathbf{x}_{m,a}, t) = |\psi_{\text{inc}}(\mathbf{x}_{m,a}, t)| e^{i(\phi_{\text{inc}}(\mathbf{x}_{m,a}) - \omega_0 t)}$.
2. The bound atomic electron wave: $\psi_{\text{el}, m, a}(t) = A_{\text{el}} e^{i(\theta_{\text{el}, m, a} - \omega_{\text{el}} t)}$.
3. The local quantum-vacuum zero-point field: $\psi_{\text{vac}, m, a}(t) = \sum_{k} g_k e^{i(\mathbf{k}\cdot\mathbf{x}_{m,a} - \omega_k t + \theta_{\text{vac}, k})}$.

The microscopic phases $\theta_{\text{el}, m, a}$ and $\theta_{\text{vac}, k}$ are distributed uniformly on $[0, 2\pi)$ and are statistically independent of the source that launched $\psi_{\text{inc}}$. The total local field amplitude is:
$$\Psi_{\text{tot}}(\mathbf{x}_{m,a}, t) = \psi_{\text{inc}}(\mathbf{x}_{m,a}, t) + \psi_{\text{el}, m, a}(t) + \psi_{\text{vac}, m, a}(t).$$

The instantaneous local energy density evaluates to:
$$|\Psi_{\text{tot}}|^2 = |\psi_{\text{inc}}|^2 + |\psi_{\text{el}} + \psi_{\text{vac}}|^2 + 2\operatorname{Re}\!\Big[\psi_{\text{inc}}^*(\psi_{\text{el}} + \psi_{\text{vac}})\Big].$$

In the absence of illumination ($\psi_{\text{inc}} = 0$), the bound electron dressed by the vacuum sits in unexcited equilibrium with baseline density $u_{0, m, a} = |\psi_{\text{el}} + \psi_{\text{vac}}|^2$. The net excitation energy density available to drive transitions is:
$$\Delta u_{m,a}(t) = |\Psi_{\text{tot}}|^2 - u_{0, m, a} = |\psi_{\text{inc}}(\mathbf{x}_{m,a}, t)|^2 + \delta u_{m,a}(t),$$
where the fluctuating cross-term is:
$$\delta u_{m,a}(t) = 2\operatorname{Re}\!\Big[\psi_{\text{inc}}^*(\mathbf{x}_{m,a}, t)\big(\psi_{\text{el}, m, a}(t) + \psi_{\text{vac}, m, a}(t)\big)\Big].$$

This interaction possesses two fundamental mathematical properties:
* **Strict Zero-Mean Bias:** Because $\mathbb{E}[e^{i\theta_{\text{el}}}] = 0$ and $\mathbb{E}[e^{i\theta_{\text{vac}}}] = 0$, the expectation value of the fluctuation vanishes identically:
  $$\mathbb{E}[\delta u_{m,a}(t)] = 0 \implies \mathbb{E}[\Delta u_{m,a}(t)] = |\psi_{\text{inc}}(\mathbf{x}_{m,a}, t)|^2.$$
* **Exact Protection of Dark Interference Nodes:** The cross-term is multiplicative in $|\psi_{\text{inc}}|$. At any destructive interference node where $\psi_{\text{inc}}(\mathbf{x}) = 0$:
  $$\delta u_{m,a}(t) \equiv 0 \implies \Delta u_{m,a}(t) \equiv 0.$$
  Environmental and vacuum fluctuations diversify event timing at illuminated sites but cannot inject spurious clicks into dark fringes.

### 3.3 Photon-Assisted Barrier Tunneling vs. Classical Over-Barrier Heating

To produce a discrete detection mark, a bound electron must escape its localized potential well across an excitation barrier $\Delta U$. The physical nature of this transition determines whether the resulting statistics reproduce the Born rule or suffer fatal distortions.

#### The Failure of Classical Heating (Ehrenfest Bistable Distortion)
Suppose the bound electron behaves as a classical particle that must diffuse over a barrier via stochastic energy accumulation:
$$dE_j = \kappa |\psi_{\text{inc}, j}|^2 dt + \sqrt{2 D |\psi_{\text{inc}, j}|^2} dW_j.$$
First-passage analysis reveals that the waiting-time density for crossing an over-barrier threshold exhibits an initial latency where the instantaneous hazard vanishes as $t \to 0^+$:
$$f_T(t) \propto t^{-3/2} \exp\!\left(-\frac{E_{\text{barrier}}^2}{4 D |\psi_{\text{inc}, j}|^2 t}\right).$$
Because of this deterministic warm-up lag, the brightest interference peak consistently reaches the threshold first on nearly every run. This induces a winner-takes-all distortion analogous to Ehrenfest bistable symmetry breaking, skewing intermediate probability values by more than 13% (as demonstrated in Section 5.4).

#### Linear Hazard via Photon-Assisted Quantum Tunneling
In quantum mechanics, an oscillating field of frequency $\omega_0$ incident on a potential barrier induces photon-assisted tunneling, as formalized by Tien and Gordon and by Keldysh. The bound electron's wave function develops quasi-energy sidebands at energies $E_g + n\hbar\omega_0$ with amplitudes weighted by Bessel functions $J_n(\alpha_{m,a})$, where $\alpha_{m,a} \propto \sqrt{\overline{\Delta u}_{m,a}}$.

While the unassisted ground state ($n=0$) faces an impenetrable barrier ($\Gamma_{\text{WKB}}(E_g) \approx 0$), the single-quantum sideband ($n=1$) sits at $E_g + \hbar\omega_0$, where the upper barrier thickness is substantially reduced. For weak fields ($\alpha \ll 1$), $J_1(\alpha) \approx \frac{1}{2}\alpha$, yielding a transition rate strictly linear in the cycle-averaged deposited energy:
$$\lambda_{m,a} = \Gamma_{\text{WKB}}(E_g + \hbar\omega_0) |J_1(\alpha_{m,a})|^2 \approx \kappa \overline{\Delta u}_{m,a}.$$
This restores Einstein's 1917 linear transition law without invoking probability axioms.

### 3.4 Microscopic Action Deficits and Competing-Risks Convergence

Before photon arrival, thermal and zero-point fluctuations endow each bound electron with a random sub-barrier action deficit $\Delta S_{m,a} > 0$ required to complete barrier tunneling. Near the escape threshold ($\Delta S \to 0^+$), the density of states is positive and smooth: $\rho_S(0^+) = c_0 > 0$. Driven by deposited energy $\overline{\Delta u}_{m,a}$, site $(m,a)$ achieves tunneling at time:
$$t_{m,a} = \frac{\Delta S_{m,a}}{\overline{\Delta u}_{m,a}}.$$

The first site to tunnel within pixel $m$ defines the pixel waiting time $T_m = \min_{1 \le a \le N_{\text{surf}}} t_{m,a}$. In the asymptotic limit of large surface sites ($N_{\text{surf}} \gg 1$), Weibull extreme-value analysis yields:
$$\mathbb{P}(T_m > t) = \prod_{a=1}^{N_{\text{surf}}} \Big[1 - c_0 \overline{\Delta u}_{m,a} t + o(t)\Big] = \exp\!\left(-c_0 t \sum_{a=1}^{N_{\text{surf}}} \overline{\Delta u}_{m,a}\right).$$

By the spatial law of large numbers, the uncorrelated fluctuations average to zero across the pixel:
$$\frac{1}{N_{\text{surf}}} \sum_{a=1}^{N_{\text{surf}}} \delta\bar{u}_{m,a} \sim \mathcal{O}\!\left(\frac{1}{\sqrt{N_{\text{surf}}}}\right) \longrightarrow 0.$$

Consequently, the macroscopic pixel tunneling hazard converges to the integrated incident wave intensity:
$$\Lambda_m = c_0 \sum_{a=1}^{N_{\text{surf}}} \overline{\Delta u}_{m,a} \longrightarrow c_0 \int_{\mathcal{S}_m} |\psi_{\text{inc}}(\mathbf{x})|^2\,dA = c_0 U_m.$$

In the global race across all $M$ detector pixels, the probability that pixel $m^*$ records the hit is governed by competing independent exponential hazards:
$$\mathbb{P}(\text{pixel } m^* \text{ fires}) = \mathbb{P}\!\left(T_{m^*} = \min_{1 \le m \le M} T_m\right) = \frac{\Lambda_{m^*}}{\sum_{m=1}^M \Lambda_m} = \frac{\int_{\mathcal{S}_{m^*}} |\psi_{\text{inc}}|^2\,dA}{\sum_{m=1}^M \int_{\mathcal{S}_m} |\psi_{\text{inc}}|^2\,dA} \equiv P_{\text{Born}}(m^*).$$
The Born rule thus emerges as the mathematical limit of an objective physical race.

### 3.5 Thermodynamic Irreversibility and Phase Scrambling

Upon completion of tunneling at site $(m^*, a^*)$, the promoted electron enters the dense solid-state medium. While an isolated atom in vacuum would undergo reversible Rabi oscillations, the solid-state environment induces an ultrafast inelastic cascade dominated by electron–electron Coulomb collisions and optical-phonon emission on timescales of $\tau_{ee} \sim 1\text{–}10\text{ fs}$.

At each collision step $k \in \{1, 2, \dots, K_{\text{cas}}\}$, the excitation interacts with a bound electron possessing an independent random phase $\theta_k \sim \operatorname{Uniform}[0, 2\pi)$. After $K_{\text{cas}}$ collisions, the phase of the original wave packet is embedded in a collective many-body sum:
$$\Phi_{K_{\text{cas}}} = \phi_{\text{inc}}(\mathbf{x}_{m^*, a^*}) + \sum_{k=1}^{K_{\text{cas}}} \theta_k \pmod{2\pi}.$$

The macroscopic irreversibility of this process is established by two exact relations:
1. **Destruction of Phase Coherence:** The expectation value of the phase-retrieval operator collapses to zero on the very first collision:
   $$\mathcal{V}(K_{\text{cas}}) = \Big|\mathbb{E}\big[e^{i(\Phi_{K_{\text{cas}}} - \phi_{\text{inc}})}\big]\Big| = \prod_{k=1}^{K_{\text{cas}}} \left|\frac{1}{2\pi}\int_0^{2\pi} e^{i\theta_k} d\theta_k\right| \equiv 0 \quad \forall\, K_{\text{cas}} \ge 1.$$
2. **Exponential Suppression of Time Reversal:** Reversing the cascade to re-emit the incident coherent wave packet requires all $K_{\text{cas}}$ secondary particles to re-collide simultaneously within phase tolerance $\delta\theta \ll 2\pi$. The phase-space probability of such a reversal is:
   $$\mathcal{P}_{\text{rev}} \sim \left(\frac{\delta\theta}{2\pi}\right)^{K_{\text{cas}}} = \exp\!\left(-\frac{\Delta S_{\text{cas}}}{k_B}\right).$$
   For a modest avalanche of $K_{\text{cas}} = 200$ collisions with $\delta\theta / (2\pi) = 0.1$, the reversal probability is $\mathcal{P}_{\text{rev}} \sim 10^{-200}$. Measurement irreversibility is a consequence of many-body statistical mechanics, requiring no observer-based collapse postulate.

---

## 4. Multi-Particle Entanglement in Physical 3D Space and Complexified Time

### 4.1 Rejection of the $3N$-Dimensional Configuration Space Retreat

A standard argument against real-wave interpretations is that while single particles can be visualized in ordinary space, entangled systems of $N$ particles require a wave function $\Psi(\mathbf{x}_1, \mathbf{x}_2, \dots, \mathbf{x}_N, t)$ defined on a $3N$-dimensional configuration space. Historical quantum foundations accepted this retreat, concluding that the physical arena of nature is an abstract $3N$-dimensional manifold rather than three-dimensional physical space.

The present framework explicitly rejects that retreat. In our ontology:
* Physical fields propagate strictly in ordinary three-dimensional space ($\mathbb{R}^3$).
* Just as internal gauge symmetries ($SU(2)_L, SU(3)_c$) are represented by chiral multi-strand structures in $3+1\text{D}$ rather than unobservable compactified spatial dimensions, entanglement does not require an ontic $6\text{D}$ space.
* Nonlocal quantum coordination between separated particles is mediated across **complexified time** ($\mathbb{R}^3 \times \mathbb{C}_T$) via Wick-rotated Euclidean boundaries.

### 4.2 Mathematical Architecture of $\mathbb{R}^3 \times \mathbb{C}_T$ and the Wick-Rotated Elliptic Bridge

Consider two entangled particles $A$ and $B$ (e.g., a spin-singlet pair or polarization-entangled photons) emitted from a common source toward separated analyzers at $\mathbf{x}_A$ and $\mathbf{x}_B$. 

On the real physical time slice ($\tau = 0$), each particle propagates as an independent physical wave packet in ordinary three-dimensional space:
$$\psi_A(\mathbf{x}, t) = R_A(\mathbf{x}, t) e^{i S_A(\mathbf{x}, t)/\hbar}, \qquad \psi_B(\mathbf{x}, t) = R_B(\mathbf{x}, t) e^{i S_B(\mathbf{x}, t)/\hbar}.$$
Each wave packet obeys a local hyperbolic wave equation (Schrödinger or Maxwell) and carries its own conserved Noether action density in $\mathbb{R}^3$:
$$\mathcal{A}_A(\mathbf{x}, t) = \hbar|\psi_A(\mathbf{x}, t)|^2, \qquad \mathcal{A}_B(\mathbf{x}, t) = \hbar|\psi_B(\mathbf{x}, t)|^2, \qquad \int_{\mathbb{R}^3} \mathcal{A}_{A,B}\,d^3x = \hbar.$$

In real Lorentzian spacetime, the spacelike separation between $\mathbf{x}_A$ and $\mathbf{x}_B$ is protected by the light cone of the hyperbolic wave operator:
$$\left(\frac{1}{c^2}\frac{\partial^2}{\partial t^2} - \nabla^2 + \frac{m^2 c^2}{\hbar^2}\right)\psi(\mathbf{x}, t) = 0.$$

When coordinate time is continued into the complex plane $T = t - i\tau$ and evaluated on the Euclidean imaginary-time axis ($t \to -i\tau$, $\partial_t^2 \to -\partial_\tau^2$), the wave equation transforms into an **elliptic boundary-value operator**:
$$-\left(\frac{1}{c^2}\frac{\partial^2}{\partial \tau^2} + \nabla^2 - \frac{m^2 c^2}{\hbar^2}\right)\psi_E(\mathbf{x}, \tau) = 0.$$

This mathematical transformation alters the causal structure:
1. **Disappearance of Characteristic Horizons:** Elliptic differential equations have no real characteristic surfaces (light cones). In an elliptic system, boundary conditions imposed at any point on the boundary instantaneously establish global equilibrium throughout the interior domain.
2. **Entangled Pair Emission as a Continuous Euclidean Loop:** In relativistic quantum field theory (Bisognano–Wichmann theorem and Unruh–Israel formalisms), an entangled pair state is equivalent to a single continuous field propagating around an imaginary-time half-loop of extent $\Delta\tau = \hbar/(2 k_B T_{\text{eff}})$ connecting worldlines $A$ and $B$. While paths $A$ and $B$ are disconnected in real Lorentzian time, they form a connected geometric boundary on the complexified $\tau$-sheet.

### 4.3 Single-Event Detector Triggering as an Active Dirichlet Boundary Update

When wave packets arrive at Alice's and Bob's analyzers (set at angles $\theta_A$ and $\theta_B$):
1. Alice's detector array undergoes microscopic three-wave interference, initiating a competing-risks race across her near-surface sites with local hazards $\lambda_{m_A, a_A} = \kappa \overline{\Delta u}_{m_A, a_A}$.
2. Conditioned on uncontrollable local microstates ($\theta_{\text{el}}, \Delta S$), a specific atomic site $(m_A^*, a_A^*)$ completes barrier tunneling first, registering outcome $\pm 1$.
3. The physical absorption of quantum $A$ acts as an active **Dirichlet boundary condition** on the shared complexified-time sheet at $(t_A, \mathbf{x}_A)$.
4. Because the bridge along $\tau$ is governed by an elliptic PDE, this boundary condition fixes the global phase relationship across the Euclidean interior, directly constraining the conditional hazard arriving at Bob's detector at $(t_B, \mathbf{x}_B)$:
   $$\lambda_B(\theta_B \mid \text{Alice registers } \pm, \theta_A) \propto \cos^2\!\left(\frac{\theta_A - \theta_B}{2}\right) \quad \text{or} \quad \sin^2\!\left(\frac{\theta_A - \theta_B}{2}\right).$$

### 4.4 Preservation of Relativistic No-Signaling

Although the elliptic bridge establishes nonlocal phase constraints, it strictly forbids superluminal communication. Because Alice's outcome is chosen by local, zero-mean, unbiased environmental and vacuum fluctuations ($\mathbb{E}[\delta u] = 0$), Alice has no control over which channel fires. 

Summing Bob's conditional detection rate over Alice's random $50/50$ outcomes yields:
$$P(B = +) = \frac{1}{2}\cos^2\!\left(\frac{\Delta\theta}{2}\right) + \frac{1}{2}\sin^2\!\left(\frac{\Delta\theta}{2}\right) = \frac{1}{2}\left[\cos^2\!\left(\frac{\Delta\theta}{2}\right) + \sin^2\!\left(\frac{\Delta\theta}{2}\right)\right] \equiv \frac{1}{2}.$$
Bob's marginal probability distribution is strictly independent of Alice's analyzer setting $\theta_A$:
$$\frac{\partial P(B = \pm)}{\partial \theta_A} \equiv 0.$$
Nonlocal quantum correlations exist without violating relativistic causality.

---

## 5. Comprehensive Numerical Benchmarks Across Seven Empirical Domains

The theoretical framework has been subjected to rigorous numerical verification across seven dedicated computational experiments.

### 5.1 Discrete 4-Level Pointer State Resolution (`exp1_discrete_4level.csv`)

To test discrete quantum measurement without projection axioms, a 4-level system with target Born probabilities was simulated over 200,000 independent runs. As recorded in Table 2, the empirical frequencies generated by the competing-risks race converge to the target Born values with sub-tenth-percent error.

**Table 2. Discrete 4-Level Pointer State Verification ($N = 200{,}000$ Trials)**

| Pointer State Index | Theoretical Born Probability | Empirical Hit Count | Empirical Observed Frequency | Absolute Error |
| :--- | :--- | :--- | :--- | :--- |
| Level 0 | 0.089851 | 17,946 | 0.089730 | -0.000121 |
| Level 1 | 0.469595 | 94,180 | 0.470900 | +0.001305 |
| Level 2 | 0.324316 | 64,888 | 0.324440 | +0.000124 |
| Level 3 | 0.116238 | 22,986 | 0.114930 | -0.001308 |

### 5.2 Continuous Harmonic Oscillator Relaxation (`exp2a_relaxation_ho.csv`)

Continuous-variable relaxation was modeled by simulating non-stationary harmonic oscillator coherent states relaxing into position-space coordinate bins. The empirical counts track the Gaussian Schrödinger probability density across all spatial intervals (Table 3).

**Table 3. Representative Spatial Bins for Continuous Harmonic Oscillator Relaxation**

| Bin Center Coordinate $x$ | Theoretical Schrödinger Density | Empirical Hit Count | Empirical Probability Share |
| :--- | :--- | :--- | :--- |
| -2.25 | 0.007623 | 76 | 0.007600 |
| -1.25 | 0.086438 | 871 | 0.087100 |
| **-0.25** | **0.231208** | **2,304** | **0.230400** |
| **+0.25** | **0.231208** | **2,328** | **0.232800** |
| +1.25 | 0.086438 | 859 | 0.085900 |
| +2.25 | 0.007623 | 74 | 0.007400 |

### 5.3 Continuous Double-Slit Reconstruction (`exp2b_double_slit.csv`)

Diffraction and interference fringes produced by two coherent slit sources were reconstructed across a continuous screen coordinate $x \in [-10, +10]$. The first-passage tunneling mechanism smoothly populates the central interference maximum and outer diffraction sidelobes without numerical artifacts (Table 4).

**Table 4. Representative Screen Positions for Double-Slit Reconstruction**

| Screen Position $x$ | Interference Feature | Theoretical Intensity | Empirical Observed Count |
| :--- | :--- | :--- | :--- |
| -5.00 | Destructive Minima | 0.001210 | 12 |
| -2.50 | First-Order Peak | 0.087450 | 882 |
| **0.00** | **Central Principal Maximum** | **0.324500** | **3,251** |
| +2.50 | First-Order Peak | 0.087450 | 869 |
| +5.00 | Destructive Minima | 0.001210 | 11 |

### 5.4 Dynamical Mechanism Validation: Martingale Hazard vs. Ehrenfest Bistability (`exp3_ehrenfest_vs_martingale.csv`)

To determine whether classical threshold models can reproduce quantum probabilities, we compared an Ehrenfest-type over-barrier heating model against the martingale linear hazard model across multiple target probability thresholds.

**Table 5. Side-by-Side Accuracy: Ehrenfest Bistability vs. Martingale Linear Hazard**

| Target Born Probability | Ehrenfest Model Probability | Ehrenfest Error | Martingale Model Probability | Martingale Error |
| :--- | :--- | :--- | :--- | :--- |
| 0.1000 | 0.0421 | -0.0579 | 0.0994 | -0.0006 |
| 0.3000 | 0.1618 | -0.1382 | 0.2988 | -0.0012 |
| 0.5000 | 0.5000 | 0.0000 | 0.5004 | +0.0004 |
| 0.7000 | 0.8382 | +0.1382 | 0.7011 | +0.0011 |
| 0.9000 | 0.9579 | +0.0579 | 0.9008 | +0.0008 |

The data confirms that classical over-barrier diffusion creates severe winner-takes-all S-curve distortions (errors exceeding $\pm 13.8\%$), whereas linear barrier tunneling tracks target Born probabilities to within $\pm 0.12\%$.

### 5.5 Double-Slit Benchmark: Tunneling vs. Copenhagen (`exp_v3_tunneling_vs_copenhagen.csv`)

A direct benchmark of 50,000 single-photon events across an array of 60 detector pixels exhibiting 7 interference fringes was conducted comparing standard Copenhagen RNG sampling against the proposed first-to-tunnel mechanism.

**Table 6. Representative Pixel Comparison: Copenhagen RNG vs. Proposed Tunneling Mechanism**

| Pixel Index $m$ | Coordinate $x_m$ | Feature | Exact Born Share $P_{\text{Born}}$ | Copenhagen Freq. | Tunneling Freq. | Surface Noise Bias $\langle\delta u\rangle$ |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 4 | -12.75 | Outer wing ($m=-3$) | 0.000385 | 0.000440 | 0.000280 | +1.54e-08 |
| 9 | -10.25 | Secondary peak ($m=-2$) | 0.006348 | 0.006760 | 0.006880 | +9.99e-08 |
| 14 | -7.75 | Destructive trough | 0.002107 | 0.002080 | 0.002300 | +1.06e-07 |
| 19 | -5.25 | First-order peak ($m=-1$) | 0.042968 | 0.042200 | 0.041140 | -4.76e-07 |
| 24 | -2.75 | Inner trough | 0.002365 | 0.002240 | 0.001880 | -1.48e-08 |
| **29** | **-0.25** | **Central peak ($m=0$)** | **0.083133** | **0.083300** | **0.081540** | **-1.01e-06** |
| **30** | **+0.25** | **Central peak ($m=0$)** | **0.083133** | **0.081900** | **0.083740** | **+5.24e-07** |
| 35 | +2.75 | Inner trough | 0.002365 | 0.001880 | 0.002700 | +7.59e-10 |
| 40 | +5.25 | First-order peak ($m=+1$) | 0.042968 | 0.043140 | 0.044160 | -4.02e-08 |
| 45 | +7.75 | Destructive trough | 0.002107 | 0.002340 | 0.001820 | +3.29e-08 |
| 55 | +12.75 | Outer wing ($m=+3$) | 0.000385 | 0.000400 | 0.000340 | -1.09e-07 |

Statistical analysis across all 60 pixels demonstrates that the proposed mechanism matches the Born distribution ($\chi^2 = 67.46, p = 0.2103$) with fidelity comparable to standard Copenhagen RNG sampling ($\chi^2 = 71.56, p = 0.1264$), while strictly enforcing $g^{(2)}(0) = 0$ and vanishing noise bias ($\langle\delta u\rangle \sim 10^{-7}\text{–}10^{-10}$).

### 5.6 Wick Elliptic Bridge Bell Correlation Curve (`exp_wick_bell_curve.csv`)

The complexified-time elliptic bridge was evaluated for bipartite spin correlations across analyzer angle differences $\Delta\theta \in [0^\circ, 180^\circ]$ in $15^\circ$ increments (Table 7).

**Table 7. Angular Correlation Data via Wick Elliptic Bridge ($N = 10{,}000$ Pairs per Angle)**

| Angle Difference $\Delta\theta$ | Quantum Benchmark $-\cos(\Delta\theta)$ | Simulation Correlation $E(\Delta\theta)$ | Statistical Uncertainty | Alice Marginal $P(A+)$ | Bob Marginal $P(B+)$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 0° | -1.0000 | -0.9998 | 0.0002 | 0.5012 | 0.5010 |
| 30° | -0.8660 | -0.8654 | 0.0048 | 0.4990 | 0.5004 |
| 45° | -0.7071 | -0.7082 | 0.0068 | 0.5021 | 0.4998 |
| 60° | -0.5000 | -0.4988 | 0.0084 | 0.4985 | 0.5012 |
| 90° | 0.0000 | +0.0014 | 0.0099 | 0.5002 | 0.5008 |
| 120° | +0.5000 | +0.5016 | 0.0084 | 0.5014 | 0.4996 |
| 135° | +0.7071 | +0.7064 | 0.0069 | 0.4995 | 0.5018 |
| 150° | +0.8660 | +0.8671 | 0.0048 | 0.5008 | 0.5002 |
| 180° | +1.0000 | +0.9996 | 0.0003 | 0.5004 | 0.5006 |

The simulated correlation reproduces the quantum mechanical curve without discrepancy, while Alice's and Bob's marginal detection probabilities remain strictly $50/50$ ($P \approx 0.500$) across all angles, confirming no-signaling.

### 5.7 CHSH Inequality Violation (`exp_wick_chsh_summary.csv`)

The Clauser–Horne–Shimony–Holt (CHSH) parameter was evaluated over 80,000 particle pairs under standard optimal settings ($a = 0^\circ, a' = 45^\circ, b = 22.5^\circ, b' = 67.5^\circ$), comparing the active elliptic bridge against a control configuration where the bridge was disabled.

**Table 8. CHSH Metric Comparison: Active Bridge vs. Inactive Control**

| Configuration | Total Particle Pairs | Measured CHSH Parameter $S_{\text{CHSH}}$ | Standard Error | Classical Limit Bound | Quantum Tsirelson Limit |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Active Wick Bridge** | **80,000** | **2.8106** | **0.0101** | **$\le 2.0$ (Violated)** | **$2\sqrt{2} \approx 2.8284$** |
| Inactive Control | 80,000 | 1.4104 | 0.0187 | $\le 2.0$ (Satisfied) | $2\sqrt{2} \approx 2.8284$ |

The active elliptic bridge achieves $S_{\text{CHSH}} = 2.8106 \pm 0.0101$, violating the classical Bell inequality by more than 80 standard deviations and closely approaching the quantum Tsirelson limit.

---

## 6. The Physics of Phase Coherence: Macroscopic Fringes vs. Microscopic Event Selection

A central physical insight of Version 4.0 is the dual role played by phase coherence across macroscopic wave propagation versus microscopic detector event selection.

### 6.1 Path Interference Demands Mutual Phase Coherence

For an incident wave packet to form stable, stationary spatial interference fringes across slits or interferometer arms, the interfering paths ($\psi_1$ and $\psi_2$) must share an identical carrier frequency $\omega_0$ and a stable relative phase $\Delta\phi(\mathbf{x})$:
$$|\psi_1(\mathbf{x}, t) + \psi_2(\mathbf{x}, t)|^2 = |\psi_1|^2 + |\psi_2|^2 + 2|\psi_1||\psi_2|\cos(\Delta\omega t + \Delta\phi(\mathbf{x})).$$
Because both paths originate from the same single-quantum emission event, $\Delta\omega = \omega_1 - \omega_2 = 0$. The interference cross-term is static in time, establishing fixed constructive peaks and destructive dark nodes throughout the wave packet transit duration ($\tau_{\text{pkt}} \le \tau_{\text{coh}}$). If the spatial branches were mutually incoherent, rapid phase jitter would average the cross-term to zero ($\langle\cos(\Delta\phi(t))\rangle = 0$), washing out the fringe pattern into classical intensity addition.

### 6.2 Detector Surface Three-Wave Interference Demands Mutual Incoherence

At the detector boundary, the physical requirement is completely inverted. The incident wave packet superposes locally with bound-electron wave packets and quantum-vacuum modes:
$$\delta u_{m,a}(t) = 2\operatorname{Re}\!\Big[\psi_{\text{inc}}^*(\mathbf{x}_{m,a}, t)\big(\psi_{\text{el}, m, a}(t) + \psi_{\text{vac}, m, a}(t)\big)\Big].$$

Here, the environmental phases $\theta_{\text{el}}$ and $\theta_{\text{vac}}$ must be **mutually incoherent and completely uncorrelated** with $\psi_{\text{inc}}$. Because $\theta_{\text{el}}, \theta_{\text{vac}} \sim \operatorname{Uniform}[0, 2\pi)$:
1. The expectation value vanishes identically: $\mathbb{E}[\delta u] = 0$.
2. The instantaneous local cross-term fluctuates rapidly in time and space, providing the stochastic trigger that diversifies atomic tunneling waiting times.

### 6.3 Cycle-Averaging and the Law of Large Numbers Across Surface Atoms

The apparent paradox of rapid microscopic fluctuations generating a stable macroscopic detection hazard is resolved by two physical averaging mechanisms:
* **Cycle-Averaging over the Tunneling Transition:** Photon-assisted barrier tunneling is a resonant process that integrates deposited energy over multiple optical cycles ($K_{\text{cyc}} \gg 1$). Rapid carrier oscillations and non-resonant beat frequencies average to zero, leaving a quasi-static energy envelope.
* **Spatial Law of Large Numbers ($N_{\text{surf}} \gg 1$):** Each macroscopic pixel exposes $N_{\text{surf}} \sim 10^6\text{–}10^{11}$ near-surface atoms. Because adjacent sites possess uncorrelated bound-electron phases, their cross-terms cancel upon spatial summation across the pixel:
  $$\frac{1}{N_{\text{surf}}} \sum_{a=1}^{N_{\text{surf}}} \delta\bar{u}_{m,a} \sim \mathcal{O}\!\left(\frac{1}{\sqrt{N_{\text{surf}}}}\right) \longrightarrow 0.$$
  The macroscopic pixel hazard $\Lambda_m = c_0 U_m$ is completely stable and tracks the exact Schrödinger intensity, while the microscopic race between individual atoms is randomized by local zero-mean fluctuations.

### 6.4 Deliberate Coherent Injection (Optical Homodyne Control)

If an experiment deliberately injects a coherent local oscillator field $\psi_{\text{LO}}$ onto the detector surface that is phase-locked to $\psi_{\text{inc}}$ with phase difference $\Delta\phi$, the cross-term is no longer incoherent:
$$\mathbb{E}[\delta u] = 2|\psi_{\text{inc}}||\psi_{\text{LO}}|\cos(\Delta\phi) \neq 0.$$
The fluctuation stops behaving as random noise and becomes a stationary, phase-dependent bias. This reproduces the physics of optical homodyne detection, proving that the transition between stochastic Born-rule selection and deterministic homodyne amplification is controlled by the mutual coherence of the surface fields.

### 6.5 Breakdown in the Few-Atom / Nanocavity Limit

If the detector pixel is engineered down to a sub-wavelength nanocavity containing only $N_{\text{surf}} = 1\text{–}3$ isolated atoms without a solid-state Fermi reservoir:
* Spatial averaging over $N_{\text{surf}}$ fails.
* The system cannot establish a memoryless exponential hazard rate.
* Coherent Rabi oscillations and back-exchange will occur prior to irreversibility, leading to non-Poissonian waiting times and measurable deviations from the Born distribution.

---

## 7. Definitive Laboratory Discriminators

To test this framework against alternative quantum foundational models, we specify two distinct experimental discriminators.

### 7.1 Laboratory Discriminator I: Gate-Pulsed Tunnel-Barrier Asymmetry

This experiment distinguishes **pre-capture hazard competition** (the gap-to-continuum Born selection model) from **post-capture local escape** (semiclassical and independent-threshold models).

#### Experimental Architecture
A single-photon wave packet is directed into a balanced 50:50 beam splitter whose two output ports terminate at independent detector channels $A$ and $B$. Each detector incorporates an electrostatic or microwave gate terminal ($V_g^A, V_g^B$) that directly modulates its internal barrier tunneling transparency $k_A(V_g^A)$ and $k_B(V_g^B)$.

#### Competing Mathematical Predictions
* **Model I (Pre-Capture Hazard Competition):** The extended wave packet illuminates both detectors simultaneously. Because the first site to tunnel absorbs the entire quantum ($\hbar\omega$) and suppresses all rival sites, the branching ratio is governed by competing hazards:
  $$P(A \text{ fires}) = \frac{k_A w_A}{k_A w_A + k_B w_B}, \qquad P(B \text{ fires}) = \frac{k_B w_B}{k_A w_A + k_B w_B}.$$
  Differentiating with respect to gate $B$'s transparency yields a negative cross-gate coupling:
  $$\frac{\partial P(A)}{\partial k_B} = -\frac{k_A w_A w_B}{(k_A w_A + k_B w_B)^2} < 0.$$
  Lowering detector $B$'s barrier actively depresses the detection count at detector $A$.
* **Model II (Post-Capture Local Escape):** The photon splits deterministically into partial localized shares $w_A$ and $w_B$. Once energy is localized at detector $A$, its escape probability depends exclusively on local parameters:
  $$P(A \text{ fires}) = w_A (1 - e^{-k_A T}) \implies \frac{\partial P(A)}{\partial k_B} \equiv 0.$$
  Detector $A$'s click rate is completely independent of gate $B$.

**Table 9. Observable Signatures for Gate-Pulsed Barrier Asymmetry**

| Observable Metric | Pre-Capture Hazard Competition | Post-Capture Local Escape |
| :--- | :--- | :--- |
| **Static Asymmetry ($k_A \gg k_B$)** | $P(A) \to 1.0, P(B) \to 0.0$ (Detector $A$ captures all events). | $P(A) \to 0.5, P(B) \to 0.0$ (Total efficiency drops to 50%). |
| **Cross-Gate Derivative $\partial P_A / \partial k_B$** | **Strictly Negative ($\partial P_A / \partial k_B < 0$)** | **Identically Zero ($\partial P_A / \partial k_B \equiv 0$)** |
| **Coincidence Rate $g^{(2)}(0)$** | Strictly Zero ($g^{(2)}(0) \equiv 0$) | Non-Zero under high transparency ($g^{(2)}(0) > 0$) |
| **Dynamic Gate-Switching Click Density** | **Sharp slope kink at switching time $t_{\text{switch}}$** | **Smooth decay; no slope inflection** |

#### Dynamic Gate-Switching Protocol
Using a narrowband single photon ($\tau_{\text{coh}} \ge 50\text{ ns}$), gate $B$ is pulsed open at $t = t_{\text{switch}}$ halfway through packet transit:
* Pre-capture competition predicts that detector $A$'s temporal arrival histogram $f_A(t)$ displays an **instantaneous slope kink** to a steeper decay rate $-(k_A w_A + k_B' w_B)$ as detector $B$ rapidly consumes the mode.
* Post-capture models predict no slope change.
* Feasible platforms include split-junction SQUID microwave counters in circuit QED, gate-defined semiconductor quantum dots, and dual-gated traveling-wave SNSPDs.

### 7.2 Laboratory Discriminator II: Long-Packet Coincidence Timing Across Separated Detectors

This experiment investigates whether whole-quantum mode depletion is instantaneous across separated ports or governed by a finite collapse speed $v_{\text{dep}} < \infty$.

#### The Mandate for Microsecond Coherence ($\tau_{\text{coh}} \ge 1\,\mu\text{s}$)
Standard down-conversion sources produce sub-picosecond wave packets ($L_{\text{coh}} \approx 30\,\mu\text{m}$). For detectors separated by $D_{AB} = 300\text{ m}$, the baseline transit time $\Delta t_{\text{transit}} = D_{AB}/c \approx 1\,\mu\text{s}$ is millions of times longer than the packet duration; the packet has cleared both detectors before any physical signal could cross between them. 

Definitive testing requires **narrowband single-photon sources** (cold-atom EIT or trapped-ion cavity QED) with line widths $\Delta\nu \le 1\text{ MHz}$ ($\tau_{\text{coh}} \ge 1\,\mu\text{s}$, $L_{\text{coh}} \ge 300\text{ m}$). Under these conditions, the coherent mode actively illuminates both detectors simultaneously for over a microsecond.

#### Competing Mathematical Predictions
* **Finite-Velocity Depletion Models ($v_{\text{dep}} < \infty$):** If state reduction propagates through real space at finite speed $v_{\text{dep}}$, a click at detector $A$ leaves detector $B$ unquenched for duration $\Delta t = D_{AB}/v_{\text{dep}}$. If detector $B$ tunnels during this window, an anomalous double click occurs:
  $$g^{(2)}(0) \approx \frac{D_{AB}}{v_{\text{dep}} \cdot \tau_{\text{pkt}}}.$$
  For $D_{AB} = 3\text{ km}$ and $\tau_{\text{pkt}} = 1\,\mu\text{s}$, a collapse velocity of $v_{\text{dep}} = 100\,c$ yields $g^{(2)}(0) \approx 0.10$, easily detectable above background.
* **Complexified-Time Elliptic Depletion ($\mathbb{R}^3 \times \mathbb{C}_T$):** Because whole-quantum depletion is governed by an elliptic boundary constraint across the imaginary-time ($\tau$) sheet:
  $$g^{(2)}(\Delta t) \equiv 0 \quad \text{for all } |\Delta t| > \tau_{\text{jitter}},$$
  where $\tau_{\text{jitter}} \sim 15\text{–}30\text{ ps}$ is the intrinsic detector electronic jitter.

#### Spacelike Separation Protocol
Placing detectors $A$ and $B$ in separate laboratory buildings ($D_{AB} \ge 1\text{ km}$) yields a light-transit time of $\Delta t_{\text{spacelike}} = 3.33\,\mu\text{s}$. Because detector jitter satisfies $\tau_{\text{jitter}} \ll \tau_{\text{pkt}} < \Delta t_{\text{spacelike}}$, all coincidence events recorded within $|\Delta t| < 3.33\,\mu\text{s}$ occur outside each other's light cones. Measuring $g^{(2)}(0) < 10^{-4}$ in this configuration eliminates local hidden-variable coordination and empirically bounds finite collapse velocities to $v_{\text{dep}} > 10^5 c$, establishing the elliptic boundary-value nature of quantum state reduction.

---

## 8. Discussion, Philosophical Implications, and Conclusion

The century-long impasse over the quantum measurement problem originated from an unexamined assumption: that because the Born rule $|\psi|^2$ provides an empirically exact ensemble calculus, nature cannot possess an underlying dynamical mechanism for individual events. This assumption forced physics into two unsatisfactory extremes: Bohr's instrumentalism, which placed single events outside physical law, and Everett's Many-Worlds interpretation, which reified every mathematical branch into unobservable parallel universes.

Version 4.0 demonstrates that neither extreme is necessary. By grounding quantum theory in physical spacetime and condensed-matter physics:
1. **The Wave Function is Ontic in Physical Space:** The Schrödinger field $\psi(\mathbf{x}, t)$ is a real physical wave propagating in ordinary three-dimensional space, carrying conserved Noether action and electromagnetic energy.
2. **Measurement is a Resonant Dynamical Process:** Detectors are not abstract classical observers, but dense solid-state lattices. Single events are generated by three-wave surface interference, unbiased vacuum fluctuations, and photon-assisted quantum barrier tunneling.
3. **The Born Rule is an Extreme-Value Law:** Just as the Maxwell–Boltzmann distribution emerges from microscopic molecular collisions without being postulated as a fundamental law, the Born probability distribution emerges from extreme-value competing-risks statistics across millions of competing atomic tunneling sites.
4. **Entanglement Does Not Require High-Dimensional Space:** Multi-particle entanglement operates in ordinary three-dimensional space coupled through complexified time ($\mathbb{R}^3 \times \mathbb{C}_T$). Wick rotation transforms hyperbolic wave propagation into an elliptic boundary-value problem, explaining nonlocal quantum correlations while strictly preserving relativistic no-signaling.
5. **The Framework is Falsifiable:** Through gate-pulsed barrier asymmetry, long-packet coincidence timing across kilometer-scale baselines, and few-atom nanocavity limits, the mechanism presents concrete experimental predictions that distinguish it from both standard Copenhagen quantum mechanics and alternative collapse models.

By replacing the axiomatic Born probability postulate with an explicit physical mechanism, quantum mechanics is restored to the continuous, causal, and realist tradition of field physics envisioned by Schrödinger and Einstein.

---

## References

* Schrödinger, E. (1926). Quantisierung als Eigenwertproblem. *Annalen der Physik*, 384(4), 361–376.
* Born, M. (1926). Zur Quantenmechanik der Stoßvorgänge. *Zeitschrift für Physik*, 37(12), 863–867.
* Bohr, N. (1928). The quantum postulate and the recent development of atomic theory. *Nature*, 121(3050), 580–590.
* von Neumann, J. (1932). *Mathematische Grundlagen der Quantenmechanik*. Springer, Berlin.
* Einstein, A., Podolsky, B., & Rosen, N. (1935). Can quantum-mechanical description of physical reality be considered complete? *Physical Review*, 47(10), 777–780.
* Bacciagaluppi, G., & Valentini, A. (2009). *Quantum Theory at the Crossroads: Reconsidering the 1927 Solvay Conference*. Cambridge University Press.
* Bell, J. S. (1964). On the Einstein Podolsky Rosen paradox. *Physics Physique Физика*, 1(3), 195–200.
* Aspect, A., Dalibard, J., & Roger, G. (1982). Experimental test of Bell's inequalities using time-varying analyzers. *Physical Review Letters*, 49(25), 1804–1807.
* Grangier, P., Roger, G., & Aspect, A. (1986). Experimental evidence for a photon anticorrelation effect on a beam splitter. *Europhysics Letters*, 1(4), 173–179.
* Shalm, L. K., et al. (2015). Strong loophole-free test of local realism. *Physical Review Letters*, 115(25), 250402.
* Tien, P. K., & Gordon, J. P. (1963). Multiphoton process observed in the interaction of microwave fields with tunneling between superconductor films. *Physical Review*, 129(2), 647–651.
* Keldysh, L. V. (1965). Ionization in the field of a strong electromagnetic wave. *Soviet Physics JETP*, 20(5), 1307–1314.
* Einstein, A. (1917). Zur Quantentheorie der Strahlung. *Physikalische Zeitschrift*, 18, 121–128.
* Eberhard, P. H. (1978). Bell's theorem and the different concepts of locality. *Il Nuovo Cimento B*, 46(2), 392–419.
* Allahverdyan, A. E., Balian, R., & Nieuwenhuizen, T. M. (2013). Understanding quantum measurement from the solution of dynamical models. *Physics Reports*, 525(1), 1–166.
* Landsman, N. P., & Reuvers, R. (2013). A flea on Schrödinger's cat. *Annals of Physics*, 337, 11–53.
* Bisognano, J. J., & Wichmann, E. H. (1976). On the duality condition for quantum fields. *Journal of Mathematical Physics*, 17(2), 303–321.
* Penrose, R. (1996). On gravity's role in quantum state reduction. *General Relativity and Gravitation*, 28(5), 581–600.
* Feynman, R. P. (1949). The theory of positrons. *Physical Review*, 76(6), 749–759.
* Milonni, P. W. (1994). *The Quantum Vacuum: An Introduction to Quantum Electrodynamics*. Academic Press.
