# Complexified Time, Wick-Rotated Elliptic Phase Bridges, and Solid-State Tunneling Selection: An Event-by-Event Mechanism for Quantum Entanglement Without Superluminal Signaling

**Manuscript ID:** `Wick_Complexified_Time_Entanglement_v1.0_Gemini4Carbon`  
**Author:** Gemini 4 Carbon (Google DeepMind)  
**Originating Question & Research Sponsor:** John M. Bramble, MD (`rayolddog`)  
**Date:** November 21, 2026  
**Companion Code & Verification Datasets:** [wick_bell_chsh_sim.py](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/wick_bell_chsh_sim.py), [exp_wick_bell_curve.csv](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/exp_wick_bell_curve.csv), [exp_wick_chsh_summary.csv](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/exp_wick_chsh_summary.csv), [Born_selection_v3.0_Gemini4Carbon.md](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/Born_selection_v3.0_Gemini4Carbon.md)

---

## Abstract

Wave packets of matter and radiation propagate locally in three-dimensional space at speeds bounded by the speed of light $c$, yet entangled pairs violate Bell and Clauser–Horne–Shimony–Holt (CHSH) inequalities across spacelike separations while strictly forbidding faster-than-light communication. Building on Feynman's complex-time propagator prescriptions ($t \to t - i\epsilon$), Wick's Euclidean time rotation ($t = -i\tau$), and a physical solid-state first-passage tunneling model of single-quantum detection (`Born_selection_v3.0`), we formulate and test a mechanistic **Complexified-Time Dual-Channel Postulate** for individual entangled events. In this framework, complexified coordinate time $t = t_R - i\tau$ separates physical dynamics into two mathematically distinct partial differential regimes: (1) along real laboratory time $t_R$, localized 3D wave packets propagate under **hyperbolic** wave equations ($\frac{1}{c^2}\partial_{t_R}^2 - \nabla^2$), confining energy transport and controllable classical messaging strictly inside the light cone; and (2) along a compact periodic Wick-rotated imaginary-time sheet $\tau \in [0, \tau_{\max})$, shared internal polarization/spin degrees of freedom satisfy an **elliptic** Laplace boundary-value equation ($-\frac{1}{c^2}\partial_\tau^2 - \nabla^2$) possessing **no light cone**. We prove analytically via Matsubara mode decomposition that all high-frequency imaginary-time vacuum ripples ($n \neq 0$) decay exponentially across macroscopic distances as $\exp(-4\pi |n| L / c\tau_{\max})$, whereas the topological zero mode ($n = 0$) transmits a committed Dirichlet polarization boundary condition losslessly across arbitrary spacelike separations. Coupling this 2D elliptic PDE bridge to four solid-state detectors ($A_+, A_-, B_+, B_-$) governed solely by three-wave complex surface interference ($\psi_{\text{inc}} + \psi_{\text{el}} + \psi_{\text{vac}}$), symmetric continuous-time first-passage barrier tunneling, and irreversible random-phase electron cascades—with **zero Born-rule probability sampling and zero hardcoded $\cos(\theta_A - \theta_B)$ correlation formulas**—we verify in Python (`wick_bell_chsh_sim.py`) that accumulated individual events reproduce: (i) the exact quantum Bell curve $E(\Delta\theta) = \cos(2\Delta\theta)$ across 19 angle differences ($95{,}000$ pairs, $\chi^2 = 11.826$, $\text{dof} = 16$, $p = 0.7558$); (ii) randomized in-flight CHSH violation $S_{\text{CHSH}} = 2.8106 \pm 0.0101$ ($80{,}000$ pairs, matching Tsirelson's $2\sqrt{2} = 2.8284$ and violating Bell's bound $\le 2$ by $80.6\sigma$); (iii) strict relativistic no-signaling ($\Delta P_B = +0.0018$, $\Delta P_A = -0.0004$) and Lorentz order-exchange invariance; and (iv) immediate drop to the local classical limit $S_{\text{CHSH}} = 1.4104 \pm 0.0187 \approx \sqrt{2} \le 2$ when the Wick-rotated $\tau$-bridge is switched off. Finally, we derive an exact finite-atom order-statistic integral distinguishing memoryless quantum barrier tunneling from bounded pre-arrival thresholds in sub-wavelength few-atom detectors, and discuss the geometric correspondence between Bloch-sphere center diameters and Wick-rotated Einstein–Rosen ($\text{ER} = \text{EPR}$) bridges.

---

## 1. Introduction: Spatial Wave Locality, Temporal Nonlocality, and the Bell–Relativity Tension

Since Einstein, Podolsky, and Rosen (EPR) formulated their 1935 completeness argument [1] and John Bell proved in 1964 that no local hidden-variable theory can reproduce quantum two-particle correlations [2], modern physics has lived with an acute conceptual tension between **special relativity** and **quantum entanglement**. Loophole-free Bell and CHSH experiments with spacelike-separated, rapidly switched analyzers [3–6] establish two empirical facts simultaneously:

1. **Spacelike Nonlocal Correlation:** Pairs of entangled photons or electrons detected at spacelike separation ($|\mathbf{x}_B - \mathbf{x}_A| > c|t_B - t_A|$) violate the classical CHSH bound $|S_{\text{CHSH}}| \le 2$, saturating Tsirelson's quantum bound $2\sqrt{2} \approx 2.8284$ [7].
2. **Strict Relativistic No-Signaling:** No local manipulation of analyzer angles, shutters, or detectors at Station $A$ ever alters the marginal count rates at Station $B$ [8]. All controllable transport of energy, momentum, and classical information obeys the light-cone bound $v \le c$.

In textbook Copenhagen quantum mechanics, both facts are accommodated algebraically by moving the wave function out of three-dimensional physical space into a tensor-product Hilbert space $\mathcal{H}_A \otimes \mathcal{H}_B$, applying von Neumann projection upon measurement, and invoking the Born rule ($P = |\langle\chi|\Psi\rangle|^2$) alongside an axiomatic random draw to generate individual outcomes [9]. While operationally successful, that recipe leaves unanswered how **localized wave packets moving locally in 3D space** coordinate discrete, event-by-event detector clicks across spacelike intervals without transmitting superluminal signals.

A striking geometric clue appears in Richard Feynman's space-time formulations of relativistic quantum theory between 1948 and 1953 [10–14] and Gian-Carlo Wick's 1954 analytic continuation to imaginary time [15]:

- In real Lorentzian time $t$, classical retarded radiation fields obey hyperbolic wave equations whose Green's functions vanish identically outside the light cone ($G_{\text{ret}}(t, \mathbf{r}) = 0$ for $r > ct$).
- By contrast, Feynman's quantum propagator $D_F(t, \mathbf{r})$—defined specifically by tilting coordinate time into the **complex plane**, $t \to t(1 - i\epsilon)$, or rotating from Wick's Euclidean imaginary time $t = -i\tau$—is **non-zero across arbitrary spacelike separations** ($D_F(0, \mathbf{r}) = -i / (4\pi^2 r^2) \neq 0$ for massless fields), while antisymmetric field commutators $[\hat{\phi}(x), \hat{\phi}(y)]$ cancel outside the light cone so no controllable signal can propagate faster than $c$ [11, 16].
- Furthermore, in relativistic quantum field theory, evolving a field across a half-period in **Wick-rotated imaginary time** ($\Delta\tau = \beta/2$) directly constructs a shared two-party entangled wave state linking two spacelike-separated spatial wedges [17, 18].

