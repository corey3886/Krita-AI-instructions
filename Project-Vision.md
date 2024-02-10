The goal of this project is to aid creatives in painting and editing images with the support of generative AI.
It aims to be an intuitive and productive tools to apply AI with a high degree of artistic control.
It should be accessible to an audience that is willing to invest some time and effort to achieve the best results,
and allow flexible customization where required.

### Motivation

Many early AI apps and services focus on the ability generate entire images from text. Language is something
all humans learn and have an intuitive proficiency for, which makes it an incredibly accessible tool. It
is however not necessarily a very precise or efficient way to create visual content. It excels at quickly
generating something out of a general idea, but fails at realizing more concrete imagination. A text
description always leaves large room for interpretation, and results are most of all very random.
More verbose and detailed language has its limits. For one, current AI model's understanding of complex
scenarios can be poor. But even as this improves over time, describing what you envision in great detail
can be difficult and tedious at best, and plain impossible in many cases.

_"A picture is worth a thousand words"_ -- Sketching, painting, 3D modeling
are all valuable methods to conceptualize and flesh out what we envision.
With these inputs to influence generative AI, users can achieve a high degree of control, and use
AI to the extent they are comfortable with - to speed up and optimize their workflows, but not always replace them.
This project approaches generative AI as a tool to fill in precisely where
requested, to ease tedious and repetitive work, be an adequate substitute for lack of time or skill, and enable projects
such as comics, animation and games that would not be feasible otherwise.

### Technology

This is achieved by supporting a combination methods:
1. **Refinement (img2img).** This refers to running the diffusion process not on random noise, but to
   use an existing image as input. The amount of noise added is controlled by the user and steers how
   much the original content may change.
2. **Selection (inpainting).** Precise artistic control may only be required in parts of the image,
   while others can be left to be filled by AI. Users should always be able to control which parts
   of the image are modified, with generated content automatically blending in with the rest of the image.
3. **Control layers (ControlNet et al).** These are additional input images which guide generation to
   follow a sketch, line art, depth map, etc.

### Design

Input images can come from any source: photos, paintings, renders or generated from text. To create,
manage, arrange and combine all those inputs, having powerful image editing tools is essential.
This is why a plugin for Krita makes sense. Integrating with its existing capabilities and becoming
a part of its interface is critical to achieve productive workflows. This leads to the following
guidelines for interface design:

- **Concise.** The canvas is central and can't be big enough. On top of that, the plugin UI has to compete
  for screen real estate with the various dockers Krita brings. Consider generative AI as one tool of many, not
  the main show.
- **Simple.** The plugin should be usable without technical knowledge of Diffusion models.
  Things like samplers, CFG, clip skip, etc. are not conductive for working towards a particular result. Features
  should be identfied by what they do, not what underlying technology they use.
- **Flexible.** Resolution is implicitly defined by the canvas and selection. The plugin should take care of
  technical constraints and automatically scale as needed. Features should synergize and work together by default.
- **Selective.** Rather than providing a large list of choices to do very similar things, the plugin
  should implement only the best approach. This may involve some trade-offs.
- **Customizable.** Not every use case can be detected automatically, and current AI models are not flexible
  enough yet to cover every scenario. For those more technically inclined, local customization is a considerable strength.
  It's important that it does not get in the way of productivity.

### Comparison
