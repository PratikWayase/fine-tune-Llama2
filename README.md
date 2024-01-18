# fine-tune-llma2-

 fine-tuning the NousResearch/llama-2-7b-chat-hf model on a custom dataset using QLoRA (Quantization in Language Representation) 
 Peft (Position Embedding Fourier Transform) techniques.
 (Supervised Fine-tuning) approach is employed for training.

# Requirements
Python 3.9
PyTorch
Hugging Face Transformers
Datasets
Peft
Trl

# Setup

Install Dependencies:
pip install -r requirements.txt

Download LLMA2 Pre-trained Model:
Obtain the LLMA2 pre-trained model ("NousResearch/llama-2-7b-chat-hf") from the Hugging Face model hub.

Download Custom Dataset:
Use the datasets library to load your custom dataset. In this example, the dataset used is "databricks/databricks-dolly-15k".
note that if datasize is large it take lot of time.in my case databricks-dolly-15k is 15 mb and it take lot of time to train 
so its best to choose small datasize if you want to get handson experience on fine tuning large language models.

Configure Parameters:
Adjust the parameters in the script according to your specific requirements. Parameters include QLoRA settings, bitsandbytes configuration, training arguments, and SFT parameters.

# Usage
Once fine-tuning is complete, you can use the newly trained model for various natural language processing tasks. The fine-tuned model is saved with the name "llama-2-7b-databricks-dolly".

# inference

# Run text generation pipeline with our next model
prompt = "What is a price action in forex market?"
pipe = pipeline(task="text-generation", model=model, tokenizer=tokenizer, max_length=200)
result = pipe(f"<s>[INST] {prompt} [/INST]")
print(result[0]['generated_text'])

# Acknowledgments
The LLMA2 model and its components, QLoRA and Peft, were developed by NousResearch. Please refer to the official documentation for more details.

# problem we faced & solution
1) run this model on t4 gpu on colab for faster & smoother running
keep describe version which want to use bocz

2)if u install like this !pip install torch it install
but when u run training arguments they show you you not install torch / accelerate
thats why you mention version of that in my case i use torch==1.10.0 like this not this !pip install torch

3) model_name = "NousResearch/llama-2-7b-chat-hf"
  dataset_name = "databricks/databricks-dolly-15k"
  new_model = "llama-2-7b-databricks-dolly"

so here u confuse what is new model ?
new model means any name you want to give your finetuned model. later it will help you in inference.


   



