# Concept

Adversarial Attack
1. Human eye perceive light reflecting from surface and brain processes optical signal to extract feature and build image for interpretation.

2. Similarly, Model learns features from the data and use this features to predict output/interpretation.

3. In certain cases, input image features can be manipulated such a way that these manipulations are not detecteable by human vision but machine groups feature set differently resulting in wrong interpretation

4. Since this manipulations are not detectable by human eyes, AI / vision models in critical applications becomes vulnerable to the attack.

# Approach Taken to Generate Adversarial Imag

Introduce noise to baseImage -> increase loss for given class outcome -> Add noise in base image such way visual appearace do not alter for human perception.

To Generate Adversarial Image:

1. Choose a baseImage -> Run prediction on base image -> Record it.

2. To generate adversary image, Calculate delta (Perturbation vector) to add in baseImage.

    2.1. To calculate Delta
        Generate Delta image -> same dimension as baseImage

    2.2. Run baseImage + Delta from model

    2.3. Calculate loss w.r.t. predicted class id

    2.4. Calculate gradient of the loss w.r.t. delta

    2.5. Update delta and clip values to a fix range

    2.6. Iterate 2.2 to 2.5 for multiple steps

    2.7. return resulting delta

3. Add resultant Delta to baseImage -> Adversarial Image

# Use
1. Open notebook in google colab.
2. Upload image on runtime storage
3. inpute image path and run cells in sequence
