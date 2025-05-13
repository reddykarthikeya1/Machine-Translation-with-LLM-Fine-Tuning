# German-English Neural Machine Translation

A complete pipeline for fine-tuning a state-of-the-art transformer model for German-to-English translation using the WMT14 dataset and Hugging Face Transformers.

---

## 🚀 Features

- **Pretrained Model**: Fine-tunes [Helsinki-NLP/opus-mt-de-en](https://huggingface.co/Helsinki-NLP/opus-mt-de-en) for high-quality translation.
- **Dataset**: Uses the [WMT14 German-English dataset](https://huggingface.co/datasets/wmt14).
- **Efficient Training**: Supports CUDA, gradient accumulation, and dynamic batch sizing for memory efficiency.
- **Evaluation**: Uses [SacreBLEU](https://github.com/mjpost/sacrebleu) for robust BLEU score computation.
- **Reproducibility**: Sets all random seeds for consistent results.
- **Custom Inference**: Easily test the model on your own German sentences.
- **Model Export**: Saves both model and tokenizer for easy deployment.

---

## 📊 Metrics

- **Final BLEU Score Achieved:** **30.44** (on the validation set)
- **Metric Used:** SacreBLEU
- **Training/Validation Split:** 50,000 train / 3,000 validation (configurable)
- **Best Model Selection:** Automatically loads and saves the checkpoint with the highest BLEU score.

---

## 📈 Example Output

```
German: Das Wetter heute ist schön.
English: The weather is nice today.

German: Ich lerne gerne neue Sprachen.
English: I like learning new languages.
```

---

## ⚡ Important Notes

- **Metrics**: BLEU is the main metric; higher is better. This project achieved a BLEU score of **30.44**.
- **Hardware**: Training is optimized for GPU but will fall back to CPU if unavailable.
- **Customization**: Adjust dataset size, batch size, and epochs in the notebook to fit your resources.
- **Reproducibility**: All seeds are set for consistent results.

---

Happy Translating! 🌍✨
