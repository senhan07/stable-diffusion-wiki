---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# What is Stable Diffusion

Stable Diffusion is a [deep learning](https://en.wikipedia.org/wiki/Deep\_learning), [text-to-image model](https://en.wikipedia.org/wiki/Text-to-image\_model) released in 2022 based on [diffusion](https://en.wikipedia.org/wiki/Diffusion\_model) techniques. It is primarily used to generate detailed images conditioned on text descriptions, though it can also be applied to other tasks such as [inpainting](https://en.wikipedia.org/wiki/Inpainting), outpainting, and generating image-to-image translations guided by a [text prompt](https://en.wikipedia.org/wiki/Prompt\_engineering). It was developed by researchers from the CompVis Group at [Ludwig Maximilian University of Munich](https://en.wikipedia.org/wiki/Ludwig\_Maximilian\_University\_of\_Munich) and Runway with a compute donation by Stability AI and training data from non-profit organizations.

Stable Diffusion is a [latent](https://en.wikipedia.org/wiki/Latent\_variable\_model) [diffusion model](https://en.wikipedia.org/wiki/Diffusion\_model), a kind of deep generative artificial [neural network](https://en.wikipedia.org/wiki/Neural\_network). Its code and model weights have been released [publicly](https://en.wikipedia.org/wiki/Source-available\_software), and it can run on most consumer hardware equipped with a modest [GPU](https://en.wikipedia.org/wiki/Graphics\_processing\_unit) with at least 8 GB [VRAM](https://en.wikipedia.org/wiki/Video\_random\_access\_memory). This marked a departure from previous proprietary text-to-image models such as [DALL-E](https://en.wikipedia.org/wiki/DALL-E) and [Midjourney](https://en.wikipedia.org/wiki/Midjourney) which were accessible only via [cloud services](https://en.wikipedia.org/wiki/Cloud\_service).

### Development

The development of Stable Diffusion was funded and shaped by the start-up company Stability AI. The technical license for the model was released by the CompVis group at Ludwig Maximilian University of Munich. Development was led by Patrick Esser of Runway and Robin Rombach of CompVis, who were among the researchers who had earlier invented the latent diffusion model architecture used by Stable Diffusion. Stability AI also credited [EleutherAI](https://en.wikipedia.org/wiki/EleutherAI) and [LAION](https://en.wikipedia.org/wiki/LAION) (a German nonprofit which assembled the dataset on which Stable Diffusion was trained) as supporters of the project.

In October 2022, Stability AI raised US$101 million in a round led by [Lightspeed Venture Partners](https://en.wikipedia.org/wiki/Lightspeed\_Venture\_Partners) and [Coatue Management](https://en.wikipedia.org/wiki/Coatue\_Management).

### Technology

#### Architecture

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Diagram of the latent diffusion architecture used by Stable Diffusion</p></figcaption></figure>

Stable Diffusion uses a kind of [diffusion model](https://en.wikipedia.org/wiki/Diffusion\_model) (DM), called a latent diffusion model (LDM) developed by the CompVis group at [LMU Munich](https://en.wikipedia.org/wiki/LMU\_Munich). Introduced in 2015, diffusion models are trained with the objective of removing successive applications of [Gaussian noise](https://en.wikipedia.org/wiki/Gaussian\_noise) on training images, which can be thought of as a sequence of [denoising autoencoders](https://en.wikipedia.org/wiki/Denoising\_autoencoder). Stable Diffusion consists of 3 parts: the [variational autoencoder](https://en.wikipedia.org/wiki/Variational\_autoencoder) (VAE), [U-Net](https://en.wikipedia.org/wiki/U-Net), and an optional text encoder. The VAE encoder compresses the image from pixel space to a smaller dimensional [latent space](https://en.wikipedia.org/wiki/Latent\_space), capturing a more fundamental semantic meaning of the image. Gaussian noise is iteratively applied to the compressed latent representation during forward diffusion. The U-Net block, composed of a [ResNet](https://en.wikipedia.org/wiki/Residual\_neural\_network) backbone, [denoises](https://en.wikipedia.org/wiki/Noise\_reduction) the output from forward diffusion backwards to obtain a latent representation. Finally, the VAE decoder generates the final image by converting the representation back into pixel space.

The denoising step can be flexibly conditioned on a string of text, an image, or another modality. The encoded conditioning data is exposed to denoising U-Nets via a [cross-attention mechanism](https://en.wikipedia.org/wiki/Attention\_\(machine\_learning\)). For conditioning on text, the fixed, pretrained CLIP ViT-L/14 text encoder is used to transform text prompts to an embedding space. Researchers point to increased computational efficiency for training and generation as an advantage of LDMs.

With 860 millions of parameters in the U-Net and 123 millions in the text encoder, Stable Diffusion is considered relatively lightweight by 2022 standards, and unlike other diffusion models, it can run on consumer GPUs.

#### Training data

Stable Diffusion was trained on pairs of images and captions taken from LAION-5B, a publicly available dataset derived from [Common Crawl](https://en.wikipedia.org/wiki/Common\_Crawl) data scraped from the web, where 5 billion image-text pairs were classified based on language and filtered into separate datasets by resolution, a predicted likelihood of containing a watermark, and predicted "aesthetic" score (e.g. subjective visual quality). The dataset was created by [LAION](https://en.wikipedia.org/wiki/LAION), a German non-profit which receives funding from Stability AI. The Stable Diffusion model was trained on three subsets of LAION-5B: laion2B-en, laion-high-resolution, and laion-aesthetics v2 5+. A third-party analysis of the model's training data identified that out of a smaller subset of 12 million images taken from the original wider dataset used, approximately 47% of the sample size of images came from 100 different domains, with [Pinterest](https://en.wikipedia.org/wiki/Pinterest) taking up 8.5% of the subset, followed by websites such as [WordPress](https://en.wikipedia.org/wiki/WordPress), [Blogspot](https://en.wikipedia.org/wiki/Blogspot), [Flickr](https://en.wikipedia.org/wiki/Flickr), [DeviantArt](https://en.wikipedia.org/wiki/DeviantArt) and [Wikimedia Commons](https://en.wikipedia.org/wiki/Wikimedia\_Commons).

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>The denoising process used by Stable Diffusion. The model generates images by iteratively denoising random noise until a configured number of steps have been reached, guided by the CLIP text encoder pretrained on concepts along with the attention mechanism, resulting in the desired image depicting a representation of the trained concept.</p></figcaption></figure>

#### Training procedures

The model was initially trained on the laion2B-en and laion-high-resolution subsets, with the last few rounds of training done on LAION-Aesthetics v2 5+, a subset of 600 million captioned images which the LAION-Aesthetics Predictor V2 predicted that humans would, on average, give a score of at least 5 out of 10 when asked to rate how much they liked them. The LAION-Aesthetics v2 5+ subset also excluded low-resolution images and images which LAION-5B-WatermarkDetection identified as carrying a [watermark](https://en.wikipedia.org/wiki/Watermark) with greater than 80% probability. Final rounds of training additionally dropped 10% of text conditioning to improve Classifier-Free Diffusion Guidance.

The model was trained using 256 [Nvidia A100](https://en.wikipedia.org/wiki/Ampere\_\(microarchitecture\)) GPUs on [Amazon Web Services](https://en.wikipedia.org/wiki/Amazon\_Web\_Services) for a total of 150,000 GPU-hours, at a cost of $600,000.

#### Limitations

Stable Diffusion has issues with degradation and inaccuracies in certain scenarios. Initial releases of the model were trained on a dataset that consists of 512×512 resolution images, meaning that the quality of generated images noticeably degrades when user specifications deviate from its "expected" 512×512 resolution; the version 2.0 update of the Stable Diffusion model later introduced the ability to natively generate images at 768×768 resolution. Another challenge is in generating human limbs due to poor data quality of limbs in the LAION database. The model is insufficiently trained to understand human limbs and faces due to the lack of representative features in the database, and prompting the model to generate images of such type can confound the model. Stable Diffusion XL (SDXL) version 1.0, released in July 2023, introduced native 1024x1024 resolution and improved generation for limbs and text.

Accessibility for individual developers can also be a problem. In order to customize the model for new use cases that are not included in the dataset, such as generating [anime](https://en.wikipedia.org/wiki/Anime) characters ("waifu diffusion"), new data and further training are required. [Fine-tuned](https://en.wikipedia.org/wiki/Fine-tuning\_\(machine\_learning\)) adaptations of Stable Diffusion created through additional retraining have been used for a variety of different use-cases, from medical imaging to [algorithmically generated music](https://en.wikipedia.org/wiki/Riffusion). However, this fine-tuning process is sensitive to the quality of new data; low resolution images or different resolutions from the original data can not only fail to learn the new task but degrade the overall performance of the model. Even when the model is additionally trained on high quality images, it is difficult for individuals to run models in consumer electronics. For example, the training process for waifu-diffusion requires a minimum 30 GB of [VRAM](https://en.wikipedia.org/wiki/VRAM), which exceeds the usual resource provided in such consumer GPUs as [Nvidia](https://en.wikipedia.org/wiki/Nvidia)'s [GeForce 30 series](https://en.wikipedia.org/wiki/GeForce\_30\_series), which has only about 12 GB.

The creators of Stable Diffusion acknowledge the potential for [algorithmic bias](https://en.wikipedia.org/wiki/Algorithmic\_bias), as the model was primarily trained on images with English descriptions. As a result, generated images reinforce social biases and are from a western perspective, as the creators note that the model lacks data from other communities and cultures. The model gives more accurate results for prompts that are written in English in comparison to those written in other languages, with western or white cultures often being the default representation.

#### End-user fine-tuning

To address the limitations of the model's initial training, end-users may opt to implement additional training to [fine-tune](https://en.wikipedia.org/wiki/Fine-tuning\_\(machine\_learning\)) generation outputs to match more specific use-cases. There are three methods in which user-accessible fine-tuning can be applied to a Stable Diffusion model checkpoint:

* An "embedding" can be trained from a collection of user-provided images, and allows the model to generate visually similar images whenever the name of the embedding is used within a generation prompt. Embeddings are based on the "textual inversion" concept developed by researchers from [Tel Aviv University](https://en.wikipedia.org/wiki/Tel\_Aviv\_University) in 2022 with support from [Nvidia](https://en.wikipedia.org/wiki/Nvidia), where vector representations for specific tokens used by the model's text encoder are linked to new pseudo-words. Embeddings can be used to reduce biases within the original model, or mimic visual styles.
* A "hypernetwork" is a small pretrained neural network that is applied to various points within a larger neural network, and refers to the technique created by [NovelAI](https://en.wikipedia.org/wiki/NovelAI) developer Kurumuz in 2021, originally intended for text-generation [transformer models](https://en.wikipedia.org/wiki/Transformer\_\(machine\_learning\_model\)). Hypernetworks steer results towards a particular direction, allowing Stable Diffusion-based models to imitate the art style of specific artists, even if the artist is not recognised by the original model; they process the image by finding key areas of importance such as hair and eyes, and then patch these areas in secondary latent space.
* [DreamBooth](https://en.wikipedia.org/wiki/DreamBooth) is a deep learning generation model developed by researchers from [Google Research](https://en.wikipedia.org/wiki/Google) and [Boston University](https://en.wikipedia.org/wiki/Boston\_University) in 2022 which can fine-tune the model to generate precise, personalised outputs that depict a specific subject, following training via a set of images which depict the subject.

### Capabilities

The Stable Diffusion model supports the ability to generate new images from scratch through the use of a text prompt describing elements to be included or omitted from the output. Existing images can be re-drawn by the model to incorporate new elements described by a text prompt (a process known as "guided image synthesis") through its diffusion-denoising mechanism. In addition, the model also allows the use of prompts to partially alter existing images via [inpainting](https://en.wikipedia.org/wiki/Inpainting) and outpainting, when used with an appropriate user interface that supports such features, of which numerous different open source implementations exist.

Stable Diffusion is recommended to be run with 10 GB or more VRAM, however users with less VRAM may opt to load the weights in [float16](https://en.wikipedia.org/wiki/Float16) precision instead of the default [float32](https://en.wikipedia.org/wiki/Float32) to tradeoff model performance with lower VRAM usage.

#### Text to image generation

Demonstration of the effect of negative prompts on image generation

<table data-full-width="false"><thead><tr><th align="center">no negative prompt</th><th align="center">"green trees"</th><th align="center">"round stones, round rocks"</th></tr></thead><tbody><tr><td align="center"><img src="../../.gitbook/assets/image (2) (1).png" alt=""></td><td align="center"><img src="../../.gitbook/assets/image (3) (1).png" alt=""></td><td align="center"><img src="../../.gitbook/assets/image (5).png" alt=""></td></tr></tbody></table>

The text to image sampling script within Stable Diffusion, known as "txt2img", consumes a text prompt in addition to assorted option parameters covering sampling types, output image dimensions, and seed values. The script outputs an image file based on the model's interpretation of the prompt. Generated images are tagged with an invisible [digital watermark](https://en.wikipedia.org/wiki/Digital\_watermark) to allow users to identify an image as generated by Stable Diffusion, although this watermark loses its efficacy if the image is resized or rotated.

Each txt2img generation will involve a specific [seed value](https://en.wikipedia.org/wiki/Random\_seed) which affects the output image. Users may opt to randomize the seed in order to explore different generated outputs, or use the same seed to obtain the same image output as a previously generated image. Users are also able to adjust the number of inference steps for the sampler; a higher value takes a longer duration of time, however a smaller value may result in visual defects. Another configurable option, the classifier-free guidance scale value, allows the user to adjust how closely the output image adheres to the prompt. More experimentative use cases may opt for a lower scale value, while use cases aiming for more specific outputs may use a higher value.

Additional text2img features are provided by [front-end](https://en.wikipedia.org/wiki/Frontend\_and\_backend) implementations of Stable Diffusion, which allow users to modify the weight given to specific parts of the text prompt. Emphasis markers allow users to add or reduce emphasis to keywords by enclosing them with brackets. An alternative method of adjusting weight to parts of the prompt are "negative prompts". Negative prompts are a feature included in some front-end implementations, including Stability AI's own DreamStudio cloud service, and allow the user to specify prompts which the model should avoid during image generation. The specified prompts may be undesirable image features that would otherwise be present within image outputs due to the positive prompts provided by the user, or due to how the model was originally trained, with mangled human hands being a common example.

#### Image modification

[<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/NightCitySphere_(SD1.5).jpg/192px-NightCitySphere_(SD1.5).jpg" alt="" data-size="original">](https://en.wikipedia.org/wiki/File:NightCitySphere\_\(SD1.5\).jpg)[![](https://upload.wikimedia.org/wikipedia/commons/thumb/5/56/NightCitySphere\_\(SDXL\).jpg/192px-NightCitySphere\_\(SDXL\).jpg)](https://en.wikipedia.org/wiki/File:NightCitySphere\_\(SDXL\).jpg)

Demonstration of img2img modification

* Left: Original image created with Stable Diffusion 1.5
* Right: Modified image created with Stable Diffusion XL 1.0

Stable Diffusion also includes another sampling script, "img2img", which consumes a text prompt, path to an existing image, and strength value between 0.0 and 1.0. The script outputs a new image based on the original image that also features elements provided within the text prompt. The strength value denotes the amount of noise added to the output image. A higher strength value produces more variation within the image but may produce an image that is not semantically consistent with the prompt provided.

The ability of img2img to add noise to the original image makes it potentially useful for [data anonymization](https://en.wikipedia.org/wiki/Data\_anonymization) and [data augmentation](https://en.wikipedia.org/wiki/Data\_augmentation), in which the visual features of image data are changed and anonymized. The same process may also be useful for image upscaling, in which the resolution of an image is increased, with more detail potentially being added to the image. Additionally, Stable Diffusion has been experimented with as a tool for image compression. Compared to [JPEG](https://en.wikipedia.org/wiki/JPEG) and [WebP](https://en.wikipedia.org/wiki/WebP), the recent methods used for image compression in Stable Diffusion face limitations in preserving small text and faces.

Additional use-cases for image modification via img2img are offered by numerous front-end implementations of the Stable Diffusion model. Inpainting involves selectively modifying a portion of an existing image delineated by a user-provided [layer mask](https://en.wikipedia.org/wiki/Layers\_\(digital\_image\_editing\)#Layer\_mask), which fills the masked space with newly generated content based on the provided prompt. A dedicated model specifically fine-tuned for inpainting use-cases was created by Stability AI alongside the release of Stable Diffusion 2.0. Conversely, outpainting extends an image beyond its original dimensions, filling the previously empty space with content generated based on the provided prompt.

A depth-guided model, named "depth2img", was introduced with the release of Stable Diffusion 2.0 on November 24, 2022; this model infers the [depth](https://en.wikipedia.org/wiki/Depth\_map) of the provided input image, and generates a new output image based on both the text prompt and the depth information, which allows the coherence and depth of the original input image to be maintained in the generated output.

#### ControlNet

ControlNet is a neural network architecture designed to manage diffusion models by incorporating additional conditions. It duplicates the weights of neural network blocks into a "locked" copy and a "trainable" copy. The "trainable" copy learns the desired condition, while the "locked" copy preserves the original model. This approach ensures that training with small datasets of image pairs does not compromise the integrity of production-ready diffusion models. The "zero convolution" is a 1×1 convolution with both weight and bias initialized to zero. Before training, all zero convolutions produce zero output, preventing any distortion caused by ControlNet. No layer is trained from scratch; the process is still fine-tuning, keeping the original model secure. This method enables training on small-scale or even personal devices.

### Releases

Major model releases include:

V1.4, August 2022

V1.5, October 2022

V2.0, November 2022

V2.1, December 2022

SDXL 1.0, July 2023

### Usage and controversy

Stable Diffusion claims no rights on generated images and freely gives users the rights of usage to any generated images from the model provided that the image content is not illegal or harmful to individuals. The freedom provided to users over image usage has caused controversy over the ethics of ownership, as Stable Diffusion and other generative models are trained from copyrighted images without the owner’s consent.

As [visual styles](https://en.wikipedia.org/wiki/Style\_\(visual\_arts\)) and [compositions](https://en.wikipedia.org/wiki/Composition\_\(visual\_arts\)) are not subject to copyright, it is often interpreted that users of Stable Diffusion who generate images of artworks should not be considered to be infringing upon the copyright of visually similar works. However, individuals depicted in generated images may be protected by [personality rights](https://en.wikipedia.org/wiki/Personality\_rights) if their likeness is used, and [intellectual property](https://en.wikipedia.org/wiki/Intellectual\_property) such as recognizable brand logos still remain protected by copyright. Nonetheless, visual artists have expressed concern that widespread usage of image synthesis software such as Stable Diffusion may eventually lead to human artists, along with photographers, models, cinematographers, and actors, gradually losing commercial viability against AI-based competitors.

Stable Diffusion is notably more permissive in the types of content users may generate, such as violent or sexually explicit imagery, in comparison to other commercial products based on generative AI. Addressing the concerns that the model may be used for abusive purposes, CEO of Stability AI, Emad Mostaque, argues that "\[it is] peoples' responsibility as to whether they are ethical, moral, and legal in how they operate this technology", and that putting the capabilities of Stable Diffusion into the hands of the public would result in the technology providing a net benefit, in spite of the potential negative consequences. In addition, Mostaque argues that the intention behind the open availability of Stable Diffusion is to end corporate control and dominance over such technologies, who have previously only developed closed AI systems for image synthesis. This is reflected by the fact that any restrictions Stability AI places on the content that users may generate can easily be bypassed due to the availability of the source code.

### Litigation

In January of 2023, three artists: [Sarah Andersen](https://en.wikipedia.org/wiki/Sarah\_Andersen), Kelly McKernan, and Karla Ortiz filed a [copyright infringement](https://en.wikipedia.org/wiki/Copyright\_infringement) lawsuit against Stability AI, [Midjourney](https://en.wikipedia.org/wiki/Midjourney), and [DeviantArt](https://en.wikipedia.org/wiki/DeviantArt), claiming that these companies have infringed the rights of millions of artists by training AI tools on five billion images scraped from the web without the consent of the original artists. The same month, Stability AI was also sued by [Getty Images](https://en.wikipedia.org/wiki/Getty\_Images) for using its images in the training data.

In July 2023, U.S. District Judge [William Orrick](https://en.wikipedia.org/wiki/William\_Orrick\_III) inclined to dismiss most of the lawsuit filed by Andersen, McKernan, and Ortiz but allowed them to file a new complaint.

### License

Unlike models like [DALL-E](https://en.wikipedia.org/wiki/DALL-E), Stable Diffusion makes its [source code available](https://en.wikipedia.org/wiki/Source-available\_software), along with the model (pretrained weights). It applies the Creative ML OpenRAIL-M license, a form of Responsible AI License (RAIL), to the model (M). The licence prohibits certain use cases, including crime, [libel](https://en.wikipedia.org/wiki/Libel), [harassment](https://en.wikipedia.org/wiki/Harassment), [doxing](https://en.wikipedia.org/wiki/Doxing), "exploiting ... minors", giving medical advice, automatically creating legal obligations, producing legal evidence, and "discriminating against or harming individuals or groups based on ... social behavior or ... personal or personality characteristics ... \[or] [legally protected characteristics or categories](https://en.wikipedia.org/wiki/Anti-discrimination\_law)". The user owns the rights to their generated output images, and is free to use them commercially.
