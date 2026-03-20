# Recyclable Material Classification using Convolutional Neural Networks (CNNs)

## Project Overview

This project focuses on developing an image classification system capable of identifying different types of recyclable materials using Convolutional Neural Networks (CNNs). The goal is to simulate a real-world automated waste sorting system that can classify materials accurately and efficiently, reducing reliance on manual labour and improving recycling outcomes.

A dataset of 2,691 labelled images across six recyclable categories was used to train and evaluate multiple deep learning models. Rather than relying on a single model, this project follows a structured experimentation approach, where **10 different CNN architectures** were designed, trained, and compared to determine the most effective model.

The final selected model (M6) achieved strong classification performance, demonstrating the practical feasibility of deep learning-based solutions in sustainability-focused applications such as waste management and recycling automation.


## Business Context and Problem

Recycling facilities often depend on manual sorting processes, which are time-consuming, inconsistent, and prone to error. Incorrect classification of materials leads to contamination in recycling streams, reducing overall efficiency and increasing operational costs.

This project addresses that challenge by building a computer vision system that can automatically classify recyclable materials from images. Such a system can be integrated into conveyor-based sorting environments, enabling faster processing, reduced human intervention, and improved sustainability outcomes.

By translating image data into actionable insights, this solution supports organisations in improving both operational efficiency and environmental impact.


## Dataset and Preprocessing

The dataset consists of 2,691 real-world images representing six recyclable material categories:

- cardboard  
- clothes  
- green-glass  
- metal  
- paper  
- white-glass  

All images were resized to a standard dimension of **50 × 50 pixels with 3 colour channels (RGB)** to ensure consistency across model inputs.

To prepare the data for modelling, several preprocessing steps were applied. These included normalising pixel values to improve model convergence, converting labels into one-hot encoded format for multi-class classification, and splitting the dataset into training and testing subsets using a **70/30 ratio**.

The dataset was relatively balanced across categories, which helped ensure fair model training without significant bias toward any single class.


## Modelling Approach

Instead of relying on a single model, this project adopts an experimental approach where **10 different CNN architectures** were systematically developed and evaluated. Each model was designed to test the impact of architectural variations such as:

- increasing convolutional depth  
- adjusting filter sizes and kernel configurations  
- modifying dense layer sizes  
- introducing dropout regularisation  
- removing or simplifying network components  

This structured experimentation allowed for a deeper understanding of how architectural choices influence classification performance.

All models were trained using TensorFlow/Keras in Google Colab, with consistent training conditions to ensure fair comparison. Early stopping was applied to prevent overfitting and improve generalisation.


## Final Model and Performance

After evaluating all 10 models, **Model M6** was selected as the best-performing architecture.

This model consists of three convolutional layers followed by pooling layers, a dropout layer for regularisation, and dense layers for classification. The architecture strikes a balance between complexity and generalisation, allowing it to capture important image features without overfitting.

The final model achieved:

- **Test Accuracy:** 79.2%  
- **Cohen’s Kappa:** 0.75  
- **Test Loss:** 0.58  

These results indicate strong predictive performance and a high level of agreement beyond chance, making the model suitable for practical classification tasks.


## Model Behaviour and Insights

An in-depth evaluation of the model revealed important patterns in classification performance across different material types.

Certain categories, such as **green-glass**, were classified with very high accuracy due to their distinct visual characteristics. On the other hand, categories like **metal** and **white-glass** proved more challenging, as they often share similar textures, reflections, and colour patterns.

This highlights a key real-world insight: classification difficulty is not only dependent on model architecture but also on how visually distinguishable the categories are.

The confusion matrix further supports this observation by showing where misclassifications occur, particularly between visually similar classes.


## Key Visualisations

### Sample Images from Dataset
This visual provides an overview of the different recyclable material categories and helps understand the classification problem from a human perspective.

<img width="690" height="663" alt="image" src="https://github.com/user-attachments/assets/adad5087-bea8-404e-853e-a6405f47e70d" />


### Training Class Distribution
This chart confirms that the dataset is reasonably balanced across categories, which supports fair model training and reduces bias.

<img width="790" height="390" alt="image" src="https://github.com/user-attachments/assets/fd608e47-679e-4794-b7c8-31fbd631525b" />


### Training and Validation Performance
This visual shows how the final model learned over time, including both accuracy and loss trends. It helps evaluate whether the model converged effectively and whether overfitting was controlled.

<img width="498" height="332" alt="Screenshot 2026-03-20 at 12 46 31 pm" src="https://github.com/user-attachments/assets/deab9f78-b8b3-4aaa-be25-852520c99e15" />


### Confusion Matrix (Final Model)
The confusion matrix highlights how well the model performed across different classes and where classification errors occurred. It is particularly useful for identifying difficult categories.

<img width="863" height="811" alt="image" src="https://github.com/user-attachments/assets/95876699-edab-43ac-834a-272c4ce88434" />


### Model Comparison Summary
This visual summarises the performance of all 10 CNN models tested, showing why Model M6 was selected as the final architecture.

<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/3246194b-370b-4a2f-866b-53368bd95968" />


## Business Value and Applications

The results of this project demonstrate that CNN-based image classification can be effectively applied to real-world recycling challenges.

Such a system could be deployed in waste management facilities to automate sorting processes, reduce labour costs, and improve classification accuracy. By minimising contamination in recycling streams, organisations can increase recovery rates and improve sustainability performance.

Additionally, this solution provides a foundation for further advancements, such as real-time classification systems integrated with conveyor belts and robotic sorting mechanisms.


## Limitations and Future Improvements

While the model performs well overall, there are opportunities for improvement.

The dataset size is relatively limited, which may restrict the model’s ability to generalise to more diverse real-world scenarios. Increasing the dataset size and applying data augmentation techniques could improve robustness.

More advanced architectures such as transfer learning models (e.g., ResNet, MobileNet) could also be explored to enhance performance further.

Finally, improving classification accuracy for visually similar materials such as metal and glass would be critical for real-world deployment.


## Technologies Used

This project was developed using:

- Python  
- TensorFlow / Keras  
- NumPy  
- OpenCV  
- Matplotlib  
- Scikit-learn  
- Google Colab  
