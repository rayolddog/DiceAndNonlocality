# Born Selection at the Detector
## A physical-wave proposal for individual photon outcomes and the emergence of Born statistics

**Version:** 3.0  
**Date:** November 12, 2026  
**Prepared by:** ChatGPT, developing the mechanism proposed by John Bramble  
**Manuscript status:** Theoretical proposal with a conditional mathematical result; no experimental validation or microscopic derivation is claimed.

## Abstract

Quantum mechanics predicts distributions of measurement outcomes with remarkable success, yet the prediction of a distribution and the physical production of one recorded event are distinct explanatory tasks. We propose a detector-centered account in which a physically real incident wave interacts with the electronic states and electromagnetic environment of a solid detector. The incident interference pattern determines the spatial structure of the coupling, while microscopic fluctuations modify the readiness of individual sites to respond. In the proposed tunneling realization, the first successful photon-assisted transition selects one site, consumes the single incident excitation, and initiates an amplification cascade. Entanglement with electronic, lattice, and environmental degrees of freedom makes the resulting record effectively irreversible. Repetition is required to recover the Born distribution without a separate draw from that distribution at the final stage of each calculation. A competing-transition model establishes a precise sufficient condition: if the conditional transition rates share a common temporal factor and are proportional to the Born weights, the first-event frequencies equal those weights. This result identifies the mathematical structure the microscopic proposal must produce; it does not derive that structure from unbiased noise. The remaining questions concern the physical law selecting an individual transition, the origin of the required rate ratios, and the consistency of exclusive absorption with energy conservation and relativistic causality.

**Keywords:** Born rule; quantum measurement; photon absorption; detector dynamics; photon-assisted tunneling; decoherence; individual outcomes.

## 1. Introduction: from statistical prediction to the individual event

The development of quantum mechanics established a distinction between the evolution of a quantum state and the probabilities assigned to experimental outcomes. Schrödinger evolution supplies a dynamical law for the state. Born's statistical interpretation, introduced in his collision work in 1926, relates amplitudes to outcome probabilities through their squared magnitudes. In his Nobel lecture, Born described both the development of that interpretation and the resistance it encountered from some of quantum theory's founders [1].

Born, Bohr, and Einstein did not share a single verdict about the completeness of this description. Born defended its statistical character. Bohr defended the adequacy of quantum mechanics through complementarity and the inseparability of a phenomenon's description from the conditions under which it is observed. Einstein accepted the theory's predictive achievements while disputing whether its wave function furnished a complete account of physical reality. The historical question was therefore whether a successful statistical theory exhausted what physics could say about an individual process, rather than an agreed conclusion that quantum mechanics was incomplete.

Einstein, Podolsky, and Rosen sharpened the issue in 1935 by considering correlations between separated systems and proposing a criterion for a complete physical description [2]. Bohr's response challenged the applicability of their criterion and defended the completeness of the quantum description within its proper scope [3]. Their disagreement involved locality, the meaning of physical reality, and the role of experimental arrangements. It cannot be reduced to a dispute over whether random numbers are useful in calculations.

Nevertheless, the difference between a predicted distribution and a particular detector record remains a useful starting point. A calculation may specify that an incident photon has a particular probability of being detected at each element of an array. It does not thereby specify which element will record the next photon. In a conventional simulation, that event can be represented by sampling the calculated probabilities. Such sampling is a computational procedure; the Copenhagen interpretation does not posit that nature contains a literal random-number generator.

This manuscript asks whether the final selection can instead be represented by a physical process at the detector. Its central proposal is that a real incident wave, the detector's microscopic electronic configuration, and its fluctuating environment jointly determine the development of competing absorption channels. The first successful transition becomes the recorded event. Repetition over changing microscopic conditions must then produce the same frequencies that conventional theory assigns through the Born rule.

The proposed account retains the successful wave calculation. It seeks to supplement that calculation at the point where an extended excitation becomes a localized, durable record. We call this proposed transition **Born selection**. The term denotes a research objective: to explain individual outcomes through detector dynamics while recovering the Born distribution as an ensemble property.

