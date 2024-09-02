Low Rank Adapation

Instead of re-doing the whole model, LoRA freezes the weights* and parameters of the model as they are. Then on top of this original model, it adds a lightweight addition called a low-rank matrix, which is then applied to new inputs to get results specific to the context. The low-rank matrix adjusts for the weights of the original model so that outputs match the desired use case.

Similar affect to [Fine-Tuning](./Fine-Tuning) but it's significantly less expensive

[LoRA in Stable Diffusion](https://machinelearningmastery.com/using-lora-in-stable-diffusion/)