# Stable Diffusion base model versions

The Krita AI Diffusion plugin uses models which are based on the Stable Diffusion architecture. It supports two different base models called "Stable Diffusion 1.5" (SD1.5) and "Stable Diffusion XL" (SDXL). These base models are refined, extended and supported by various other models (LoRA, ControlNet, IP-Adapter) which must match the base architecture. **They are not compatible!** You can choose which version to work with, but need to have all matching extensions installed. Individual components cannot be mixed.

## Stable Diffusion 1.5

Released in October 2022 this is the older of the two base models. It was trained on 512x512 images originally, although custom checkpoints also work well for resolutions up to 768. It is still suitable for much higher resolutions by generating a low resolution image first and then upscaling it - the Plugin will do this automatically.

Advantages of SD 1.5:
* Requires less GPU memory (VRAM)
* Requires less disk space
* More community content available (checkpoints, LoRA)
* Wider range of control modes available

## Stable Diffusion XL

Released in July 2023 this is a newer base model designed for higher fidelity. It was trained on images with a total of 1024x1024 pixels (various aspect ratios).

Advantages of SD XL:
* Better quality at high resolutions
* Improved understanding of text prompts

## Installation
When using the Plugin's automatic installer you can select which base model ("workload") you want to install. You have to choose at least one, but can opt to install both.

![workload-installation](https://github.com/Acly/krita-ai-diffusion/assets/6485914/f32ee3e4-b57d-4c26-982d-15d682246cd2)

Optional packages and extensions listed below are available for selection depending on whether the base workload is installed. Some packages like upscalers are unrelated to diffusion and work for both, others have separate packages available for each version. Not all extensions exist for both versions.

## Styles
Styles indicate which base model version they use with an icon. This is derived from the selected checkpoint, which can be either SD1.5 or SDXL. Any LoRA you add must match the base model.

Note that the Plugin automatically filters styles for workloads you don't have installed. In the Style configuration menu you will see a notification if there is an issue.

![SD versions in Style selection](https://github.com/Acly/krita-ai-diffusion/assets/6485914/4982ac56-da4c-4a8d-94f6-17043a7a4ce7)