The scope here is deliberately specific. We consider an incident single-photon wave packet illuminating a row of detector elements. A tunneling-assisted detector provides the proposed microscopic realization. An account of this arrangement would be an initial case study, not yet a universal theory of measurement.

## 2. A simple recipe for Born selection

Table 1 states the mechanism in its intended physical order. The qualifications identify what is assumed and what remains to be calculated.

**Table 1. Proposed recipe for generating individual detector records.**

| Step | Physical proposal | Role in the calculation |
|---|---|---|
| 1. A real incident wave | The wave function represents a physically real quantum state with spatially extended wave character. | Begin with a specified single-photon state, including its spatial, temporal, spectral, and polarization structure. Physical reality is an interpretive premise. |
| 2. Wave evolution | The state evolves toward and within the detector according to the appropriate Hamiltonian. | Preserve Schrödinger evolution for the joint quantum state, using an electromagnetic-field and matter Hamiltonian for a photon. |
| 3. Surface interaction | The incident wave couples to electrons in the detector's active surface region and to the electromagnetic environment. | Calculate local transition amplitudes, including interference among indistinguishable pathways and the detector's material response. |
| 4. Microscopic fluctuations | Electronic configurations and vacuum-related fluctuations modify the local response without an imposed preference for one otherwise equivalent detector element. | Specify the fluctuations' means, correlations, spectra, and coupling to the transition. Unbiasedness alone does not establish Born frequencies. |
| 5. First successful transition | A photon-assisted tunneling transition occurs at one site before the competing sites complete absorption. | Resolve the event through a microscopic dynamics or an explicitly identified stochastic transition law. Tunneling requires a physical barrier. |
| 6. Exclusive absorption | That transition consumes the single incident excitation, leaving no second photon from the same input to be absorbed elsewhere. | Supply a consistent rule for exclusive selection and field depletion. This is the proposal's global component. |
| 7. Amplification and recording | The initial excitation couples to other electrons, the lattice, and the readout apparatus. | Produce a stable macroscopic record and make recovery of the initial coherent state practically inaccessible. |
| 8. Ensemble accumulation | Repeated preparations encounter different microscopic detector and environmental states. | Demonstrate that accumulated outcome frequencies converge to the Born distribution, with detector inefficiency and background events accounted for. |

The intended causal sequence is thus wave evolution, local interaction, fluctuation-sensitive competition, exclusive absorption, and irreversible recording. The distribution is recovered from many such events. It is not used as a final list from which the recorded site is directly selected.

## 3. Physical content of the proposal

### 3.1. What is meant by a real wave?

Calling the wave real assigns physical significance to the quantum state. It does not require the state to be an ordinary classical electric field whose energy can be divided continuously among independent absorbers.

For a single photon, a useful optical amplitude is

$$
f(\mathbf r,t)
=\langle 0|\hat E^{(+)}(\mathbf r,t)|1_f\rangle ,
\tag{1}
$$

with polarization indices suppressed. In the idealized single-photon case, the first-order field correlation is

$$
G^{(1)}(\mathbf r,t)
=\langle 1_f|\hat E^{(-)}(\mathbf r,t)
\hat E^{(+)}(\mathbf r,t)|1_f\rangle
=|f(\mathbf r,t)|^2 .
\tag{2}
$$

These quantities connect wave propagation to standard photodetection theory [4,5]. The amplitude in Eq. (1) is not the mean electric field: a photon-number state can have a vanishing mean field and still exhibit spatial interference in detection.

The real-wave premise therefore concerns a quantum excitation. It preserves the possibility of an extended interference pattern together with a single absorption event. For many interacting particles, a wave function also generally belongs to a many-body configuration space; a collection of independent three-dimensional waves is not a complete replacement for that structure.

The joint state evolves schematically as

$$
i\hbar\frac{\partial}{\partial t}|\Psi(t)\rangle
=\left(\hat H_{\mathrm{field}}+\hat H_{\mathrm{detector}}
+\hat H_{\mathrm{int}}+\hat H_{\mathrm{environment}}\right)
|\Psi(t)\rangle .
\tag{3}
$$

Equation (3) uses the Schrödinger equation in its general state-vector form. A photon should not be propagated by inserting zero mass into the nonrelativistic Schrödinger equation for a massive particle.

