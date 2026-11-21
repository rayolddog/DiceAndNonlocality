# Individual records from a real wave

**Version 3.0**
**12 November 2026**

**Draft text:** Grok
**Mechanism:** as specified by John M. Bramble

---

## Abstract

The Schrödinger equation already gives the wave at a detector, and the squared modulus of that wave already gives the distribution of energy across the detector. The step this manuscript replaces is the one that turns that distribution into a single record. In the Copenhagen reading the wave is a device for calculating probabilities, the Born rule converts the wave into a distribution, and a random draw selects one outcome. The mechanism proposed here keeps the wave as a physical wave. At the surface of a row of detectors the incident packet, the wave packets of electrons bound near the surface, and a contribution from the quantum vacuum interfere as complex waves. The bound electrons and the vacuum add unbiased phase noise. A record is made when an electron at one site tunnels through the barrier into a higher orbit, and the whole quantum is taken at that site. Further interactions with bound electrons of unrelated phases disperse the phase record, so the incident packet cannot be reconstructed. A sequence of such records accumulates to the same distribution the Born rule would have assigned.

---

## 1. The debate

In 1926 Max Born proposed that the square of the Schrödinger wave gives the probability of a result in a scattering experiment [Born 1926a, Born 1926b]. That rule became the link between the wave function and the laboratory. Niels Bohr built the Copenhagen reading around it. The wave function is the instrument for predicting the statistics of a specified experimental arrangement. A single run yields one outcome. The wave does not describe that outcome as a physical object evolving through the apparatus. Complementarity says what kind of account is not to be asked for [Bohr 1928, Bohr 1935].

Albert Einstein accepted the statistical success of the rule and rejected it as a finished account of one event. In December 1926 he wrote to Born that he was convinced the theory did not bring us closer to the old one's secrets, because the old one at least played dice in a way one could picture, and "He does not play dice" [Einstein 1926]. At the Solvay meeting in 1927 he pressed the point with a screen: the wave is spread over the whole screen, yet the mark appears at one place [Bacciagaluppi & Valentini 2009]. In 1935, with Podolsky and Rosen, he made the objection sharp. If the wave function were a complete description of physical reality, a measurement here would determine a quantity there without a physical process that accounts for the individual result. Quantum mechanics, they concluded, is incomplete [Einstein, Podolsky & Rosen 1935]. Bohr's reply did not supply that process. It relocated the description to the entire phenomenon, arrangement included [Bohr 1935].

Erwin Schrödinger, who had written the equation of motion for the wave, was no happier with a probability reading or with an instantaneous collapse. His 1935 papers treat the wave as the real object and the jump into one outcome as an unresolved break in the theory [Schrödinger 1935].

The disagreement can be stated without settling it. Born and Bohr held that the theory's job is the distribution of outcomes. Einstein and Schrödinger held that a complete theory also has to say what happens in one run, when an extended wave leaves one mark. This manuscript takes the second demand as its question and does not pretend that either of them endorsed the mechanism below. The historical fact used here is only this: the standard calculation ends by sampling a distribution, and that ending was the point Einstein would not accept.

Nothing in the proposal re-derives the quadratic rule. The energy distribution across the detector is the one the interference calculation already gives. The change is the last step. One record is produced by the physics at the surface, and the distribution is what many records make.

## 2. The recipe

Consider a row of detector sites illuminated by one wave packet. The comparison is between the usual calculation of a single outcome and the mechanism proposed in its place.

| Step | Copenhagen calculation | Proposed mechanism |
| --- | --- | --- |
| 1. Propagation | The Schrödinger equation evolves the wave function up to the detector. | The same equation evolves the same wave. The wave is a real physical wave, not only a catalog of probabilities. |
| 2. Amplitude at the surface | The amplitude on each site is the incident wave packet, evaluated at that site. | The local complex amplitude is the sum of three contributions: the incident packet, the wave packets of electrons bound to atoms near the surface, and a contribution from the quantum vacuum at the surface. |
| 3. Energy across the row | The Born rule converts the amplitude into an energy share proportional to the squared modulus. That share is a probability. | The deposited energy is the squared modulus of the summed complex wave. Its average across runs is the same distribution. The bound electrons and the vacuum add phase noise with no preferred direction, so they do not move the average. |
| 4. One record | A random number generator draws one site with probability equal to its share. The wave function is then declared to have collapsed. | Each site can raise a bound electron through the surface barrier by tunneling. The tunneling rate follows that site's share of the energy. The first site to tunnel takes the entire quantum. |
| 5. After the record | The collapse postulate removes every other branch. | The electron that has tunneled interacts with other bound electrons in the solid. Those electrons have unrelated phases. The cascade copies the phase information of the incident packet until it cannot be gathered back. |
| 6. Many records | The histogram of random draws approaches the Born distribution. | The histogram of tunneling sites approaches the same distribution, because each site's chance of being first is its share of the energy. |

The two calculations agree through step 3. They separate at step 4. One samples a list of probabilities. The other follows a rate at the surface until one site has the quantum.

## 3. The wave at the surface

The incident packet arrives as a complex wave. On a row of sites its phase and magnitude are fixed by the path it has traveled, as the Schrödinger evolution, or the equivalent optical propagation, prescribes. At each site that wave meets electrons bound to atoms near the surface. Those electrons are themselves complex waves, with phases of their own. The quantum vacuum at the surface contributes a further complex amplitude. The local field that can drive a transition is the sum of the three.

The energy available at a site is quadratic in that sum. Writing the incident contribution as \(A_m\) and the surface contributions, electrons plus vacuum, as a noise amplitude \(N_m\),

\[
E_m \propto |A_m + N_m|^2.
\]

