# Intent Classification with BERT

This project demonstrates an intent classification task using GAN-BERT with a focus on preprocessing, training, and evaluating a deep learning model for natural language processing (NLP). 

## Course Information
- **Course Topic**: Intent Classification - GAN BERT
- **Course Work by**: @Bagiya
- **Start Date**: June 14
- **Reference**: 
  [Intent Classification with BERT - Hannibunny](https://hannibunny.github.io/mlbook/transformer/intent_classification_with_bert.html)

## Dataset
The dataset used is sourced from the CLINC OOS dataset. The dataset includes:
- **Training Samples**: 15,000
- **Validation Samples**: 3,000
- **Test Samples**: 4,500

### Example Dataset Workflow
1. **Data Loading**: 
   - Fetched via a public URL.
   - Converted into Pandas DataFrames for processing.

2. **Label Encoding**:
   - Labels were binarized using `LabelBinarizer` from Scikit-learn.

3. **Train/Validation/Test Splits**:
   - Proper splits were ensured to avoid data leakage.

## Model Details
1. **BERT Model**:
   - Using the Small BERT variant: `small_bert/bert_en_uncased_L-8_H-512_A-8`.
   - TensorFlow Hub was used to load pre-trained models and preprocessors.

2. **Classifier Model**:
   - Input: Text-based input layer.
   - Layers: BERT Preprocessing → BERT Encoder → Dropout → Dense Layer (output).
   - Output: Multi-class intent classification across 150 intents.

3. **Training Configuration**:
   - Optimizer: Adam (`learning_rate=1e-5`).
   - Loss Function: Categorical Crossentropy with logits.
   - Metrics: Categorical Accuracy.
   - Epochs: 5
   - Batch Size: 32.

## Evaluation
- **Training Accuracy**: 95.29%
- **Validation Accuracy**: 93.27%
- **Test Accuracy**: 92.64%
- Loss and Accuracy curves plotted over epochs for insights.

## Inference Examples
The model accurately classifies examples like:
- **Input**: "play a song from U2" → **Intent**: `play_music`
- **Input**: "Will it rain tomorrow" → **Intent**: `weather`
- **Input**: "I like to book a table for 3 persons" → **Intent**: `restaurant_reservation`

## How to Use
1. Install required dependencies: TensorFlow, TensorFlow Hub, Pandas, NumPy, and Matplotlib.
2. Load the dataset and preprocess as shown in the script.
3. Train the model using the provided architecture.
4. Use the trained model for inference on custom text inputs.

## Visualization
- Training and validation loss and accuracy are plotted to understand performance trends over epochs.

## References
- [CLINC OOS Dataset Repository](https://github.com/clinc/oos-eval)
- [TensorFlow Hub - BERT Models](https://tfhub.dev/)

---
Enjoy exploring intent classification with BERT!