### 3.2. Interference at the detector

The incident packet establishes a spatially varying interaction with the detector. Electronic states near the surface determine which transitions are available, how strongly they couple to the incident field, and how those transitions respond to the surrounding material.

The phrase “interference between the incident wave, electronic waves, and the vacuum” requires a precise interpretation. Photon and electron wave functions describe different degrees of freedom and cannot simply be added as three scalar waves. Instead, their coupling enters a joint transition amplitude. In a dipole approximation, a representative interaction is

$$
\hat H_{\mathrm{int}}
\simeq-\sum_i\hat{\mathbf d}_i\cdot\hat{\mathbf E}(\mathbf r_i),
\tag{4}
$$

where \(\hat{\mathbf d}_i\) is the electronic dipole operator associated with an active site. A particular material may require a more complete interaction Hamiltonian.

At lowest order in the interaction picture, the transition amplitude into an absorbing channel has the schematic form

$$
\mathcal M_i(t)
=-\frac{i}{\hbar}\int_0^t
\langle F_i|\hat H_{\mathrm{int}}(s)|I\rangle\,ds .
\tag{5}
$$

The initial and final states include both field and detector degrees of freedom. Contributions can interfere when they lead to the same indistinguishable final channel. Different, distinguishable records are separate channels. Equations (4) and (5) provide a physically meaningful formulation of the proposed complex-wave interaction without treating electron and photon amplitudes as interchangeable quantities.

For the proposed mechanism and conventional quantum theory to predict the same optical pattern, they must use the same incident state, material response, and boundary conditions. Averaging over the proposed fluctuations must preserve the relevant calibrated response. This agreement is a condition on the mechanism, not a consequence of calling the noise unbiased.

### 3.3. The incident energy pattern and the deposited energy

There are two distinct distributions. One is the spatial profile of incident field energy or absorption propensity. The other is the energy actually deposited in one experimental trial.

For an ideal narrowband photon of energy approximately \(\hbar\omega\), a successful localized absorption transfers that excitation's energy into the selected detector region. If the probability for that region is \(p_i\), the mean deposited energy per trial is approximately

$$
\langle E_i\rangle=p_i\hbar\omega .
\tag{6}
$$

Equation (6) does not mean that a fraction \(p_i\hbar\omega\) has already been irreversibly deposited at every detector before selection. The proposal instead gives the extended wave a spatially varying capacity to initiate absorption, followed by one completed transfer. This distinction avoids requiring previously deposited energy to be gathered from distant sites.

The same distinction clarifies the Born rule's role. It assigns probabilities to measurement outcomes. An average energy distribution follows only after the possible energies and the detector response have also been specified.

### 3.4. Electronic fluctuations and the vacuum contribution

The proposed fluctuations have two sources: the many-body state of the material and its electromagnetic environment. Electronic occupations, phonons, defects, local fields, and coupling to external circuitry can alter the susceptibility of an active site. Vacuum field correlations may influence radiative dynamics and the effective response near material boundaries.

An effective description may represent fluctuations of a relevant detector variable by

$$
\xi_i(t)=\xi_i^{\mathrm{mat}}(t)+\xi_i^{\mathrm{vac}}(t),
\qquad
\langle\xi_i(t)\rangle=0,
\tag{7}
$$

with correlation functions

$$
C_{ij}(t,t')=\langle\xi_i(t)\xi_j(t')\rangle .
\tag{8}
$$

Here \(\xi_i\) is a placeholder for a specified physical quantity, such as a fluctuation in detuning or barrier height. Equation (7) is an effective modeling assumption. It does not establish that an arbitrary classical noise process reproduces the operator correlations of a quantum environment.

“Unbiased” means that equivalent, equally illuminated sites have no imposed preference in the preparation of their microscopic fluctuations. It does not imply white noise, independent sites, Gaussian statistics, or identical behavior under unequal illumination. Material boundaries can generate spatial and spectral structure that must be calculated.

Vacuum fluctuations also cannot be treated as an unrestricted supply of energy that excites a passive ground-state detector. In ideal absorptive photodetection, the normally ordered vacuum correlation satisfies