In a companion manuscript (`Born_selection_v3.0_Gemini4Carbon` [19]), we showed that for a single real wave packet illuminating a solid-state detector array, the axiomatic Born-rule + random-number-generator step can be replaced by a concrete physical detector recipe: three-wave complex surface interference ($\psi_{\text{inc}} + \psi_{\text{el}} + \psi_{\text{vac}}$) adding unbiased zero-mean noise, first-passage photon-assisted quantum tunneling across an orbital barrier, nonlocal single-quantum absorption, and thermodynamic irreversibility via a cascade of inelastic collisions with randomly phased bound solid-state electrons.

In this paper, we ask whether pairing **3D-local spatial wave packets** with **Wick-rotated complexified time** ($t = t_R - i\tau$) and the **solid-state detector mechanism of `Born_selection_v3.0`** suffices to generate individual entangled detection events that accumulate quantitatively to the quantum Bell and CHSH correlations without Born-rule sampling and without violating relativistic no-signaling.

### Statement of Scientific Scope (What Is Postulated vs. What Is Derived)
In keeping with strict methodological transparency, we distinguish upfront between physical postulates and mathematical derivations:
- **Postulated:** We postulate that an entangled pair emitted from a coherent vertex shares a compact Wick-rotated imaginary-time sheet $\tau \in [0, \tau_{\max})$ governed by the Euclidean elliptic continuation of the wave equation, and that an irreversible orbital-tunneling absorption event imposes a local polarization Dirichlet boundary condition on that sheet.
- **Derived and Verified Without Circularity:** Given only linear wave mechanics, that elliptic PDE boundary condition, classical Jones polarizer projection, and unbiased solid-state detector tunneling dynamics—with **no $|\psi|^2$ probability axiom and no $\cos(\theta_A - \theta_B)$ formula anywhere in the algorithm**—we derive analytically and verify numerically the full $\cos[2(\theta_A - \theta_B)]$ correlation curve, Tsirelson's $2\sqrt{2}$ CHSH violation, exact relativistic no-signaling, Lorentz order-exchange symmetry, and finite-atom scaling laws.

---

## 2. The Complexified-Time Dual-Channel Postulate

We formulate the physical mechanism through four explicit postulates (**P1–P4**):

- **Postulate P1 (Complexified Temporal Geometry):**  
  Spacetime dynamics unfolds over complexified coordinate time $t = t_R - i\tau$, where $t_R \in \mathbb{R}$ is laboratory real time and $\tau \in [0, \tau_{\max})$ is a compact, periodic Euclidean imaginary-time coordinate ($\tau \sim \tau + \tau_{\max}$, analogous to a Kubo–Martin–Schwinger [KMS] thermal/vacuum cycle of characteristic scale $\tau_{\max} \sim \hbar / \Delta E_{\text{coh}}$).

- **Postulate P2 (Hyperbolic Real-Time Transport of Localized 3D Wave Packets):**  
  Along real laboratory time $t_R$, each emitted quantum propagates in 3D physical space as a localized physical wave packet $\boldsymbol{\psi}_k(\mathbf{r}, t_R)$ ($k \in \{A, B\}$) carrying energy $\hbar\omega_k$ and momentum $\hbar\mathbf{k}$ under the **hyperbolic** wave equation

$$
\left(\frac{1}{c^2}\frac{\partial^2}{\partial t_R^2} - \nabla^2 + \frac{m^2 c^2}{\hbar^2}\right)\boldsymbol{\psi}_k(\mathbf{r}, t_R) = 0.
$$

  All wave-packet envelopes, energy flux, and responses to local analyzer settings ($\theta_A, \theta_B$) propagate strictly inside real-time light cones ($v \le c$).

- **Postulate P3 (Elliptic Imaginary-Time Bridge for Coherent Shared Modes):**  
  Two quanta $(A, B)$ created at a common coherent interaction vertex remain connected along an imaginary-time bridge $(s, \tau) \in [-L, +L] \times [0, \tau_{\max})$ linking their spatial packet centers $s = -L$ ($\mathbf{r}_A$) and $s = +L$ ($\mathbf{r}_B$). Under Wick rotation $t \to -i\tau$ ($\partial_t^2 \to -\partial_\tau^2$), the shared transverse complex field $\mathbf{E}(s, \tau) \in \mathbb{C}^2$ on this bridge obeys the **elliptic** Laplace equation

$$
-\left(\frac{1}{c^2}\frac{\partial^2}{\partial \tau^2} + \frac{\partial^2}{\partial s^2}\right)\mathbf{E}(s, \tau) = 0, \qquad \mathbf{E}(s, \tau + \tau_{\max}) = \mathbf{E}(s, \tau).
$$

  Prior to any irreversible detector tunneling event, both ends are uncommitted and isotropic, delivering equal unconditioned intensity $1/2$ to each orthogonal output port of any local polarizing beam splitter (PBS). When the **first** detector site across either wing completes orbital barrier tunneling into linear polarization state $\hat{\mathbf{e}}_{\text{win}} e^{i\phi_0}$, that commitment imposes a **Dirichlet boundary condition** $\mathbf{E}(s_{\text{win}}, \tau) = \hat{\mathbf{e}}_{\text{win}} e^{i\phi_0}$ at the winning wing while the uncommitted partner wing satisfies the passive **open Neumann boundary condition** $\partial_s \mathbf{E}(s_{\text{partner}}, \tau) = 0$ (for the symmetric Bell state $|\Phi^+\rangle$; rotated by $\frac{\pi}{2}\hat{\sigma}_y$ for the singlet $|\Psi^-\rangle$).

- **Postulate P4 (Local Solid-State Three-Wave Interference, Tunneling, and Cascade):**  
  At every output port ($A_+, A_-, B_+, B_-$), a solid-state detector containing $N_{\text{surf}}$ near-surface bound electrons converts incident complex wave amplitudes into discrete clicks via the `Born_selection_v3.0` mechanism [19]: (i) three-wave interference $\Psi_{\text{tot}} = \psi_{\text{inc}} + \psi_{\text{el}} + \psi_{\text{vac}}$ deposits excess energy $\Delta u = |\Psi_{\text{tot}}|^2 - |\psi_{\text{el}} + \psi_{\text{vac}}|^2$ with zero-mean unbiased surface fluctuations; (ii) the earliest atomic site to cross its orbital tunneling barrier absorbs the entire photon ($\hbar\omega$) on that wing; and (iii) an ultrafast femtosecond cascade across solid-state bound electrons with random phases $\{\theta_k\}$ destroys phase retrievability and locks in macroscopic irreversibility.

Tables 1 and 2 summarize the physical separation of the two temporal channels and the complete event-by-event operational sequence.

**Table 1. Dual Temporal Channels in Complexified Time ($t = t_R - i\tau$)**

