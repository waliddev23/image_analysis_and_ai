# SAM2 Model Finetuning: Hands-On Experience  

This repository provides a hands-on exploration of the **Segment Anything Model 2 (SAM2)** developed by Meta, focusing on preparing data for fine-tuning and implementing a robust training pipeline. The project is divided into two main parts:

---

## Part 1: Data Preparation  

The first step involves preparing the dataset for fine-tuning. This part of the implementation is highly inspired by a FreeCodeCamp tutorial on the SAM2 model. It covers:  

1. **Downloading Data**:  
   - The dataset is sourced from **Roboflow**, with annotations provided in the COCO format.  

2. **Processing Annotations**:  
   - The COCO annotations, specifically mask information, are converted into individual JPG mask files stored in a separate folder.  
   - A **dataframe** is created that links each image to its corresponding mask, serving as a structured reference for the model during fine-tuning.

3. **Output**:  
   - Cleaned and organized image-mask pairs ready for the fine-tuning pipeline.

> **Note**: All data preparation is implemented in the first notebook (`data_preparation.ipynb`), which ensures seamless data conversion and preparation for the training phase.

---

## Part 2: Model Fine-Tuning  

The second notebook, `train.ipynb`, focuses on fine-tuning the SAM2 model over 3000 steps. This includes:  

1. **Model Initialization**:  
   - The **Segment Anything Model 2** (SAM2) is loaded, with the vision and prompt encoders frozen to fine-tune only the mask decoder.  

2. **Training**:  
   - A systematic training pipeline with data loaders, loss functions, and optimization is implemented.  
   - Bounding box prompts derived from the prepared dataset are used as the primary input during fine-tuning.  

3. **Performance Metrics**:  
   - The Intersection over Union (IoU) metric is tracked to evaluate model performance.  
   - The maximum IoU score achieved is **0.71**, demonstrating a promising improvement in segmentation capability.  

4. **Challenges**:  
   - Despite its overall performance, the model occasionally struggles to accurately identify objects.  
   - However, given that the fine-tuning is based on a **single point prompt**, the results are still commendable.

---

## Results  

- **IoU Metric**: Achieved a maximum value of **0.71** during fine-tuning.  
- **Strengths**: The model performs well on specific object detection tasks, especially when using bounding box prompts , and it was able to detect objects that where not even masked in the input dataset .  
- **Limitations**:  from  Some challenges remain in precisely identifying objects, highlighting areas for further fine-tuning or dataset augmentation.  