$$
\langle0|\hat E^{(-)}\hat E^{(+)}|0\rangle=0,
\tag{9}
$$

even though other vacuum correlations are nonzero [4,5]. A biased or metastable detector can release stored energy, but that energy must be included in its accounting. Any effective vacuum-noise model must respect this distinction and reproduce the appropriate dark-count behavior.

### 3.5. Tunneling as the initiating transition

The proposed realization uses a detector with a genuine tunneling barrier. The incident field and the local electronic configuration jointly enable a photon-assisted transition into a state from which amplification can proceed. Microscopic fluctuations affect the timing of this transition, so different sites may complete it first in otherwise identically prepared trials.

A transition to a higher atomic orbital is not, in general, tunneling. An energy-level gap and a spatial potential barrier are different physical structures. Conventional optical absorption can excite an electron or create an electron–hole pair without tunneling being the initiating process. Consequently, the present recipe requires a specified barrier-containing detector rather than a claim about every solid detector.

Photon-assisted tunneling does provide a concrete physical setting. For example, Haldar and colleagues demonstrated microwave photon counting using a cavity-coupled double quantum dot, with tunneling events monitored through a third dot [6]. That experiment establishes a relevant detection architecture; it does not establish the outcome-selection mechanism proposed here or its applicability to an optical detector surface.

In the intended realization, photon absorption and barrier crossing belong to a coupled transition. The electron does not first acquire energy without a source and then subsequently capture a photon to pay the energy cost.

Ordinary tunneling calculations yield amplitudes or rates. They do not, by themselves, identify which barrier crossing occurs in an individual trial. A complete version of this proposal must therefore specify either a dynamics that determines the transition from microscopic initial conditions or a physical stochastic law whose event statistics are independently justified.

### 3.6. The first transition and exclusive absorption

The central selection hypothesis is that the first completed absorption channel consumes the single excitation represented by the incident packet. The remaining sites can no longer absorb that same photon. In this sense, selection acts on the state of the entire packet.

Standard quantum optics already contains a related mathematical fact. For orthogonal detector channels,

$$
|1_f\rangle=\sum_{i=1}^{M}c_i|1_i\rangle,
\qquad
\sum_i|c_i|^2=1,
\tag{10}
$$

and

$$
\hat a_i|1_f\rangle=c_i|0\rangle .
\tag{11}
$$

Conditional on absorption in channel \(i\), the field is left in the vacuum rather than with a residual fraction of the same photon available for a second absorption. Equation (11) expresses the state change associated with an event; it does not determine which \(i\) occurs.

The proposed mechanism assigns physical significance to this exclusive selection. It must explain how the first transition becomes the actual event, while preserving the single-excitation constraint. Calling the packet nonlocal states part of the intended ontology but does not supply the missing dynamical law.

No instantaneous transport of already deposited energy across the array is assumed. Nor is a controllable signal between detector sites implied. “First” can initially be defined in the rest frame of a compact detector assembly. A general account of spacelike-separated candidate events would need a relativistically consistent formulation or a stated additional spacetime structure.

### 3.7. Amplification and effective irreversibility

Once absorption has initiated a local excitation, its consequences spread through the detector. Electronic collisions, lattice excitations, charge multiplication, and coupling to the readout system can convert a microscopic change into a stable record. The gain energy may come predominantly from the detector's bias supply.

The original phase relations become distributed among a large number of degrees of freedom. A description confined to the measured subsystem then loses access to the interference between distinct macroscopic records. This is the role of environmental decoherence and the stability of pointer states [7].

Randomly distributed phases provide an intuitive picture of part of this process, but the essential issue is the loss of accessible phase relations through entanglement and environmental coupling. Under globally unitary evolution, information is not necessarily destroyed; reconstructing it would require control of an overwhelmingly large joint state.

Thus, “irreversible” here means effectively irreversible for the apparatus and available operations. Decoherence explains the durability and apparent classicality of records, but does not alone establish why exactly one outcome occurs [8]. In the proposal, selection and the subsequent stabilization of the selected record are distinct tasks.

## 4. Comparison with the conventional calculation

Table 2 compares a conventional operational simulation with the intended mechanism. The conventional account can already include detailed detector dynamics; the proposed addition concerns the explanation of an individual realized outcome.

