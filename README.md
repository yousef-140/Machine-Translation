
🧠 Neural Machine Translation (English → German)
This repository contains multiple Neural Machine Translation (NMT) models implemented from scratch using TensorFlow / Keras, progressing from classic Seq2Seq models to a full Transformer architecture.

The project is educational and experimental, focusing on understanding:

Encoder–Decoder architectures

Attention mechanisms

Teacher Forcing

Inference strategies (Greedy & Beam Search)

Evaluation with BLEU score

📌 Models Implemented
1️⃣ Seq2Seq (LSTM Encoder–Decoder) — No Attention
Encoder: LSTM

Decoder: LSTM

Training with Teacher Forcing

Inference using Greedy Decoding

Observations:

Converges slowly

Higher training & validation loss

Weak long-sentence translations

Suffers from information bottleneck

2️⃣ Seq2Seq (LSTM + Attention)
Encoder: LSTM

Decoder: LSTM + Attention

Dot-product attention

Teacher Forcing during training

Observations:

Much faster convergence

Significant drop in loss compared to no-attention model

Better alignment and fluency

Slight overfitting observed due to limited dataset size

3️⃣ Transformer (Encoder–Decoder)
Multi-Head Self Attention

Positional Encoding

No recurrence (fully parallel)

Custom implementation (no keras.layers.Transformer)

Features:

Teacher Forcing during training

Greedy Decoding for inference

Optional Beam Search decoding

Results:

Best qualitative translations

Stable training

Better handling of long sequences

BLEU score reflects dataset size limitations

🧪 Dataset & Preprocessing
Parallel English–German sentence pairs

Text cleaning & normalization

<start> / <end> tokens for decoder

Tokenization using Tokenizer

Padding & batching with tf.data.Dataset

⚙️ Training Details
Loss: Sparse Categorical Crossentropy

Optimizer: Adam

Teacher Forcing enabled

Custom training loops (tf.GradientTape)

Validation at each epoch

🔍 Inference
Greedy decoding

Beam Search (optional)

<start> token used only internally

Output cleaned before display

📊 Evaluation
Metric: BLEU Score

Transformer BLEU ≈ 0.12

Note:
BLEU is highly sensitive to dataset size and reference diversity.
Given the limited training data, the BLEU score is expected and acceptable.
Qualitative evaluation shows coherent and meaningful translations.

📈 Key Takeaways
Attention significantly improves Seq2Seq performance

Transformers outperform RNN-based models in fluency and stability

BLEU alone is not sufficient to judge translation quality

Proper inference strategy (Beam Search, length penalty) matters

🛠 Technologies Used
Python

TensorFlow / Keras

NumPy

Custom Transformer components

Google Colab (training)

🚀 Future Improvements
Larger dataset

BPE / Subword tokenization

Length penalty in Beam Search

Label smoothing

Deeper Transformer architecture

📎 Author Notes
This project was built to deeply understand NMT architectures from the ground up, focusing on implementation details, training flow, debugging, and inference — not just using prebuilt APIs.