The phases inside \(N_m\) are unbiased. They have no preferred sign, and they fluctuate many times during the wait for a tunneling event. The average of \(E_m\) is then proportional to \(|A_m|^2\), up to a noise floor that is the same from site to site and is subtracted with the dark rate. The pattern calculated from the incident wave alone is the pattern the detector averages to. The surface terms are why two runs with the same incident wave do not mark the same site. They are not an extra draw from the Born list. They are fields present at the surface.

The vacuum piece is the smaller of the two noise contributions. The phases of the bound electrons differ from atom to atom and from moment to moment, and they dominate the variation. If either contribution were biased, the average energy would shift away from \(|A_m|^2\) and the accumulated marks would follow the shifted pattern. Unbiased means that the average of the cross term between \(A_m\) and \(N_m\) vanishes.

## 4. The individual record

A bound electron sits behind a barrier. Tunneling through that barrier, into a higher orbit or into the conduction states of the solid, is the registration. While no electron has tunneled, the quantum has not been taken. The rate at site \(m\) is proportional to the mean energy deposited there,

\[
\Gamma_m = \kappa \, s_m, \qquad s_m = \frac{|A_m|^2}{\sum_n |A_n|^2},
\]

with one constant \(\kappa\) set by the barrier and the coupling, common to the row. These are independent waits. The probability that site \(m\) is the first to tunnel is the rate of \(m\) divided by the sum of the rates,

\[
P(m) = \frac{\Gamma_m}{\sum_n \Gamma_n} = s_m.
\]

That is the Born weight of the site, obtained here as the chance of winning a race of physical rates rather than as a probability assigned to a draw.

The wave packet is extended along the whole row. The quantum is not. The first tunneling event takes the entire photon at that one site, and the rates at every other site drop to zero because the quantum has been absorbed. This is the nonlocality Einstein pointed at with the screen. The wave is everywhere along the row. The energy of one photon is collected at the site where the barrier is crossed. The mechanism does not remove that nonlocality. It says what local event the collection is attached to.

The race has to be a race of rates, not a race of instantaneous peaks. If instead one froze the noisy pattern and awarded the quantum to whichever site was brightest at that instant, the sites that are already bright in \(|A_m|^2\) would win more often than their share. A barrier that is crossed only after a site has stored up some fixed fraction of a quantum has the same fault: a site born above that fraction wins too easily. The rule that preserves the distribution is the proportional rate above, with the noise fluctuating many times before the typical wait \(1/\kappa\), so that each site tunnels according to its average energy.

## 5. Irreversibility

Tunneling is the record. It is not yet the end of every trace of the incident packet. The electron that has crossed the barrier interacts with other electrons bound in the solid. Those electrons carry phases that were not set by the incident packet. Each interaction copies phase information into a larger set of degrees of freedom. After a cascade of such interactions, reconstructing the incident packet would require reversing phases that are spread through the solid and are unrelated to one another. That reconstruction does not occur.

There is a short interval in which a reversal is still conceivable: after the local amplitude has built up, and before the cascade has dispersed it. Once the cascade has run, the mark remains and the wave that made it cannot be put back. No additional postulate is required to declare the wave function collapsed. The packet has been absorbed whole at one site, and the information that would undo that absorption has been dispersed through the detector.

## 6. Accumulation

One record is one site. It is not a sample drawn from a stored distribution. The next photon, prepared the same way, meets a new set of surface phases and a new vacuum contribution, and its tunneling site is a new draw from the same rates. Because \(P(m) = s_m\) for each photon, the fraction of marks at each site approaches \(s_m\) as the number of photons grows. The histogram becomes the Born distribution. The distribution is the consequence of the records. It is not the device that selected them.

The same histogram is produced by drawing random numbers from \(s_m\). The two procedures can be told apart only where the mechanism's conditions fail. A bias in the surface phases, a noise pattern that is frozen rather than fluctuating, or a record taken before the whole quantum has been gathered, moves the histogram off \(s_m\). A random number generator weighted by \(s_m\) cannot make those errors, because it never consults the surface. Those departures are the experimental content of the proposal.

## 7. Scope

The proposal is a mechanism for the last step of a detection. The Schrödinger evolution up to the surface is left as it is. The squared modulus remains the average energy. Born's rule remains the correct distribution of a long run.

The claim is that a single run is not completed by sampling that distribution. It is completed by unbiased interference with the surface and the vacuum, by a tunneling rate proportional to the local share, by absorption of the whole quantum at the first site to tunnel, and by a cascade that disperses the phase record. That sequence is a physical calculation of one result. The Born distribution is what the results accumulate to.

## References

- Bacciagaluppi, G. and Valentini, A. (2009). *Quantum Theory at the Crossroads: Reconsidering the 1927 Solvay Conference*. Cambridge University Press.
- Bohr, N. (1928). The quantum postulate and the recent development of atomic theory. *Nature* **121**, 580–590.
- Bohr, N. (1935). Can quantum-mechanical description of physical reality be considered complete? *Physical Review* **48**, 696–702.
- Born, M. (1926a). Zur Quantenmechanik der Stoßvorgänge. *Zeitschrift für Physik* **37**, 863–867.
- Born, M. (1926b). Quantenmechanik der Stoßvorgänge. *Zeitschrift für Physik* **38**, 803–827.
- Einstein, A. Letter to Max Born, 4 December 1926. In Born, M. (1971), *The Born–Einstein Letters*. Macmillan.
- Einstein, A., Podolsky, B. and Rosen, N. (1935). Can quantum-mechanical description of physical reality be considered complete? *Physical Review* **47**, 777–780.
- Schrödinger, E. (1935). Die gegenwärtige Situation in der Quantenmechanik. *Naturwissenschaften* **23**, 807–812, 823–828, 844–849.