**Table 2. Two routes from a wave calculation to a recorded event.**

| Stage | Conventional operational simulation | Proposed Born-selection mechanism |
|---|---|---|
| Propagation | Evolve the incident state with the appropriate Hamiltonian. | Use the same wave evolution. |
| Detector interaction | Calculate coupling, transition amplitudes, and material response. | Calculate the same quantities while resolving the microscopic variables proposed to control selection. |
| Spatial pattern | Obtain channel probabilities from the state and the measurement operators. | Obtain the spatial structure of competing physical transition channels. |
| One outcome | Sample an outcome using its calculated probability; a simulation commonly uses pseudorandom numbers. | Evolve the competition until one channel completes the initiating transition. |
| Photon consumption | Condition the field state on the recorded absorption. | Treat consumption of the single excitation as part of the physical selection process. |
| Record | Model amplification and environmental decoherence. | Use those processes to stabilize the selected event. |
| Repetition | Repeated samples reproduce the specified probability law. | Repeated microscopic realizations must produce that law as a result. |

For a general detector, the conventional rule is

$$
p_i=\operatorname{Tr}(\rho\Pi_i),
\qquad
\Pi_i\geq0,
\qquad
\sum_{i=0}^{M}\Pi_i=I,
\tag{12}
$$

where \(i=0\) can represent no detection. An ideal channel measurement on Eq. (10) gives \(p_i=|c_i|^2\).

The proposed replacement concerns the final selection step, not the propagation or interference calculation. It must nevertheless account for detector response: equal incident intensities do not imply equal observed counts when efficiencies, thresholds, or active areas differ.

A simulation of the proposal may still require random numbers to represent unresolved detector microstates or stochastic forces. Its distinguishing aim is to avoid directly drawing the outcome label from the desired Born probabilities. If the microscopic randomness is merely designed to encode those probabilities, the explanatory problem has been relocated rather than resolved.

## 5. A mathematical model of competing transitions

### 5.1. Conditional transition rates

Consider \(M\) channels with fixed spatial weights

$$
w_i=|c_i|^2,
\qquad
\sum_iw_i=1.
\tag{13}
$$

For the following sufficient-condition calculation, assume a common pulse envelope and matched detector response. Let \(\lambda_i(t)\) be the conditional rate for the first registered transition to occur in channel \(i\), given that none has yet occurred. Thus

$$
\Pr(i\text{ triggers in }[t,t+dt)\mid\text{no earlier event})
=\lambda_i(t)\,dt+o(dt).
\tag{14}
$$

With specified nonnegative rates and negligible simultaneous-event probability, the no-event survival function is

$$
S(t)=\exp\!\left[-\int_0^t\sum_j\lambda_j(s)\,ds\right].
\tag{15}
$$

The probability that channel \(i\) wins before the end of a gate \(T\) is

$$
P_i(T)=\int_0^T S(t)\lambda_i(t)\,dt .
\tag{16}
$$

These are statements about an effective event process. They do not presuppose that each site has an independent physical photon to absorb. The process terminates after the first event, consistently with the proposed single-excitation constraint.

### 5.2. A sufficient condition for Born frequencies

Suppose the microscopic mechanism produces the factorized rates

$$
\boxed{\lambda_i(t)=w_i\,\kappa(t)}
\tag{17}
$$

with the same nonnegative temporal factor \(\kappa(t)\) for every channel. Then

$$
\begin{aligned}
P_i(T)
&=w_i\int_0^T
\kappa(t)\exp\!\left[-\int_0^t\kappa(s)\,ds\right]dt\\
&=w_i\left(1-e^{-K(T)}\right),
\qquad
K(T)=\int_0^T\kappa(s)\,ds .
\end{aligned}
\tag{18}
$$

The no-detection probability is \(P_0(T)=e^{-K(T)}\). Conditional on detection, provided its probability is nonzero,

$$
\boxed{\Pr(i\mid\text{detection before }T)=w_i=|c_i|^2.}
\tag{19}
$$

If eventual detection is certain, the unconditional probabilities also equal \(w_i\). For repeated independent detected trials with the same preparation,

