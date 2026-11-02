## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

## Problem Statement:
The aim of this program is to design and implement LangChain Expression Language (LCEL) using Python. It integrates a prompt template, OpenAI GPT-4o-mini language model, and output parser to generate responses based on user input. The program uses ChatPromptTemplate to create structured prompts and StrOutputParser to convert the AI response into plain text. It connects all the components using the LCEL pipe operator (|) and executes the chain using the invoke() method. The main objective is to generate simple, clear, and meaningful explanations for a given topic and display the final output to the user.


## DESIGN STEPS:

### STEP 1:
Import the required libraries and load the API key.

### STEP 2:
Create a prompt with two parameters and initialize the model and output parser.

### STEP 3:
Connect the components using the LCEL pipe operator (`|`) and execute the chain.

## PROGRAM:

```
import os
import openai

from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv()) # read local .env file
openai.api_key = os.environ['OPENAI_API_KEY']
from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser

model = ChatOpenAI(model="gpt-4o-mini", temperature=0)

prompt = ChatPromptTemplate.from_template(
    "Explain {topic} in simple words."
)

output_parser = StrOutputParser()

chain = prompt | model | output_parser

result = chain.invoke({"topic": "Artificial Intelligence"})

print(result)
print("Name:M.DARSHIKIA")
print("REG NO:212225220020")

```

## OUTPUT:
<img width="1717" height="917" alt="image" src="https://github.com/user-attachments/assets/51465ee1-a804-453f-9958-0e2298e9e3b4" />




### Real-World Applications:

1. AI Chatbots – Generate responses to user queries.
2. Educational Assistants – Suggest learning activities.
3. Content Generation – Create content based on user inputs.
4. Recommendation Systems – Suggest activities based on user interests.

## RESULT:

Thus, the LCEL expression was successfully implemented using two prompt parameters and three key components. The chain generated meaningful responses and demonstrated its applications in real-world scenarios.
