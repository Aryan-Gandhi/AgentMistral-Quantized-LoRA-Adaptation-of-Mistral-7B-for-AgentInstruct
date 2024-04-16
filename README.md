# QuaLORAgentMistral-Quantized-LoRA-Adaptation-of-Mistral-7B-for-AgentInstruct
# Mistral-7B AgentTuner

This project demonstrates efficient finetuning of the Mistral-7B language model on the AgentInstruct dataset for instruction-following tasks using Low-Rank Adaptation (LoRA) and quantization techniques.

## Dataset

The project uses the THUDM/AgentInstruct dataset, which consists of multiple splits containing conversations between humans and GPT-based agents. The dataset is analyzed to understand the distribution of conversation turns, response lengths, and commonly used words.

## Model

The Mistral-7B model is chosen for its strong general-purpose capabilities and competitive performance on both language and coding tasks. The model is loaded with 4-bit quantization using the bitsandbytes library for memory efficiency.

## Preprocessing

The dataset is transformed to surround instructions with [INST] tokens and split into train and test sets. The maximum token length is determined based on the distribution of token counts in the dataset.

## Training

The model is finetuned using the SupervisedFinetuning (SFT) Trainer from the trl library. Gradient checkpointing is enabled, and the model is prepared for LoRA training. LoRA hyperparameters like rank (r) and alpha are configured, and training arguments like number of epochs, batch size, and learning rate are set.

## Evaluation

The trained model is tested on sample prompts, and its perplexity is compared to the base model. The model artifacts and logs are saved and moved to Google Drive for persistence.

## Results

The trained model shows improved performance on test prompts compared to the base model, demonstrating the effectiveness of the LoRA finetuning and quantization techniques.

## Usage

To use this project, follow these steps:

1. Clone the repository
2. Install the required dependencies
3. Run the provided code in a Google Colab notebook or a similar environment
4. Adjust the hyperparameters and training arguments as needed
5. Train the model and evaluate its performance on test prompts

## Acknowledgements

This project makes use of the following libraries and datasets:

- Transformers
- Datasets
- PyTorch
- BitsnBytes
- TRL
- THUDM/AgentInstruct Dataset