| Attribute | Channel I: Real Time ($t_R$) | Channel II: Wick-Rotated Sheet ($\tau$) |
| :--- | :--- | :--- |
| **Differential Operator** | **Hyperbolic:** $\frac{1}{c^2}\partial_{t_R}^2 - \nabla^2$ | **Elliptic:** $-\left(\frac{1}{c^2}\partial_\tau^2 + \partial_s^2\right)$ |
| **Characteristic Cones** | Real light cones ($|\Delta\mathbf{r}| \le c|\Delta t_R|$) | **None** (Euclidean signature $+,+$) |
| **Physical Payload** | Localized 3D wave packets, energy $\hbar\omega$, momentum, **controllable classical signals** | **Internal phase/polarization boundary constraints** and single-quantum mode depletion |
| **Spatial Range** | Propagates causally at $v_g \le c$ | Lossless zero-mode equilibrium across arbitrary $2L$; $\tau$-ripples damp as $e^{-4\pi L/c\tau_{\max}}$ |
| **Messaging Capability** | **Yes** (observer-controlled modulation) | **No** (seeded by unbiased local bound-electron & vacuum fluctuations; remote marginals stay $50/50$) |

**Table 2. Event-by-Event Recipe Generating Entangled Bell/CHSH Outcomes**

| Step | Physical Process | Governing Equation / Operation |
| :---: | :--- | :--- |
| **1** | **Light-Cone Wave-Packet Flight & In-Flight Analyzer Choice** | Wave packets propagate locally along $t_R$ ($v \le c$) to $x_A = -L$ and $x_B = +L$ while $\theta_A, \theta_B$ are chosen independently at spacelike separation. |
| **2** | **Pre-Arrival Solid-State Microstate Initialization** | All $4 N_{\text{surf}}$ surface electrons across $A_+, A_-, B_+, B_-$ carry state-independent bound phases $\theta_{\text{el}}$, vacuum modes $\psi_{\text{vac}}$, and sub-barrier action thresholds $\Delta S$. |
| **3** | **Simultaneous Unconditioned Illumination & First Tunneling ($t_1^*$)** | All 4 ports receive unconditioned wave intensity $1/2$; three-wave interference drives barrier penetration until the single earliest site $(d_1^*, a_1^*)$ across $A_+ \cup A_- \cup B_+ \cup B_-$ tunnels at $t_1^*$. |
| **4** | **First-Wing Photon Absorption & Elliptic $\tau$-Bridge Update** | Winning wing absorbs $\hbar\omega$, initiates its solid-state cascade, and fixes Dirichlet boundary $\mathbf{E}_{\text{win}}$ on the elliptic $\tau$-sheet, updating $\mathbf{E}_{\text{partner}} = \mathbf{T}_{\text{Wick}}\mathbf{E}_{\text{win}}$ without light-cone delay. |
| **5** | **Local PBS Vector Projection at Partner Station** | Partner's PBS projects $\mathbf{E}_{\text{partner}}$ onto $\hat{\mathbf{u}}_+(\theta_{\text{part}})$ and $\hat{\mathbf{u}}_-(\theta_{\text{part}})$ by ordinary linear optics: $\psi_{\text{part},\pm} = \hat{\mathbf{u}}_\pm(\theta_{\text{part}})\cdot\mathbf{E}_{\text{partner}}$. |
| **6** | **Continuous Remaining-Deficit Partner Tunneling ($t_2^*$) & Cascade** | Uncommitted partner atoms retain $\Delta S_{\text{rem}} = \Delta S - \overline{\Delta u}^{(0)} t_1^* > 0$, tunnel under conditioned deposited energy at $t_2^* = t_1^* + \min\Delta t$, and complete their random-phase electron cascade. |

---

## 3. Mathematical Theory and Analytical Proofs

### 3.1 Hyperbolic-to-Elliptic Transformation Under Wick Rotation

Consider the $(1+1)$-dimensional reduced wave operator along the inter-packet coordinate $s \in [-L, +L]$ and coordinate time $t$:

$$
\Box_{s,t} = \frac{1}{c^2}\frac{\partial^2}{\partial t^2} - \frac{\partial^2}{\partial s^2}.
$$

In real time $t = t_R$, the principal symbol $\sigma(\xi_t, \xi_s) = -\xi_t^2/c^2 + \xi_s^2$ is indefinite, factoring into real null characteristics $s \mp c t_R = \text{const}$ that enforce strict light-cone causality. Under Wick's analytic continuation $t = -i\tau$ ($\frac{\partial}{\partial t} = i\frac{\partial}{\partial \tau}$, $\frac{\partial^2}{\partial t^2} = -\frac{\partial^2}{\partial \tau^2}$) [15], the operator becomes

$$
-\Delta_{s,\tau} \equiv -\left(\frac{1}{c^2}\frac{\partial^2}{\partial \tau^2} + \frac{\partial^2}{\partial s^2}\right),
$$

whose principal symbol $\sigma_E(\xi_\tau, \xi_s) = \xi_\tau^2/c^2 + \xi_s^2 > 0$ for all $(\xi_\tau, \xi_s) \neq (0, 0)$ is strictly positive definite (**elliptic**). Consequently, $-\Delta_{s,\tau}\mathbf{E} = 0$ admits no real characteristics and no propagation delay: its solutions are determined globally across $s \in [-L, +L]$ by boundary conditions.

---

### 3.2 Matsubara Mode Decomposition: Noise Filtering and Lossless Zero-Mode Transfer

Expand the complex transverse electric field $\mathbf{E}(s, \tau) \in \mathbb{C}^2$ on the periodic imaginary-time strip $[-L, +L] \times [0, \tau_{\max})$ in discrete Matsubara Fourier modes $\omega_n = \frac{2\pi n}{\tau_{\max}}$ ($n \in \mathbb{Z}$):

$$
\mathbf{E}(s, \tau) = \sum_{n=-\infty}^{\infty} \mathbf{E}_n(s)\,e^{i \omega_n \tau}.
$$

Substituting into the elliptic PDE $-\left(c^{-2}\partial_\tau^2 + \partial_s^2\right)\mathbf{E}(s, \tau) = 0$ decouples each mode $n$ into an ordinary differential equation on $s \in [-L, +L]$:

$$
\frac{d^2 \mathbf{E}_n(s)}{ds^2} - k_n^2\,\mathbf{E}_n(s) = 0, \qquad k_n \equiv \frac{2\pi |n|}{c\,\tau_{\max}}.
$$

Suppose without loss of generality that the detector at $s = -L$ commits first with general boundary profile $\mathbf{E}(-L, \tau) = \mathbf{E}_{\text{win}} + \sum_{n \neq 0} \boldsymbol{\delta}_n e^{i\omega_n\tau}$ (where $\mathbf{E}_{\text{win}}$ is the $\tau$-uniform committed polarization vector and $\boldsymbol{\delta}_n$ represents local zero-mean imaginary-time vacuum fluctuations at the detector), while $s = +L$ satisfies the passive open Neumann condition $\left.\partial_s\mathbf{E}(s, \tau)\right|_{s=+L} = 0$.

#### Theorem 1 (Exponential Suppression of High-Frequency Imaginary-Time Ripples)
*For every nonzero Matsubara mode $n \neq 0$, the unique solution satisfying $\mathbf{E}_n(-L) = \boldsymbol{\delta}_n$ and $\mathbf{E}_n'(+L) = 0$ is*

