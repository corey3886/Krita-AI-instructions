# Selection Fill

Using selections to modify parts of the image is a key feature of the plugin. It allows you to apply AI generation exactly where
you want. You can work on an image iteratively, mixing traditional painting tools and generated content as needed.

## Generation mode

Creating a selection will transform the "Generate" button to reflect the operation.
By default this is either _Fill_, or _Expand_, depending on the selection context.
But there is also a drop-down which allows you to choose a more specific action which
may yield better results.

![release-1 14 0-inpaint-menu](https://github.com/Acly/krita-ai-diffusion/assets/6485914/67247461-3712-4fa4-bd8b-eb346578f1bb)

### Fill

This is a general purpose mode that fits most scenarios where you want to replace a part of the image with something
similar. It may generate new things, but is biased towards using colors found in the vicinity of the selection.
It tries to strike a balance between flexibility to make changes and blending in with the rest of the image.

| Original | Mask | Result |
|-|-|-|
| ![original](https://github.com/Acly/krita-ai-diffusion/assets/6485914/74c53aef-cae5-4037-a47c-8db87ce71d20) | ![fill-mask](https://github.com/Acly/krita-ai-diffusion/assets/6485914/e5111191-d9c0-4d73-a799-c9ffe2677933) | ![fill-result](https://github.com/Acly/krita-ai-diffusion/assets/6485914/d91669f7-a413-45ec-b55b-2888870b8c05) |


### Expand

This mode is geared to expanding the image at the left, right, top or bottom. You can expand into more than one direction
at once, but it requires more resources (memory and time). The easiest way to expand the canvas is to use Krita's crop tool
(hotkey: C) and click anywhere into the image. You can now resize the canvas at the sides. Select the blank areas and click
Expand to generate content.

| Original | Mask | Result |
|-|-|-|
| ![original](https://github.com/Acly/krita-ai-diffusion/assets/6485914/74c53aef-cae5-4037-a47c-8db87ce71d20) | ![release-1 14 0-inpaint-expand-mask](https://github.com/Acly/krita-ai-diffusion/assets/6485914/c306b3da-2061-49d5-abba-48e8682d1184) | ![release-1 14 0-inpaint-expand-image](https://github.com/Acly/krita-ai-diffusion/assets/6485914/57b5a20a-2c5c-430f-ab72-732b6e64783b) |

_Expand_ completely ignores existing content in the selection area, it can be blank or anything else. It attempts to blend in
with the colors used at the border of the selection, and prefers to generate more of the same, rather than being overly creative.

### Add Content
Use this mode to add new things to the image. This mode requires you to use text or control layers to describe the new content
you want to see. It generates with the flexibility to drastically deviate from the colors seen in the rest of the image, and
may not blend as well as other modes.

| Original | Mask | Result |
|-|-|-|
| ![original](https://github.com/Acly/krita-ai-diffusion/assets/6485914/74c53aef-cae5-4037-a47c-8db87ce71d20) | ![release-1 14 0-inpaint-add-mask](https://github.com/Acly/krita-ai-diffusion/assets/6485914/0eb8ba61-7b8d-40f8-8154-165277b5a8a6) | ![release-1 14 0-inpaint-add-image](https://github.com/Acly/krita-ai-diffusion/assets/6485914/1bc87a8a-ed3c-49e9-b7c2-60091d3248e8) |


### Remove Content
This mode is geared towards object removal. It ignores existing content in the selection area and fills it with a continuation
of the surroundings instead.

| Original | Mask | Result |
|-|-|-|
| ![original](https://github.com/Acly/krita-ai-diffusion/assets/6485914/74c53aef-cae5-4037-a47c-8db87ce71d20) | ![release-1 14 0-inpaint-remove-mask](https://github.com/Acly/krita-ai-diffusion/assets/6485914/b34f8486-1083-48d7-84cc-db950f1449c9) | ![release-1 14 0-inpaint-remove-image](https://github.com/Acly/krita-ai-diffusion/assets/6485914/45bc4c80-743b-4775-83c8-dd49468b08d2) |

### Replace Background
An experimental mode where you can select a forground object. The selected content is kept, and everything else in the image is
replaced. This mode requires you to use text to describe the new background.

| Original | Mask | Result |
|-|-|-|
| ![original](https://github.com/Acly/krita-ai-diffusion/assets/6485914/74c53aef-cae5-4037-a47c-8db87ce71d20) | ![release-1 14 0-inpaint-replace-mask](https://github.com/Acly/krita-ai-diffusion/assets/6485914/8291ebfd-3f77-47a1-ae0f-984fd057296a) | ![release-1 14 0-inpaint-replace-image](https://github.com/Acly/krita-ai-diffusion/assets/6485914/d70f778e-d4b8-4fae-8038-f581ea8421d2) |

_Note:_ inpaint models aren't trained for this particular use case, complex interactions between foreground/background require some luck.

## Custom Generation

If none of the modes quite fit, there is also the option to configure generation parameters manually.

![custom-inpaint-menu](https://github.com/Acly/krita-ai-diffusion/assets/6485914/bde041d3-ffca-4844-83f0-4ded84047ae6)

* **Seamless:** When enabled, an inpaint model is used to make generated content blend in with the existing image as best as possible.
  In some cases you may want to explicitly disable this, for example when generating a single panel within a comic page. When disabled,
  generation will behave as if the seleted area was its own image within the canvas, independent of the rest.
* **Focus:** When disabled, the text you enter describes the entire _context area_ (see below). Enable this to focus your prompt
  exclusively on the selected area instead.
* **Fill:** This defines how the selected area is filled before generation, and can influence what kind of results are possible.
  * **None** means the image content is not touched at all, which allows you to paint it over as you see fit.
  * **Neutral** allows to generate anything without bias.
  * **Blur** will blur existing and surrounding content together.
  * **Border** ignores existing content and takes colors only from the surrounding.
  * **Inpaint** fills the selected area using a small, specialized AI model.

Visualization of the fill modes: (note that these are not final results, they only show pre-processing)

| Input | Neutral | Blur | Border | Inpaint |
|-|-|-|-|-|
| ![preprocess-input](https://github.com/Acly/krita-ai-diffusion/assets/6485914/cbcfb8b5-4dce-40eb-bd9f-c7c5b4e1eb06) | ![preprocess-neutral](https://github.com/Acly/krita-ai-diffusion/assets/6485914/2abf0f7b-31e0-4bb3-8468-6b6b3c0203b6) | ![preprocess-blur-65](https://github.com/Acly/krita-ai-diffusion/assets/6485914/44c1f71f-ebaa-4a3d-89dd-cbb91532e95b) | ![preprocess-navier-stokes](https://github.com/Acly/krita-ai-diffusion/assets/6485914/31f83df1-7ad1-4d5a-8c1f-8406b0baa36e) | ![preprocess-mat](https://github.com/Acly/krita-ai-diffusion/assets/6485914/b2d53ec5-8d1f-47f8-8633-9143b0fbbef5) |


### Context area

When generating content for the selected area, part of the surrounding image is processed as "context". This is required to get
good results that blend in. A larger context area improves coherency with the rest of the image, at the cost of slower speed 
and increased memory requirements. You always pay for the entire context even if it isn't touched, not just the masked area.

By default the context is selected automatically. It can be influenced by changing _Settings > Diffusion > Selection Padding_.
Note that there are also internal constraints and tweaks to select a suitable region. Custom Generation offers some additional options:
* **Selection Bounds:** use only the selection area. This makes sense when _Seamless_ is disabled, but won't allow it to work properly if it's on.
* **Entire Image:** use the entire image as context. Best coherency, but slow and image quality suffers at high resolutions.
* **<Custom Layer>:** use the area indicated by a Selection Mask or Transparency Mask layer. Full control!

### Working with Selection Masks

This is an example workflow that uses selection masks to define a custom context.

First, make sure you have "Global Selection Mask" enabled in Krita.

![custom-inpaint-global-selection](https://github.com/Acly/krita-ai-diffusion/assets/6485914/0595d119-aae8-40e8-8406-99ed26fdc490)

Use rectangular selection tool to mark your context area.

![custom-inpaint-context-selection](https://github.com/Acly/krita-ai-diffusion/assets/6485914/069b1ad2-58fa-4543-836b-374393ef8cde)

Save your selection mask (the dashed circle icon marked below), and optionally give it a nice name. Then create the selection
which you want to fill (like some badly generated hands).

![custom-inpaint-context-layer](https://github.com/Acly/krita-ai-diffusion/assets/6485914/25af02b5-8437-4ba2-828d-ca847d0940f4)

In custom generation menu, select your mask as context. You can reuse it any time you need.

![custom-inpaint-context-menu](https://github.com/Acly/krita-ai-diffusion/assets/6485914/c79a6009-1fa3-4173-b123-592c4afc2cfc)


