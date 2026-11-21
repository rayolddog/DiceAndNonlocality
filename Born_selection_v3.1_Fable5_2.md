# Born Selection as a First-to-Fire Race: A Simulation

**Version 3.1 (short form) · 2026-11-12**
**Drafted by Claude Fable 5.2 (Anthropic) from a mechanism proposed by J. Bramble.**
Code and results: `~/Desktop/Fable/born_selection_v3/recipe_sim.py`, `recipe_results.json`.

---

## Abstract

Quantum mechanics predicts the distribution of detection events with the Born rule but does not describe the single event. To simulate one, a site is drawn at random from the Born distribution. We replace that draw with a physical race. The wave is taken to be real and its squared modulus at the detector to be an energy density. Each absorbing site makes an irreversible transition across its energy gap at a rate proportional to the local energy density, and the first site to do so absorbs the whole quantum. In a simulated two-slit experiment, a first-to-fire race among detector sites, with firing rates proportional to the local energy of the wave and random phases at the individual atoms, accumulates to the Born rule distribution: 200,000 such events reproduce it as closely as the random draw does. The rule is not a derivation of the Born rule; the squared modulus enters through the rate. It is a physical account of the single event.

## 1. Background

Born proposed in 1926 that the squared modulus of the wave function is the probability of an outcome [1]. Einstein objected that a theory of probabilities was not a description of the individual event, and at the 1927 Solvay conference he pointed out that if the wave is real, detection at one point requires the wave to cease acting everywhere else at once [2,3]. Bohr held that no further description is available [4]. Practice followed Bohr: the wave is computed with the Schrödinger equation, the Born rule gives the distribution, and nothing is said about how one outcome occurs [5].

Einstein had himself written a law that connects a wave to individual events. In 1917 he took the rate of absorption by an atom to be proportional to the energy density of the radiation [6]. We use that law as the selection rule.

## 2. The recipe

| Step | Standard recipe | Proposed recipe |
|---|---|---|
| 1. Wave at the detector | Schrödinger equation; complex interference | The same |
| 2. Squared modulus | Probability of detection at each site | Energy density of a real wave at each site |
| 3. Single event | Random draw weighted by step 2 | Each site has a memoryless transition rate proportional to step 2. The first to fire wins |
| 4. After the event | Collapse | The whole quantum is absorbed at the winning site. A cascade among the detector's electrons makes the record irreversible |

Steps 1 and 2 are numerically identical in the two columns. Only step 3 differs.

## 3. Result

For independent memoryless clocks with rates λ_m, the probability that clock m fires first is λ_m divided by the sum of all rates. With λ_m proportional to the squared modulus at site m, this is the Born distribution, for any number of sites and any grouping of sites into detectors.

## 4. Simulation

**Setup.** A two-slit amplitude ψ(x) = cos(πx)·sinc(x/3) falls on 15 detectors spanning three fringes, with 20 atoms per detector. Each trial is one quantum. Every atom draws an exponential waiting time from its rate, and the earliest fires. Each rule was run for 200,000 trials. Detector counts are compared with the Born weights by chi-square with 14 degrees of freedom; the 95 percent critical value is 23.7.

| Rule for the single event | χ² vs Born | Central detector share (Born 0.1651) |
|---|---|---|
| Random draw from the Born distribution | 4.9 | 0.1661 |
| First to fire, rate = energy density | 10.7 | 0.1654 |
| First to fire, with a random phase factor on each atom's coupling, redrawn each trial | 12.2 | 0.1640 |
| Control: largest deposit wins, with random-phase noise added to the wave | 980,332 | 0.987 |

**The central result: a first-to-fire race among detector sites, with firing rates proportional to the local energy of the wave and random phases at the individual atoms, accumulates to the Born rule distribution.**

The race is statistically indistinguishable from the random draw. Random phases in the detector do not change the outcome distribution. The random numbers in the race are the waiting times of the individual sites; no site location is drawn. The control shows that noise on the interference pattern is not enough: without the race, the brightest detector takes nearly every event.

**Timing.** The total firing rate is about the detector's absorption probability divided by the packet duration, so the event occurs while the packet is passing. For silicon at 800 nm, a given atom's chance of firing is about 2 × 10⁻¹⁴ per photon and about 5 × 10¹³ atoms are illuminated, giving a total chance of order one. The delay is therefore a fraction of the packet duration: picoseconds for down-conversion photons, nanoseconds for quantum-dot or atomic sources. Event times follow the packet's intensity envelope, as in the standard theory.

## 5. Limits

1. The rate law contains the squared modulus. The Born rule is relocated to a physical rate, not derived.
2. Outcome frequencies and event times match standard quantum mechanics. The recipe makes no new prediction for single-quantum detection.
3. Absorbing the whole quantum at one site, with no other site firing, is nonlocal. This is Einstein's 1927 objection, and Bell's theorem shows any single-outcome account must contain such a step [7]. Single-photon anticorrelation confirms that only one site fires [8].
4. The recipe covers one quantum in ordinary space. Entangled pairs are left to later work.

## References

1. Born, M. (1926). Zur Quantenmechanik der Stoßvorgänge. *Zeitschrift für Physik* 37, 863–867.
2. Born, M., and Einstein, A. (1971). *The Born–Einstein Letters*. Macmillan. Letter of 4 December 1926.
3. Bacciagaluppi, G., and Valentini, A. (2009). *Quantum Theory at the Crossroads: Reconsidering the 1927 Solvay Conference*. Cambridge University Press.
4. Bohr, N. (1949). Discussion with Einstein on epistemological problems in atomic physics. In Schilpp, P. A., ed., *Albert Einstein: Philosopher-Scientist*.
5. Feynman, R. P., Leighton, R. B., and Sands, M. (1965). *The Feynman Lectures on Physics*, Vol. III, ch. 1.
6. Einstein, A. (1917). Zur Quantentheorie der Strahlung. *Physikalische Zeitschrift* 18, 121–128.
7. Bell, J. S. (1964). On the Einstein Podolsky Rosen paradox. *Physics* 1, 195–200.
8. Grangier, P., Roger, G., and Aspect, A. (1986). Experimental evidence for a photon anticorrelation effect on a beam splitter. *Europhysics Letters* 1, 173–179.