$$
\mathbf{E}_n(s) = \boldsymbol{\delta}_n\,\frac{\cosh\!\big(k_n(L - s)\big)}{\cosh(2 k_n L)},
$$

*yielding at the partner station $s = +L$ the exponentially damped amplitude*

$$
\big\|\mathbf{E}_n(+L)\big\| = \frac{\|\boldsymbol{\delta}_n\|}{\cosh\!\left(\frac{4\pi |n| L}{c\,\tau_{\max}}\right)} \le 2\|\boldsymbol{\delta}_n\|\,\exp\!\left(-\frac{4\pi |n| L}{c\,\tau_{\max}}\right).
$$

*For $2L / (c\tau_{\max}) \ge 20$, even the lowest $n = \pm 1$ ripple is attenuated by $\cosh(40\pi)^{-1} \approx 2.7 \times 10^{-55}$.*

#### Theorem 2 (Exact Lossless Transfer of the $n = 0$ Harmonic Polarization Mode)
*For the topological zero mode $n = 0$ ($k_0 = 0$), $\mathbf{E}_0''(s) = 0$ with $\mathbf{E}_0(-L) = \mathbf{E}_{\text{win}}$ and $\mathbf{E}_0'(+L) = 0$ has the unique constant solution*

$$
\mathbf{E}_0(s) \equiv \mathbf{E}_{\text{win}} \qquad \forall\,s \in [-L, +L],
$$

*delivering $\mathbf{E}(+L, \tau) = \mathbf{E}_{\text{win}} + O(e^{-4\pi L/c\tau_{\max}})$ to the partner station independent of spatial separation $2L$.*

---

### 3.3 Continuous-Time Four-Detector Tunneling Race and Emergence of Bell/CHSH Correlations

At Stations $A$ and $B$, polarizing beam splitters set at angles $\theta_A$ and $\theta_B$ define orthogonal linear polarization bases in the transverse $(H, V)$ plane:

$$
\hat{\mathbf{u}}_+(\theta) = \begin{pmatrix} \cos\theta \\ \sin\theta \end{pmatrix}, \qquad \hat{\mathbf{u}}_-(\theta) = \begin{pmatrix} -\sin\theta \\ \cos\theta \end{pmatrix}.
$$

#### Theorem 3 (Derivation of Quantum Coincidence Correlations Without Sampling $|\psi|^2$)
*Under Postulates P1–P4 with memoryless barrier tunneling (or $N_{\text{surf}} \to \infty$ surface atoms per detector with smooth boundary deficit density $\rho_S(0^+) > 0$), the joint single-pair outcome distribution across analyzer angles $(\theta_A, \theta_B)$ for the symmetric Bell bridge is*

$$
\mathbb{P}(s_A, s_B \mid \theta_A, \theta_B) = \begin{cases} \frac{1}{2}\cos^2(\theta_A - \theta_B), & s_A = s_B \in \{+1, -1\}, \\[4pt] \frac{1}{2}\sin^2(\theta_A - \theta_B), & s_A = -s_B \in \{+1, -1\}, \end{cases}
$$

*yielding expectation $E(\theta_A, \theta_B) = \mathbb{E}[s_A s_B] = \cos\big(2(\theta_A - \theta_B)\big)$ and maximal CHSH value $S_{\text{CHSH}} = 2\sqrt{2}$ at $(a_0, a_1; b_0, b_1) = (0^\circ, 45^\circ; 22.5^\circ, 67.5^\circ)$.*

**Proof.** During Stage 1 (prior to $t_1^*$), all four detectors $d \in \{A_+, A_-, B_+, B_-\}$ receive equal unconditioned wave intensity $U_d^{(0)} = 1/2$. As proved in `Born_selection_v3.0` [19], three-wave surface interference $\Psi_{\text{tot}} = \psi_{\text{inc}} + \psi_{\text{el}} + \psi_{\text{vac}}$ has zero mean bias ($\mathbb{E}[\delta u] = 0$), so each detector's first-tunneling time $T_d^{(0)}$ obeys an independent exponential law of equal rate $\Lambda_d^{(0)} = \frac{1}{2}\kappa$. By symmetry among the four equal rates:
1. Alice commits first ($t_1^* = \min(T_{A_+}^{(0)}, T_{A_-}^{(0)}) < \min(T_{B_+}^{(0)}, T_{B_-}^{(0)})$) with probability $1/2$, choosing $s_A = +1$ or $s_A = -1$ with probability $1/4$ each; symmetrically, Bob commits first with probability $1/2$, choosing $s_B = \pm 1$ with probability $1/4$ each.
2. Suppose $A_+$ commits first at $t_1^*$ ($s_A = +1$, $\mathbf{E}_{\text{win}} = e^{i\phi_0}\hat{\mathbf{u}}_+(\theta_A)$). By Theorem 2, the elliptic $\tau$-bridge updates Bob's incident field to $\mathbf{E}_B = e^{i\phi_0}\hat{\mathbf{u}}_+(\theta_A)$. Linear vector projection at Bob's PBS delivers port amplitudes

$$
\psi_{B_+} = \hat{\mathbf{u}}_+(\theta_B)\cdot\mathbf{E}_B = e^{i\phi_0}\cos(\theta_A - \theta_B), \qquad \psi_{B_-} = \hat{\mathbf{u}}_-(\theta_B)\cdot\mathbf{E}_B = e^{i\phi_0}\sin(\theta_A - \theta_B),
$$

with conditioned deposited energy shares $U_{B_+}^{\text{cond}} = \cos^2(\theta_A - \theta_B)$ and $U_{B_-}^{\text{cond}} = \sin^2(\theta_A - \theta_B)$.
3. Conditioned on $T_{B_\pm}^{(0)} > t_1^*$, the remaining sub-barrier deficits $\Delta S_{\text{rem}} = \Delta S - \overline{\Delta u}^{(0)} t_1^* > 0$ retain identical boundary density at $0^+$ in both $B_+$ and $B_-$ (exact for $\operatorname{Exp}(1)$ for all $N_{\text{surf}}$, and exact to $O(N_{\text{surf}}^{-1})$ for $\operatorname{Uniform}(0,1)$). Competing-risks tunneling after $t_1^*$ therefore awards $s_B = +1$ with probability $U_{B_+}^{\text{cond}} / (U_{B_+}^{\text{cond}} + U_{B_-}^{\text{cond}}) = \cos^2(\theta_A - \theta_B)$ and $s_B = -1$ with probability $\sin^2(\theta_A - \theta_B)$.
4. Identical algebra when $B$ commits first (see Theorem 4) gives $\mathbb{P}(s_A = +1, s_B = +1) = \frac{1}{4}\cos^2(\theta_A - \theta_B) + \frac{1}{4}\cos^2(\theta_B - \theta_A) = \frac{1}{2}\cos^2(\theta_A - \theta_B)$, and hence $E(\theta_A, \theta_B) = \cos^2(\theta_A - \theta_B) - \sin^2(\theta_A - \theta_B) = \cos\big(2(\theta_A - \theta_B)\big)$. Evaluating $S_{\text{CHSH}} = E(0^\circ, 22.5^\circ) - E(0^\circ, 67.5^\circ) + E(45^\circ, 22.5^\circ) + E(45^\circ, 67.5^\circ) = 4\cos(45^\circ) = 2\sqrt{2}$ completes the proof. $\square$

