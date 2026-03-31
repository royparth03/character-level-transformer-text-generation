# Lightweight GPT Text Generator

## Overview

This project implements a lightweight transformer-based language model (similar to GPT) trained on Shakespeare text. The model generates human-like text using self-attention mechanisms.

## Features

- Transformer architecture implemented from scratch
- Character-level language modeling
- Text generation capability
- Lightweight model suitable for local execution

## Project Structure

- bigram.py: Model implementation and training
- input.txt: Training dataset (Shakespeare text)
- output.txt: Generated text samples
- requirements.txt: Dependencies

## Data Pipeline

Raw Text → Character Encoding → Tensor Conversion → Train/Validation Split → Batch Sampling → Input-Target Pair Creation → Model Training

### Explanation

1. **Raw Text**  
   Shakespeare text is loaded from `input.txt`.

2. **Character Encoding**  
   Each character is mapped to a unique integer using a lookup table (stoi).

3. **Tensor Conversion**  
   Encoded data is converted into PyTorch tensors for computation.

4. **Train/Validation Split**  
   Data is split into training (90%) and validation (10%) sets.

5. **Batch Sampling**  
   Random fixed-length sequences are sampled to create training batches.

6. **Input-Target Pair Creation**  
   The model learns by predicting the next character in a sequence:

x = "Hell"
y = "ello"

7. **Model Training**  
   Batches are fed into the transformer model to minimize prediction loss.

## How to Run

1. Install dependencies:

pip install -r requirements.txt

2. Run the model:

python bigram.py

## Results

- Final Training Loss: ~1.67
- Validation Loss: ~1.82

## Sample Output

Oor Gley I must ther,--all hao thusI shall kinkep weate have have mine...

## Limitations

- Character-level model (limited coherence)
- Small dataset
- Lightweight architecture

## Future Improvements

- Word-level modeling
- Larger transformer
- Better training optimization