$$
\frac{N_i}{N_{\mathrm{det}}}\longrightarrow w_i
\tag{20}
$$

by the law of large numbers. Finite records fluctuate around these values; they need not equal them exactly.

Equation (19) establishes a useful conditional result: a competition for the first transition can produce Born frequencies. The unresolved physical step is Eq. (17). Its proportionality to \(w_i\) must emerge from the proposed detector dynamics. Inserting it by hand produces a valid statistical construction, not an independent derivation of the Born rule.

If channel efficiencies enter as constant factors, the analogous assumption \(\lambda_i=\eta_iw_i\kappa\) instead yields conditional fractions \(\eta_iw_i/\sum_j\eta_jw_j\). This is a reminder that detector calibration belongs inside the measurement model.

### 5.3. What noise must preserve

A fluctuating common factor \(\kappa(t)\), with a well-defined conditional event process, can change the waiting time without changing the channel fractions in Eq. (19). The cancellation holds for each realization of that common factor.

Independent local fluctuations generally do not cancel. In particular,

$$
\langle\lambda_i(t)\rangle=w_i\kappa(t)
\tag{21}
$$

does not imply Eq. (19), because the survival factor and the channel rates are correlated. The probability of winning depends on the entire competition, not solely on a mean rate.

Appendix A gives an exact counterexample: identical, unbiased fluctuations at two sites change a target probability of \(0.25\) to \(0.275\). This result does not exclude a suitable physical noise mechanism. It shows that its correlation structure and effect on the competition have to be demonstrated.

Likewise, channels with different pulse shapes need not obey Eq. (17). Early absorption can weight the competition differently from an unweighted integral of the incident pattern. A full treatment must derive the relevant time-dependent detector response and compare it with the corresponding quantum prediction.

### 5.4. The stronger goal: individual results from microscopic conditions

The rate model still assigns probabilities to transitions. A stronger completion would introduce microscopic variables \(z\), representing the relevant detector and environmental conditions, and an event map

$$
i=F(\Psi,z).
\tag{22}
$$

For a specified preparation measure \(\mu\), the outcome basin would be

$$
\mathcal B_i(\Psi)=\{z:F(\Psi,z)=i\}.
\tag{23}
$$

The required result is

$$
\mu\!\left(\mathcal B_i(\Psi)\right)
=\langle\Psi|\Pi_i|\Psi\rangle ,
\tag{24}
$$

including the no-detection outcome when applicable. Here the detector's preparation measure must be justified physically, rather than fitted separately to force agreement for each incident state.

Equations (22)–(24) state precisely the ambition to replace a final probability draw with an individual-result calculation. They do not themselves provide \(F\), the microscopic evolution, or the measure \(\mu\). Those are the central ingredients still to be constructed.

## 6. Relation to existing measurement theory

Quantum-trajectory methods already combine wave evolution with discrete stochastic events and can simulate individual measurement records [9]. Their existence shows that event-by-event modeling is compatible with standard quantum mechanics. It also sets a demanding benchmark: describing a photon absorption as a jump or a first event is not, by itself, a new explanation of the Born rule.

The additional claim proposed here is that the detector's physical microstate and fluctuations can supply the selection mechanism and explain its statistics. To establish that claim, one must identify which assumptions differ from, or complete, conventional quantum-trajectory theory. If every event rate is imported from standard quantum probabilities, the result remains a microscopic implementation of those probabilities.

A successful real-wave account must also preserve nonclassical photon correlations. A divided classical wave with independent local thresholds is insufficient as a general account of single-photon experiments. Beam-splitter anticorrelation measurements provide a relevant experimental constraint alongside interference [10]. The proposed exclusive-absorption mechanism must reproduce both, including the observed suppression of double detections from one prepared photon.

The present detector-array model does not establish a theory of entangled measurements at separated locations. Any such extension must confront Bell's result: a completion satisfying the relevant locality and independence assumptions cannot reproduce all quantum correlations [11]. Adding local detector noise does not remove that constraint. A theory that uses nonlocal selection must also show that the mechanism does not permit controllable faster-than-light signaling.

## 7. A program for calculation and experimental assessment