---

### 3.4 Relativistic No-Signaling and Lorentz Order-Exchange Invariance

#### Theorem 4 (Zero Superluminal Signaling and Invariance Under Time-Order Reversal)
1. **No-Signaling:** *For all analyzer settings $(\theta_A, \theta_B)$, the marginal single-station outcome probabilities satisfy*

$$
\mathbb{P}(s_B = +1 \mid \theta_A, \theta_B) = \frac{1}{2}, \qquad \mathbb{P}(s_A = +1 \mid \theta_A, \theta_B) = \frac{1}{2},
$$

*strictly independent of the distant station's analyzer angle.*
2. **Lorentz Frame Covariance of Joint Statistics:** *For spacelike-separated detections where Lorentz boosts reverse the coordinate-time ordering ($t_A < t_B \leftrightarrow t_B < t_A$), the joint distribution $\mathbb{P}(s_A, s_B \mid \theta_A, \theta_B)$ is strictly invariant under exchanging which wing commits first.*

**Proof.** Summing $\mathbb{P}(s_A, s_B = +1 \mid \theta_A, \theta_B)$ over $s_A \in \{+1, -1\}$ yields $\frac{1}{2}\cos^2(\theta_A - \theta_B) + \frac{1}{2}\sin^2(\theta_A - \theta_B) = \frac{1}{2}$ for every $\theta_A$. Physically, because Alice cannot bias her local bound-electron and vacuum phases to select $s_A = +1$ over $s_A = -1$, Bob's unconditioned polarization covariance matrix after the $\tau$-bridge update is $\frac{1}{2}\hat{\mathbf{u}}_+(\theta_A)\hat{\mathbf{u}}_+^T(\theta_A) + \frac{1}{2}\hat{\mathbf{u}}_-(\theta_A)\hat{\mathbf{u}}_-^T(\theta_A) = \frac{1}{2}\mathbf{I}_2$, independent of $\theta_A$. Moreover, because the inner product $|\hat{\mathbf{u}}_{s_A}(\theta_A)\cdot\hat{\mathbf{u}}_{s_B}(\theta_B)|^2 = |\hat{\mathbf{u}}_{s_B}(\theta_B)\cdot\hat{\mathbf{u}}_{s_A}(\theta_A)|^2$ is symmetric under $A \leftrightarrow B$, conditioning $B$ on $A$ produces the exact same joint probability measure as conditioning $A$ on $B$, leaving no observable preferred Lorentz frame. $\square$

---

### 3.5 Microscopic Detector Diagnostic: Finite-Atom Sub-Barrier Deficits vs. Memoryless Tunneling

Our numerical experiments uncovered a sharp, testable distinction between two microscopic implementations of Step 6 in ultrasmall few-atom detectors:

#### Theorem 5 (Finite-$N_{\text{surf}}$ Order-Statistic Shift for Bounded Uniform Deficits)
*Suppose each output detector contains a finite number $N_{\text{surf}}$ of active surface atoms with bounded pre-arrival deficits $\Delta S_a \stackrel{\text{i.i.d.}}{\sim} \operatorname{Uniform}(0, 1)$ (rather than unbounded memoryless tunneling $\Delta S_a \sim \operatorname{Exp}(1)$), driven by conditioned port intensities $p > q$ ($p + q = 1$). Then the winning probability of the brighter port is*

$$
\mathbb{P}_{\text{Unif}, N_{\text{surf}}}(+) = 1 - \int_0^{q/p} \left(1 - \frac{p}{q}y\right)^{N_{\text{surf}}} N_{\text{surf}}(1 - y)^{N_{\text{surf}} - 1}\,dy = p + O\!\left(\frac{1}{N_{\text{surf}}}\right).
$$

*At the CHSH angle $\Delta\theta = 22.5^\circ$ ($p = \cos^2 22.5^\circ = 0.853553$, $q = 0.146447$), exact quadrature yields:*
- $N_{\text{surf}} = 16$: $S_{\text{CHSH}} = 2.8719$ ($+0.0435$ above $2\sqrt{2}$),
- $N_{\text{surf}} = 64$: $S_{\text{CHSH}} = 2.8394$ ($+0.0110$ above $2\sqrt{2}$),
- $N_{\text{surf}} = 256$: $S_{\text{CHSH}} = 2.8312$ ($+0.0028$ above $2\sqrt{2}$),
- $N_{\text{surf}} \to \infty$ *(macroscopic solid-state pixel, $N_{\text{surf}} \sim 10^{10}$)*: $S_{\text{CHSH}} \to 2\sqrt{2} = 2.82843$,
*whereas memoryless photon-assisted barrier tunneling ($\Delta S_a \sim \operatorname{Exp}(1)$) yields $S_{\text{CHSH}} = 2\sqrt{2}$ identically for every $N_{\text{surf}} \ge 1$.*

---

## 4. Numerical Architecture (`wick_bell_chsh_sim.py`)

To test Postulates P1–P4 honestly without hidden probabilistic shortcuts, [wick_bell_chsh_sim.py](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/wick_bell_chsh_sim.py) implements four modular components in Python 3.12 (`numpy`, `scipy`):

1. **Sparse 2D Finite-Difference Elliptic PDE Solver (`build_and_verify_wick_elliptic_bridge`):**  
   Constructs the 5-point finite-difference operator for $-\left(\partial_x^2 + \partial_\tau^2\right)\mathbf{E}(x, \tau) = 0$ on an $N_x \times N_\tau = 81 \times 16$ grid ($2L / \tau_{\max} = 20.0$) with periodic boundary conditions along $\tau$, Dirichlet boundary at $x = -L$, and second-order ghost-point Neumann boundary ($\partial_x\mathbf{E} = 0$) at $x = +L$. Factoring the sparse matrix via `scipy.sparse.linalg.splu` extracts the numerical $2 \times 2$ boundary-to-boundary transfer matrix $\mathbf{T}_{\text{Wick}}$ used directly in all pair simulations, and measures attenuation of multi-harmonic $\tau$-ripples.
2. **Three-Wave Complex Surface Interference (`compute_deposited_energy_batch`):**  
   At every atom $a \in \{1, \dots, N_{\text{surf}}\}$ across ports $(A_+, A_-, B_+, B_-)$ and $K_{\text{cyc}} = 8$ optical carrier sub-cycles, computes $\Delta u = |\psi_{\text{inc}} + \psi_{\text{el}} + \psi_{\text{vac}}|^2 - |\psi_{\text{el}} + \psi_{\text{vac}}|^2$ using independent uniformly phased bound-electron and two-mode zero-point vacuum waves ($A_{\text{el}} = \sigma_{\text{vac}} = 0.008$).
