# Compute in Transit 04 — The Fixed-Band Experiment

Can DeMo's top-k selection, which needs comparisons, be replaced by a fixed frequency band, which a photonic link module (arXiv:2608.21536) could compute in transit? A 15.8M-parameter GPT trained on TinyStories with eight simulated workers says no: every fixed band ends more than a nat above top-k, and half the bytes per step does not buy the loss back. The deck shows the loss and the bytes (payload and wire, with an interactive ring calculator), the captured energy that explains it, how the emulated optics first diverged and how feeding back the values sent fixed it, the ENOB and bit-plane tolerance, and what it means for a link module.

The goal behind it: compress gradient traffic on the wire without sending indices, with the compression done for free in the link. A fixed frequency band needs no comparisons, so the optics can compute it in transit, and both ends already know which coefficients are sent. Slide 01b animates the proposed system end to end, from the TX GPU's gradient through the module, the network and the RX GPU, with the error-feedback loop and the bytes on each hop; every frame is computed by a port of the experiment's code.

Topics: DeMo, Fixed band vs top-k, Captured energy, Error feedback, Emulated optics, ENOB.

**Live site:** https://brendanjameslynskey.github.io/CiT_04_Fixed_Band_Experiment/

Part of the [Compute in Transit series](https://github.com/BrendanJamesLynskey/LLM_Hub_Compute_in_Transit). Every number comes from [results/tinystories-gpu/results.md](https://github.com/BrendanJamesLynskey/DeMo_Fixed_Band_Experiment/blob/main/results/tinystories-gpu/results.md) or [docs/optics_investigation.md](https://github.com/BrendanJamesLynskey/DeMo_Fixed_Band_Experiment/blob/main/docs/optics_investigation.md) in [DeMo_Fixed_Band_Experiment](https://github.com/BrendanJamesLynskey/DeMo_Fixed_Band_Experiment), where the code, logs and tests live. The optics' improvement over the exact band is a hypothesis, from one seed per run. Every concept used here is explained, with links, in the [series glossary](https://brendanjameslynskey.github.io/LLM_Hub_Compute_in_Transit/#glossary). Sister series: [Fourier Optics for Inference](https://github.com/BrendanJamesLynskey/LLM_Hub_Fourier_Optics_Inference), [LLM Inference Simulators](https://github.com/BrendanJamesLynskey/LLM_Hub_Inference_Simulators), [FHE Accelerator Simulators](https://github.com/BrendanJamesLynskey/FHE_Hub_Accelerator_Simulators).

Licence: CC BY 4.0.
