# Physical Grounding of the Material Feel Map

### Anchoring each sensory dimension to something you can measure

*A companion to the Material Feel Map and SENSUS-Bench. It answers the first question a materials scientist asks: how do you turn a word like "soft" into a number?*

---

## Why this document exists

The Map's six dimensions were each chosen for a reason. Every one corresponds to a physical property of a surface that an instrument can measure. That is what keeps a shared vocabulary from being a pile of subjective adjectives. The perceptual dimensions are well established in psychophysics. The standard reference is Okamoto, Nagano & Yamada (2013), whose review consolidates decades of work into roughly five perceptual axes: macro-roughness, fine-roughness, warmness, hardness, and a friction/moisture axis.

The table below pairs each dimension with the physical quantity under it, a lab-grade way to measure that quantity, and a cheap proxy you can use before owning any serious equipment. The two-tier split is deliberate. It lets an early pilot run on a durometer and a kitchen scale, while still pointing at the precise metrology the full benchmark will need.

## The mapping

| # | Map dimension | Poles | Physical basis | Metric (symbol) | Typical unit | Lab-grade method | Cheap-tier proxy |
|---|---------------|-------|----------------|-----------------|--------------|------------------|------------------|
| 1 | **Texture** | rough ↔ smooth | Surface topography | Roughness *Ra*, *Rz*; spatial wavelength | µm | Optical or stylus profilometry | USB microscope + image analysis; graded reference set (e.g. abrasive grits) |
| 2 | **Give** | hard ↔ soft | Compliance of the surface | Elastic modulus *E* (or Shore hardness) | MPa (or Shore A/D) | Instrumented indentation / universal testing machine | Shore durometer (~$50–150) |
| 3 | **Temperature** | cool ↔ warm | Rate at which the surface draws heat from skin | Thermal effusivity *e* | J·m⁻²·K⁻¹·s⁻¹ᐟ² | Transient plane-source ("hot-disk") | Fixed-time contact thermocouple vs. a reference material |
| 4 | **Moisture** | dry ↔ moist | Surface tack and moisture (the "moistness" facet of friction) | Tack / pull-off force; surface energy | N; mN·m⁻¹ | Probe-tack test; contact-angle goniometry | Qualitative tack + friction-sled behaviour |
| 5 | **Grip** | slippery ↔ grippy | Friction against skin (the magnitude facet) | Kinetic / static friction coefficient *µ* | dimensionless | Tribometer against a skin-mimic probe | Inclined-plane slip test, or a sled + load cell |
| 6 | **Weight** | light ↔ substantial | Mass and density | Bulk density *ρ* (or areal density for flexibles) | kg·m⁻³ (or g·m⁻²) | Precision balance + caliper / pycnometry | Kitchen scale + ruler |

## Notes that keep it honest

**Moisture and grip are two facets of one axis.** In the psychophysics literature, stickiness/slipperiness and moistness/dryness load onto a single friction dimension. The Map splits them into two controls because they feel distinct. A dry rubber grip and a damp gel are both high-friction, yet they read very differently. Whether they hold up as two independent axes or collapse back into one is an empirical question the benchmark can settle. Treat rows 4 and 5 as a hypothesis, not a settled fact.

**Weight sits slightly outside the classic texture dimensions.** Okamoto's axes describe a surface; weight is a property of the object. It earns a place on the Map because heft shifts meaning, since a heavier bottle reads as more premium. But it is measured differently, by mass and density rather than surface metrology, and should be reported that way.

**Friction is not a fixed number.** The coefficient between skin and a surface depends on skin hydration, normal force, and sliding speed. A friction measurement is only comparable when those are held constant (see conditions below). Report the conditions alongside the value.

**Thermal effusivity, not conductivity, is the right quantity for warmth.** What the hand reads as "cool" is how fast heat leaves the skin on contact. That depends on thermal effusivity, which combines conductivity, density, and heat capacity, rather than on conductivity alone. For ranking, a cheap proxy is enough: measure how far a fixed-time contact reading drops against a reference block. You can order materials that way without a hot-disk rig.

## Measurement conditions (so results are comparable)

Two procedural choices from standard psychophysics matter enough to state up front, because without them no two labs' numbers can be compared:

- **Contact mode.** Separate passive touch (a motorized stage moves the material across a still finger at a fixed normal force, around 0.5 N, and velocity, around 50 mm·s⁻¹) from active touch (the participant swipes freely). The two give different data. Pick one as primary and hold it constant.
- **Environment.** Fix room temperature (about 21–23 °C) and relative humidity (about 40–50%). Skin moisture and a material's apparent warmth both drift with ambient conditions, so an uncontrolled room adds noise to rows 3, 4, and 5.

## How this plugs into SENSUS

This is the instrumental layer of the stack. In SENSUS-Bench terms, the metrics in the table are the Phase-1 material characterization: the feature vector `[Ra, E, e, µ, ρ, …]` that a model receives as input, and against which human feeling-and-meaning responses are regressed. The Map gives the human-readable dimensions. This document gives their measurable coordinates. The benchmark tests how well the two line up.

Worth being clear about what this is and is not. None of it is the hard or novel part. The link from physical signal to perception is settled materials science and psychophysics, and this table summarizes it. SENSUS's contribution starts one layer up, in the feeling and meaning these inputs give rise to, and in the open benchmark that measures the mapping. This document is here so the lower layer stays rigorous and reproducible, which frees the upper layer to be where the new work happens.

---

**Reference**

- Okamoto, S., Nagano, H., & Yamada, Y. (2013). Psychophysical dimensions of tactile perception of textures. *IEEE Transactions on Haptics, 6*(1), 81–93.

*Measurement methods above follow standard materials-science and psychophysics practice (for example, Shore hardness per ASTM D2240; surface roughness as ISO surface-texture parameters). Verify the current standard for any metric before formal use.*

*Physical Grounding of the Material Feel Map. Content licensed CC BY 4.0.*
