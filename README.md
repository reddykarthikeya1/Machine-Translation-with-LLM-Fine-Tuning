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

- **BLEU Score**: The primary metric for translation quality. Computed using SacreBLEU on the validation set.
- **Training/Validation Split**: Customizable to fit your hardware (default: 50,000 train / 3,000 validation).
- **Best Model Selection**: Automatically loads and saves the checkpoint with the highest BLEU score.

---

## 🛠️ Usage

### 1. Environment Setup

```sh
python -m venv llm_env
# Activate your environment and install dependencies:
pip install torch transformers datasets evaluate sacrebleu
```

### 2. Training

Open and run all cells in [`translate.ipynb`](translate.ipynb) to:

- Load and preprocess the dataset
- Fine-tune the model
- Evaluate and save the best checkpoint

### 3. Inference

After training, test the model with your own sentences:

```python
def translate(text):
    # ...see notebook for details...
    return translation

print(translate("Das Wetter heute ist schön."))
```

### 4. Model Export

The fine-tuned model and tokenizer are saved to [`fine-tuned-opus-mt-de-en/`](fine-tuned-opus-mt-de-en/).

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

- **Metrics**: BLEU is the main metric; higher is better.
- **Hardware**: Training is optimized for GPU but will fall back to CPU if unavailable.
- **Customization**: Adjust dataset size, batch size, and epochs in the notebook to fit your resources.
- **Reproducibility**: All seeds are set for consistent results.

---

## 📂 Project Structure

```
translate.ipynb
fine-tuned-opus-mt-de-en/
    config.json
    model.safetensors
    ...
llm_env/
results/
```

---

## 📚 References

- [Hugging Face Transformers](https://huggingface.co/transformers/)
- [SacreBLEU](https://github.com/mjpost/sacrebleu)
- [WMT14 Dataset](https://huggingface.co/datasets/wmt14)

---

Happy Translating! 🌍✨
