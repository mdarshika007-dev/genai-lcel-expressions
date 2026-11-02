## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

## PROBLEM STATEMENT:
To create an LCEL chain that accepts two inputs and generates meaningful responses using a language model.

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
<img width="1476" height="932" alt="image" src="https://github.com/user-attachments/assets/c94d8a3a-f194-4085-a1d7-ee54a633f3bf" />



### Real-World Applications:

1. AI Chatbots – Generate responses to user queries.
2. Educational Assistants – Suggest learning activities.
3. Content Generation – Create content based on user inputs.
4. Recommendation Systems – Suggest activities based on user interests.

## RESULT:

Thus, the LCEL expression was successfully implemented using two prompt parameters and three key components. The chain generated meaningful responses and demonstrated its applications in real-world scenarios.
