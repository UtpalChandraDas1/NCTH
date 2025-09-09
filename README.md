Augmentation Model, Slight Augmentation of the Images, Affine(scale=(0.95, 1.05),       # small zoom in/out
           translate_percent=(0.02, 0.02),  # small shifts
           rotate=(-10, 10),         # slight rotation only
           shear=(-3, 3),            # very small shear
           p=0.9),
    
    # Machine settings (small changes)
    RandomBrightnessContrast(brightness_limit=0.1, contrast_limit=0.1, p=0.5),
    GaussianBlur(blur_limit=(3, 3), p=0.2),
    GaussNoise(var_limit=(5, 20), p=0.3),
    
    # Subtle probe pressure simulation
    ElasticTransform(alpha=20, sigma=4, alpha_affine=5, p=0.2),
    GridDistortion(num_steps=4, distort_limit=0.02, p=0.2),
    OpticalDistortion(distort_limit=0.02, shift_limit=0.01, p=0.2)
]) 
