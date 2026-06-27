## LangChain Working with Models & Prompts

We will use VS CODE for our practice.

1. ==Create an virtual environment==
	```cmd
	python -m venv .venv
	```
					or
```cmd 
conda create -p venv python==3.13
```

activate virtual environment
```cmd
conda activate venv/
```


2. ==Install the libraries== 

> [!Create an requirements.txt in the same folder]
>       requirements.txt

```txt
#Langchain cores 
langchain
lamgchain-core

#Openai integration 
langchain-openai
openai

#Antropic Integration 
langchain-anthropic

#Google Gemini (Palm) Intergration 
langchain-google-genai
google-generativeai

#hugging face integration 
langchain-huggingface
transformers
huggingface-hub

#enviroment variable management 
python-dotenv

#Machine learning utilities 

numpy 
scikit-learn 
seaborn 
pandas 
Torch
TensorFlow
Flax

```

```cmd 
pip install -r requiements.txt
```

3. ==Code==
	```python 
	from langchain_openai import OpenAI
	from dotenv import load_dotenv
	
	load_dotenv()
	
	llm = OpenAI(model='gpt-3.5-turbo-instruct')
	
	result = llm.invoke("What is the capital of pakistan")
	
	print(result)
	```


3. ==Generate an Key from OpenAi==
	 use that api key and save that on ( .env ) file. 