The next step is to replace the verbal recipe with one fully specified model. A useful first implementation would couple two or more matched, barrier-containing absorbers to a single-photon input state and include a physically characterized environment. Its results should be compared with the quantum prediction for that same apparatus.

**Table 3. Required calculations and discriminating checks.**

| Question | Calculation or measurement | Criterion |
|---|---|---|
| What initiates an event? | Specify electronic states, the barrier, field coupling, bias, and relevant reservoirs. | Obtain a definite absorption and triggering dynamics rather than an unspecified threshold. |
| Where does the noise come from? | Derive or independently characterize fluctuation spectra and cross-correlations. | Avoid choosing a noise distribution solely because it produces the desired histogram. |
| Is selection calculated? | Track a microscopic realization to a completed transition. | Identify the step that determines the outcome and any probability postulate still used there. |
| Does one photon produce one primary event? | Count coincident triggers in a split-channel arrangement. | Recover single-photon anticorrelation after accounting for background, cross-talk, and multiphoton contamination. |
| Are Born frequencies recovered? | Vary unequal channel weights, relative optical phase, channel number, and detector response. | Match the complete measurement prediction over a family of inputs without refitting the mechanism for each state. |
| Is the record stable? | Model amplification, environmental coupling, and possible reversal. | Explain the separation between reversible microscopic interaction and a practically irreversible record. |
| Is the energy budget consistent? | Track incident energy, detector bias energy, and dissipation. | Preserve energy accounting and the correct passive-detector and dark-count limits. |
| Does the proposal add predictive content? | Compare changes in event timing, correlations, or frequencies with conventional detector theory. | Identify either a distinct testable prediction or a demonstrable explanatory completion with the same predictions. |

A balanced two-channel test is insufficient: symmetry alone can produce equal counts. Unequal weights and variable interference phases are more informative. The counterexample in Appendix A illustrates why a model can pass a symmetry test yet fail away from equal illumination.

The statistical record should include missed detections and background events, not merely a histogram normalized after arbitrary exclusions. Long runs also require an assessment of detector drift and memory, since convergence to fixed frequencies assumes an appropriate stationary or repeatable preparation.

The present manuscript reports no such simulation or experiment. Equations (18)–(19) and the counterexample below are analytic results for explicitly stated effective models.

## 8. Discussion and conclusion

The proposed mechanism locates outcome selection in the interaction between an extended quantum wave and a physically structured detector. Its sequence is concrete: the wave establishes a pattern of coupling; the microscopic material and electromagnetic environment influence competing transitions; one transition absorbs the available excitation; and a cascade stabilizes the record.

This sequence offers a way to formulate the distinction between the distribution of possible outcomes and the occurrence of one outcome. It also separates three explanatory tasks that can otherwise be conflated: forming the interference pattern, selecting a unique absorption event, and making its record effectively irreversible.

The mathematical competition model shows how the desired ensemble behavior can arise. When channel rates retain the Born weights as fixed ratios, the first-event probabilities reproduce those weights exactly, conditional on detection. The result gives a target for a microscopic theory. It does not show that zero-mean fluctuations, tunneling, or decoherence automatically generate that target.

The decisive work is therefore to derive the selection dynamics and its preparation measure, demonstrate exclusive absorption, and recover the required statistics across different incident states and detector settings. If this can be achieved without inserting the outcome probabilities at an earlier stage, the Born rule could be understood as the statistical expression of a physical event-selection process. Until then, Born selection remains a specified mechanism proposal with a clear mathematical condition for success.

## Appendix A. Why unbiased local noise is insufficient

Consider two channels with target weights

$$
w_1=\frac14,\qquad w_2=\frac34.
\tag{A1}
$$

For each trial, let two independent local gain factors \(A_1,A_2\) each take the values \(1/2\) and \(3/2\) with equal probability. Both have mean one, so their fluctuations \(A_i-1\) have zero mean and identical statistics.

During that trial, let the constant competing rates be

$$
\lambda_1=\kappa w_1A_1,\qquad
\lambda_2=\kappa w_2A_2,
\qquad \kappa>0,
\tag{A2}
$$

and wait until a first event occurs. Conditional on the gains, the probability that channel 1 wins is

