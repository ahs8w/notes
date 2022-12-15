# Stable Diffusion

1. UNET - noise predictor 
input noisy image[latent] and predicts the noise 
    - subtract output from input => image[latent] 
        - result is closer to the distribution which the model was trained on
        - continue for many steps (~50) to improve the resulting image[latent]
    - images require too much compute better to operate in latent space
    - how are text embeddings incorporated?
        - adding attention layers between the ResNet blocks

2. VAE - compression algorithm
    - encoder - compresses image into latent space
    - decoder - convert latent space back into pixel space
  
3. CLIP model - text encoder  
transforms text inputs into the same latent space as images  
    - trained on 400M images and captions (alt text)
    - combination of image encoder and text encoder
    - compare resulting embeddings with cosine similarity
    - Contrastive Loss to increase similarity of images with appropriate captions


4. Diffusion Model  
NN (UNET) learns to gradually denoise data
    - Diffusion Sampler/Scheduler determines how much noise to add/remove in training/inference



Text Encoder (CLIP) -> Diffusion Model (UNET + Scheduler) -> Image Decoder (VAE decoder)