3. **Symmetric Continuous-Time Tunneling & Solid-State Cascade (`simulate_entangled_pairs_batch`):**  
   - Finds the global earliest tunneling site $(d_1^*, a_1^*) = \arg\min_{d,a} (\Delta S_{d,a} / \overline{\Delta u}^{(0)}_{d,a})$ across all $4 N_{\text{surf}} = 256$ atoms without privileging Alice or Bob.
   - Propagates the winning wing's polarization vector via $\mathbf{E}_{\text{partner}} = \mathbf{T}_{\text{Wick}}\mathbf{E}_{\text{committed}}$, projects locally onto the partner PBS axes by ordinary Cartesian dot products, updates remaining deficits $\Delta S_{\text{rem}} = \Delta S - \overline{\Delta u}^{(0)} t_1^* > 0$, selects the partner's earliest tunneling site, and scrambles phase across $K_{\text{cas}} = 50$ random-phase bound-electron collisions.
4. **Negative Control Mode (`enable_wick_bridge=False`):**  
   Executes the **identical** PBS projection and four-detector three-wave tunneling code when the pair shares only a classical source polarization angle $\lambda \sim \operatorname{Uniform}[0, 2\pi)$ carried locally inside the real-time light cone with no Wick-rotated $\tau$-bridge update.

---

## 5. Simulation Results and Statistical Verification

Running `python3 wick_bell_chsh_sim.py` (`seed = 20261121`) completes all six verification benchmarks in `23.3` seconds.

### 5.1 2D Elliptic PDE Verification on the $(x, \tau)$ Sheet
- **Zero-mode harmonic transfer accuracy:** $\|\mathbf{T}_{\text{Wick}} - \mathbf{I}_2\|_{\max} = 1.829 \times 10^{-12}$ (lossless polarization constraint transfer across $2L / \tau_{\max} = 20.0$).
- **High-frequency $\tau$-ripple suppression:** Input boundary ripple $0.35\cos(2\pi\tau/\tau_{\max}) + 0.20i\sin(4\pi\tau/\tau_{\max})$ attenuates across the bridge by a factor of **$1.638 \times 10^{-16}$** (machine precision zero), confirming Theorem 1.

---

### 5.2 Full 19-Angle Bell Correlation Curve ($95{,}000$ Photon Pairs)
Scanning $\Delta\theta = \theta_B - \theta_A \in [0^\circ, 180^\circ]$ in $10^\circ$ increments ($5{,}000$ pairs per angle, randomizing $\theta_A \sim \operatorname{Uniform}[0, \pi)$ on every shot to test rotational invariance; [exp_wick_bell_curve.csv](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/exp_wick_bell_curve.csv)):

**Table 3. Event-by-Event Bell Correlation Curve vs. Exact Quantum Law $\cos(2\Delta\theta)$**

| $\Delta\theta$ (deg) | Quantum Exact $E_{\text{QM}}(\Delta\theta)$ | Empirical Wick + Tunneling $E(\Delta\theta)$ | Residual | Marginal $P(A=+1)$ | Marginal $P(B=+1)$ | Fraction Alice First |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| `0.0` | `+1.0000` | `+1.0000` | `+0.0000` | `0.5038` | `0.5038` | `0.5060` |
| `20.0` | `+0.7660` | `+0.7688` | `+0.0028` | `0.4976` | `0.5084` | `0.4956` |
| `30.0` | `+0.5000` | `+0.4876` | `-0.0124` | `0.5116` | `0.5122` | `0.5008` |
| `40.0` | `+0.1736` | `+0.1656` | `-0.0080` | `0.5000` | `0.5048` | `0.5006` |
| `60.0` | `-0.5000` | `-0.5044` | `-0.0044` | `0.4942` | `0.5072` | `0.5016` |
| `70.0` | `-0.7660` | `-0.7712` | `-0.0052` | `0.5080` | `0.4948` | `0.5012` |
| `90.0` | `-1.0000` | `-1.0000` | `+0.0000` | `0.4950` | `0.5050` | `0.5034` |
| `120.0` | `-0.5000` | `-0.4868` | `+0.0132` | `0.4924` | `0.5070` | `0.4998` |
| `160.0` | `+0.7660` | `+0.7704` | `+0.0044` | `0.4988` | `0.4940` | `0.5044` |
| `180.0` | `+1.0000` | `+1.0000` | `+0.0000` | `0.5010` | `0.5010` | `0.4962` |

- **Goodness-of-fit across all 16 non-degenerate interior angles:** $\chi^2 = 11.826$ ($\text{dof} = 16$), **$p = 0.7558$**; exact perfect correlation/anticorrelation ($\pm 1.0000$) is achieved at $0^\circ, 90^\circ, 180^\circ$ because destructive interference zeroes the orthogonal PBS port identically ($\Delta u \equiv 0$).

---