$$
P_1(A_1,A_2)
=\frac{w_1A_1}{w_1A_1+w_2A_2}.
\tag{A3}
$$

The four equally likely cases give

| \(A_1\) | \(A_2\) | Probability that channel 1 wins |
|---|---|---|
| \(1/2\) | \(1/2\) | \(1/4\) |
| \(1/2\) | \(3/2\) | \(1/10\) |
| \(3/2\) | \(1/2\) | \(1/2\) |
| \(3/2\) | \(3/2\) | \(1/4\) |

Consequently,

$$
\langle P_1\rangle
=\frac14\left(\frac14+\frac1{10}+\frac12+\frac14\right)
=\frac{11}{40}=0.275,
\tag{A4}
$$

rather than \(w_1=0.25\). Although \(\langle\lambda_i\rangle=\kappa w_i\), averaging the normalized competition is not the same as normalizing the average rates. A mechanism based on unbiased local fluctuations therefore needs an additional dynamical reason for Born agreement.

## References

1. Born, M. “The statistical interpretation of quantum mechanics.” Nobel Lecture, December 11, 1954. [Nobel Foundation lecture](https://www.nobelprize.org/uploads/2018/06/born-lecture.pdf).

2. Einstein, A., Podolsky, B., and Rosen, N. “Can Quantum-Mechanical Description of Physical Reality Be Considered Complete?” *Physical Review* **47**, 777–780 (1935). [doi:10.1103/PhysRev.47.777](https://doi.org/10.1103/PhysRev.47.777).

3. Bohr, N. “Can Quantum-Mechanical Description of Physical Reality be Considered Complete?” *Physical Review* **48**, 696–702 (1935). [doi:10.1103/PhysRev.48.696](https://doi.org/10.1103/PhysRev.48.696).

4. Glauber, R. J. “The Quantum Theory of Optical Coherence.” *Physical Review* **130**, 2529–2539 (1963). [doi:10.1103/PhysRev.130.2529](https://doi.org/10.1103/PhysRev.130.2529).

5. Glauber, R. J. “Nobel Lecture: One hundred years of light quanta.” *Reviews of Modern Physics* **78**, 1267–1278 (2006). [doi:10.1103/RevModPhys.78.1267](https://doi.org/10.1103/RevModPhys.78.1267).

6. Haldar, S., Barker, D., Havir, H., Ranni, A., Lehmann, S., Dick, K. A., and Maisi, V. F. “Continuous Microwave Photon Counting by Semiconductor-Superconductor Hybrids.” *Physical Review Letters* **133**, 217001 (2024). [doi:10.1103/PhysRevLett.133.217001](https://doi.org/10.1103/PhysRevLett.133.217001).

7. Zurek, W. H. “Decoherence, einselection, and the quantum origins of the classical.” *Reviews of Modern Physics* **75**, 715–775 (2003). [doi:10.1103/RevModPhys.75.715](https://doi.org/10.1103/RevModPhys.75.715).

8. Schlosshauer, M. “Decoherence, the measurement problem, and interpretations of quantum mechanics.” *Reviews of Modern Physics* **76**, 1267–1305 (2004 issue; published February 23, 2005). [doi:10.1103/RevModPhys.76.1267](https://doi.org/10.1103/RevModPhys.76.1267).

9. Dalibard, J., Castin, Y., and Mølmer, K. “Wave-function approach to dissipative processes in quantum optics.” *Physical Review Letters* **68**, 580–583 (1992). [doi:10.1103/PhysRevLett.68.580](https://doi.org/10.1103/PhysRevLett.68.580).

10. Grangier, P., Roger, G., and Aspect, A. “Experimental Evidence for a Photon Anticorrelation Effect on a Beam Splitter: A New Light on Single-Photon Interferences.” *Europhysics Letters* **1**, 173–179 (1986). [doi:10.1209/0295-5075/1/4/004](https://doi.org/10.1209/0295-5075/1/4/004).

11. Bell, J. S. “On the Einstein Podolsky Rosen paradox.” *Physics Physique Fizika* **1**, 195–200 (1964). [doi:10.1103/PhysicsPhysiqueFizika.1.195](https://doi.org/10.1103/PhysicsPhysiqueFizika.1.195).
