# Aesthetic Post-Training Diffusion Models from Generic Preferences with Step-by-step Preference Optimization

<p>
    Generating visually appealing images is fundamental to modern text-to-image generation models. 
    A potential solution to better aesthetics is direct preference optimization (DPO), 
    which has been applied to diffusion models to improve general image quality including prompt alignment and aesthetics. 
    Popular DPO methods propagate preference labels from clean image pairs to all the intermediate steps along the two generation trajectories. 
    However, preference labels provided in existing datasets are blended with layout and aesthetic opinions, which would disagree with aesthetic preference. 
    Even if aesthetic labels were provided (at substantial cost), it would be hard for the two-trajectory methods to capture nuanced visual differences at different steps.
</p>
<p>
    To improve aesthetics economically, this paper uses existing generic preference data and introduces step-by-step preference optimization 
    (SPO) that discards the propagation strategy and allows fine-grained image details to be assessed. Specifically, 
    at each denoising step, we 1) sample a pool of candidates by denoising from a shared noise latent, 
    2) use a step-aware preference model to find a suitable win-lose pair to supervise the diffusion model, and 
    3) randomly select one from the pool to initialize the next denoising step. 
    This strategy ensures that diffusion models focus on the subtle, fine-grained visual differences 
    instead of layout aspect. We find that aesthetic can be significantly enhanced by accumulating these 
    improved minor differences.
</p>
<p>
    When fine-tuning Stable Diffusion v1.5 and SDXL, SPO yields significant 
    improvements in aesthetics compared with existing DPO methods while not sacrificing image-text alignment 
    compared with vanilla models. Moreover, SPO converges much faster than DPO methods due to the step-by-step 
    alignment of fine-grained visual details. Code and models are available at 
    <a href="https://github.com/RockeyCoss/SPO" target="_blank">link</a>.
</p>