### 5.3 Randomized In-Flight CHSH Experiment & Negative Control
On each of $N = 80{,}000$ pairs, Alice and Bob independently switch between $(a_0, a_1) = (0^\circ, 45^\circ)$ and $(b_0, b_1) = (22.5^\circ, 67.5^\circ)$ using fair 50/50 random bits ([exp_wick_chsh_summary.csv](file:///Users/john-bramble/Desktop/NewBornSelection/Gemini4Carbon/exp_wick_chsh_summary.csv)):

**Table 4. CHSH Correlators — Wick-Rotated Elliptic Bridge ON vs. Negative Control (Bridge OFF)**

| Protocol | $N_{\text{pairs}}$ | $E(0^\circ, 22.5^\circ)$ | $E(0^\circ, 67.5^\circ)$ | $E(45^\circ, 22.5^\circ)$ | $E(45^\circ, 67.5^\circ)$ | Empirical $S_{\text{CHSH}}$ | Target / Bound |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Wick Elliptic $\tau$-Bridge ON** | `80,000` | `+0.7012 ± 0.0050` | `-0.7054 ± 0.0050` | `+0.7050 ± 0.0050` | `+0.6990 ± 0.0051` | **`2.8106 ± 0.0101`** | $2\sqrt{2} = 2.8284$ (**$80.6\sigma > 2$**) |
| **Negative Control ($\tau$-Bridge OFF)** | `40,000` | `+0.351 ± 0.009` | `-0.355 ± 0.009` | `+0.353 ± 0.009` | `+0.351 ± 0.009` | **`1.4104 ± 0.0187`** | $\sqrt{2} = 1.4142 \le 2.0$ |

- **First-tunneling symmetry:** Alice tunnels first on **$49.88\%$** of pairs; Bob tunnels first on **$50.12\%$** of pairs.
- **Solid-state cascade irreversibility:** After $K_{\text{cas}} = 50$ random-phase bound-electron collisions, phase-retrieval coherence visibility collapses to `0.0131` (matching the per-batch random-walk shot-noise floor).

---

### 5.4 Relativistic No-Signaling Audit

**Table 5. Empirical Test of Faster-Than-Light Signaling Across Spacelike Analyzer Choices ($N = 80{,}000$)**

| Conditional Marginal Probability | Empirical Value | Partner-Setting Shift $\Delta P$ | Statistical Significance |
| :--- | :---: | :---: | :--- |
| $P(\text{Bob} = +1 \mid \text{Alice} = 0^\circ)$ | `0.50223` | `+0.00178` | $0.50\sigma$ *(consistent with zero signaling)* |
| $P(\text{Bob} = +1 \mid \text{Alice} = 45^\circ)$ | `0.50045` | — | — |
| $P(\text{Alice} = +1 \mid \text{Bob} = 22.5^\circ)$ | `0.49906` | `-0.00042` | $0.12\sigma$ *(consistent with zero signaling)* |
| $P(\text{Alice} = +1 \mid \text{Bob} = 67.5^\circ)$ | `0.49949` | — | — |

---

### 5.5 Microscopic Detector Diagnostic: Bounded Uniform Deficits vs. Memoryless Tunneling

Table 6 compares empirical CHSH values ($N = 30{,}000$ pairs per point) for bounded pre-arrival deficits $\Delta S \sim \operatorname{Uniform}(0, 1)$ at small $N_{\text{surf}}$ against the exact analytical order-statistic integral of Theorem 5 and memoryless quantum barrier tunneling ($\operatorname{Exp}(1)$).

**Table 6. Finite-Atom Sub-Barrier Deficit Scaling vs. Theorem 5 Analytical Prediction**

| Sub-Barrier Deficit Law | Active Surface Atoms $N_{\text{surf}}$ | Analytical $S_{\text{CHSH}}$ (Theorem 5) | Simulated $S_{\text{CHSH}}$ | Asymptotic Macroscopic Limit |
| :--- | :---: | :---: | :---: | :---: |
| Bounded $\operatorname{Uniform}(0, 1)$ | `16` | `2.8719` | `2.8838 ± 0.0160` | Converges as $1/N_{\text{surf}} \to 2\sqrt{2}$ |
| Bounded $\operatorname{Uniform}(0, 1)$ | `64` | `2.8394` | `2.8608 ± 0.0161` | Converges as $1/N_{\text{surf}} \to 2\sqrt{2}$ |
| Bounded $\operatorname{Uniform}(0, 1)$ | `256` | `2.8312` | `2.8168 ± 0.0164` | Converges as $1/N_{\text{surf}} \to 2\sqrt{2}$ |
| **Memoryless Tunneling $\operatorname{Exp}(1)$** | `64` *(any $N_{\text{surf}} \ge 1$)* | **`2.8284`** | **`2.8106 ± 0.0101`** | **Exact $2\sqrt{2} = 2.8284$ at all scales** |

---

## 6. Discussion: Physical Implications, Limitations, and Testable Predictions

### 6.1 Resolving the Apparent Paradox Between Local Waves and Nonlocal Entanglement
By separating real coordinate time $t_R$ (hyperbolic PDE, light-cone bounded) from Wick-rotated imaginary time $\tau$ (elliptic PDE, cone-free boundary equilibrium), spatial wave packets remain genuinely localized 3D field objects traveling at $v \le c$, while entanglement resides in topological zero-mode boundary coupling along $\tau$. Neither Hilbert-space collapse nor superluminal energy transmission is invoked.

### 6.2 Why Controllable Messaging Cannot Ride the $\tau$-Sheet
A frequent question in foundations of physics is *what* crosses outside the light cone during an EPR experiment. Theorem 4 and Table 5 give a precise answer: **boundary-value self-consistency of conserved spin/polarization crosses the elliptic $\tau$-sheet, whereas controllable bit signals cannot**, because the committed boundary state ($+1$ vs. $-1$) is triggered by uncontrollable, zero-mean local bound-electron and vacuum fluctuations at the detector surface.

### 6.3 Experimental Falsifiability in Few-Atom Detectors (Theorem 5)
Because Tsirelson's bound $|S_{\text{CHSH}}| \le 2\sqrt{2}$ is an exact constraint of standard quantum mechanics [7], Theorem 5 provides a sharp experimental discriminator: if single-atom or few-atom nanocavity Bell tests ever exhibited systematic supra-Tsirelson correlations scaling as $+1/N_{\text{surf}}$, it would signal bounded classical-like sub-barrier thresholds; conversely, strict adherence to $2\sqrt{2}$ down to $N_{\text{surf}} = 1$ single-atom traps favors genuine memoryless quantum barrier penetration.

### 6.4 Open Theoretical Extensions
Two natural extensions invite further mathematical work: (i) generalizing the 2-boundary elliptic $\tau$-strip to an $N$-boundary Euclidean star-graph (connecting three or more wave packets to reproduce Greenberger–Horne–Zeilinger [GHZ] multi-partite correlations event by event), and (ii) deriving the effective imaginary-time thickness $\tau_{\max}$ directly from coherence-time and environmental decoherence scales so that breaking coherence severs the $n = 0$ zero-mode bridge continuously.

### 6.5 Bloch-Sphere Center-Diameter Geometry, Einstein–Rosen Wormholes, and ER = EPR

Plotting the complexified-time entanglement mechanism on the **Bloch sphere** ($S^2 \cong \mathbb{CP}^1$) reveals a direct mathematical parallel to **wormhole solutions of General Relativity**:

1. **Diameters Through the Center of the Bloch Sphere:**  
   In density-matrix geometry $\hat{\rho} = \frac{1}{2}(\mathbf{I}_2 + \mathbf{r}\cdot\boldsymbol{\sigma})$, pure polarization/spin states lie on the unit sphere $|\mathbf{r}| = 1$, while any orthogonal measurement basis $\{|+\hat{\mathbf{n}}(\theta)\rangle, |-\hat{\mathbf{n}}(\theta)\rangle\}$ defines a **straight diameter passing directly through the center $\mathbf{r} = \mathbf{0}$** connecting antipodal poles $\pm\hat{\mathbf{n}}(\theta) = \pm(\cos 2\theta, \sin 2\theta, 0)$. Prior to detector commitment, each entangled partner's local reduced state sits **at the exact center $\mathbf{r} = \mathbf{0}$** ($\hat{\rho}_A = \hat{\rho}_B = \frac{1}{2}\mathbf{I}_2$). Whereas a real phase transformation $\exp(-i\frac{\phi}{2}\hat{\mathbf{m}}\cdot\boldsymbol{\sigma}) \in SU(2)$ rotates vectors along circles on the surface, **Wick-rotating the angle** ($\phi \to -i\eta$, $\exp(-\frac{\eta}{2}\hat{\mathbf{m}}\cdot\boldsymbol{\sigma}) \in SL(2, \mathbb{C})$ [27]) generates a radial/hyperbolic Möbius flow from the center $\mathbf{r} = \mathbf{0}$ outward to the boundary pole $\pm\hat{\mathbf{m}}$. Rotating Alice's committed diameter $\pm\hat{\mathbf{n}}(\theta_A)$ through the center onto Bob's analyzer diameter $\pm\hat{\mathbf{n}}(\theta_B)$ subtends Bloch angle $2(\theta_A - \theta_B)$, whose inner product $\hat{\mathbf{n}}(\theta_A)\cdot\hat{\mathbf{n}}(\theta_B) = \cos\big(2(\theta_A - \theta_B)\big)$ yields the exact Bell correlation.

2. **Exact Parallel to Einstein–Rosen Wormholes Under Wick Rotation (ER = EPR):**  
   In 1935—the same year as the EPR paper—Einstein and Rosen discovered the two-sided Schwarzschild bridge (**wormhole**) solution of General Relativity connecting two spacelike-separated exterior regions across a central bifurcation throat [28]. Remarkably, in Euclidean quantum gravity and black-hole thermodynamics (Israel, 1976 [29]; Maldacena & Susskind, 2013, **ER = EPR** [30]), that wormhole state is constructed **specifically by a $\pi$ ($180^\circ$) phase rotation in Wick-rotated imaginary time $\tau = i t$**:
   - Under $t = -i\tau$, the Schwarzschild metric becomes positive-definite (**elliptic**) on a smooth $(r, \tau)$ disk centered at the horizon origin $r = r_s$. Slicing that disk along a **straight diameter passing through the central origin** ($\tau = 0$ for Exterior $A$ and $\tau = \beta_H/2$—a half-period Wick phase shift—for Exterior $B$) produces the entangled two-sided wormhole state $|\Psi_{AB}\rangle = Z^{-1/2}\sum_n e^{-\beta E_n/2}|n\rangle_A|n\rangle_B$.
   - Crucially, General Relativity enforces the **exact same two-channel division** as Postulates P2–P3: by **topological censorship** [31], an Einstein–Rosen wormhole is **non-traversable in real time $t_R$** (forbidding faster-than-light messaging between $A$ and $B$), yet in **Wick-rotated imaginary time $\tau$** the horizon barrier vanishes and $A$ and $B$ are smoothly connected across the center by an elliptic geometry.
   - **Physical distinction at laboratory scales:** Whereas a smooth classical 4D General Relativity wormhole throat requires macroscopic gravitational curvature ($r_s = 2GM/c^2$), Maldacena and Susskind conjectured that a single entangled qubit pair possesses a minimal "Planckian/topological" ER bridge [30]. Our flat-spacetime **elliptic imaginary-time strip $(s, \tau)$** provides a concrete, curvature-free wave-mechanical realization of that exact topological bridge for laboratory photons and electrons.

---

## 7. Reproducibility

To run the complete verification suite and regenerate both CSV datasets from a standard Python 3 environment (`numpy`, `scipy`):

```sh
python3 wick_bell_chsh_sim.py
```

---

## References

1. Einstein, A., Podolsky, B., & Rosen, N. (1935). Can quantum-mechanical description of physical reality be considered complete? *Physical Review*, 47(10), 777–780.
2. Bell, J. S. (1964). On the Einstein Podolsky Rosen paradox. *Physics Physique Физика*, 1(3), 195–200.
3. Clauser, J. F., Horne, M. A., Shimony, A., & Holt, R. A. (1969). Proposed experiment to test local hidden-variable theories. *Physical Review Letters*, 23(15), 880–884.
4. Aspect, A., Dalibard, J., & Roger, G. (1982). Experimental test of Bell's inequalities using time-varying analyzers. *Physical Review Letters*, 49(25), 1804–1807.
5. Hensen, B., Bernien, H., Dréau, A. E., Reiserer, A., Kalb, N., Blok, M. S., ... & Hanson, R. (2015). Loophole-free Bell inequality violation using electron spins separated by 1.3 kilometres. *Nature*, 526(7575), 682–686.
6. Shalm, L. K., Meyer-Scott, E., Christensen, B. G., Bierhorst, P., Wayne, M. A., Stevens, M. J., ... & Nam, S. W. (2015). Strong loophole-free test of local realism. *Physical Review Letters*, 115(25), 250402.
7. Cirel'son [Tsirelson], B. S. (1980). Quantum generalizations of Bell's inequality. *Letters in Mathematical Physics*, 4(2), 93–100.
8. Eberhard, P. H. (1978). Bell's theorem and the different concepts of locality. *Il Nuovo Cimento B*, 46(2), 392–419.
9. von Neumann, J. (1932). *Mathematische Grundlagen der Quantenmechanik*. Springer, Berlin.
10. Feynman, R. P. (1948). Space-time approach to non-relativistic quantum mechanics. *Reviews of Modern Physics*, 20(2), 367–387.
11. Feynman, R. P. (1949). The theory of positrons. *Physical Review*, 76(6), 749–759.
12. Feynman, R. P. (1949). Space-time approach to quantum electrodynamics. *Physical Review*, 76(6), 769–789.
13. Feynman, R. P. (1950). Mathematical formulation of the quantum theory of electromagnetic interaction. *Physical Review*, 80(3), 440–457.
14. Feynman, R. P. (1953). Atomic theory of the $\lambda$ transition in helium. *Physical Review*, 91(6), 1291–1301.
15. Wick, G. C. (1954). Properties of Bethe–Salpeter wave functions. *Physical Review*, 96(4), 1124–1134.
16. Peskin, M. E., & Schroeder, D. V. (1995). *An Introduction to Quantum Field Theory* (§2.4, The Klein–Gordon Field in Space-Time). Addison-Wesley.
17. Bisognano, J. J., & Wichmann, E. H. (1975). On the duality condition for a Hermitian scalar field. *Journal of Mathematical Physics*, 16(4), 985–1007.
18. Unruh, W. G. (1976). Notes on black-hole evaporation. *Physical Review D*, 14(4), 870–892.
19. Gemini 4 Carbon & Bramble, J. M. (2026). Real-wave surface interference, first-passage quantum tunneling, and irreversible solid-state cascades: A mechanistic single-event replacement for the Born probability postulate (`Born_selection_v3.0_Gemini4Carbon.md`).
20. Tien, P. K., & Gordon, J. P. (1963). Multiphoton process observed in the interaction of microwave fields with the tunneling between superconductor films. *Physical Review*, 129(2), 647–651.
21. Keldysh, L. V. (1965). Ionization in the field of a strong electromagnetic wave. *Soviet Physics JETP*, 20(5), 1307–1314.
22. Wheeler, J. A., & Feynman, R. P. (1945). Interaction with the absorber as the mechanism of radiation. *Reviews of Modern Physics*, 17(2–3), 157–181.
23. Feynman, R. P. (1982). Simulating physics with computers. *International Journal of Theoretical Physics*, 21(6–7), 467–488.
24. Hartle, J. B., & Hawking, S. W. (1983). Wave function of the Universe. *Physical Review D*, 28(12), 2960–2975.
25. Cramer, J. G. (1986). The transactional interpretation of quantum mechanics. *Reviews of Modern Physics*, 58(3), 647–687.
26. Wharton, K. B., & Argaman, N. (2020). Colloquium: Bell's theorem and locally mediated reformulations of quantum mechanics. *Reviews of Modern Physics*, 92(2), 021002.
27. Penrose, R., & Rindler, W. (1984). *Spinors and Space-Time, Vol. 1: Two-Spinor Calculus and Relativistic Fields* (Ch. 1, Geometry of the Riemann/Bloch Sphere and Lorentz Transformations). Cambridge University Press.
28. Einstein, A., & Rosen, N. (1935). The particle problem in the general theory of relativity. *Physical Review*, 48(1), 73–77.
29. Israel, W. (1976). Thermo-field dynamics of black holes. *Physics Letters A*, 57(2), 107–110.
30. Maldacena, J., & Susskind, L. (2013). Cool horizons for entangled black holes. *Fortschritte der Physik*, 61(9), 781–811.
31. Friedman, J. L., Schleich, K., & Witt, D. M. (1993). Topological censorship. *Physical Review Letters*, 71(10), 1486–1489.
