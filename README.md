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


# Acknowledgments
The LLMA2 model and its components, QLoRA and Peft, were developed by NousResearch. Please refer to the official documentation for more details.

# problem we faced & solution
1) run this model on t4 gpu on colab for faster & smoother running
keep describe version which want to use bocz

2)if u install like this !pip install torch it install
but when u run training arguments they show you you not install torch / accelerate
thats why you mention version of that in my case i use torch==1.10.0 like this not this !pip install torch




   



