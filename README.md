# RAG-Healthcare

This project was developed as part of the Independent Learning Module at FHNW.

## Overview

The project is run locally. To install all the required dependencies, run the following command:

```bash
pip install -r requirements.txt
```

It will install all the necessary packages.

The project is divided into two main parts:

1. **SHAP Values Setup**  
   This includes configuring and interpreting SHAP values, which help explain the predictions made by a machine learning model.

2. **LLM Queries**  
   This demonstrates how to effectively use a Large Language Model (LLM) to derive insights from the SHAP analysis output. It includes examples of both poor and effective ways of querying an LLM.

## Groq Integration

We use [Groq](https://console.groq.com/keys) to access the LLM. Groq offers over 1000 calls per day, which should be sufficient for teaching purposes. Each student can create an account quickly and obtain an API key. This key is then used in the \`.env\` file.

It is also possible to use Groq on Deepnote, and the steps are largely the same, with minimal code changes.

### Groq API Key for Deepnote Integration

1. **Create an account on Groq**  
   Sign up here: [Groq Console](https://console.groq.com/keys)

2. **Create an API Key**  
   Once you are logged in, generate your personal API key.

3. **Create an Environment Variable**  
   In your Deepnote project, create an environment variable as described here: [Deepnote Docs](https://deepnote.com/docs/environment-variables).

   - Name the variable **Groq_API**.
   - In the **Key** field, enter \`GROQ_API_KEY\`.
   - In the **Value** field, paste the secret key you obtained from Groq.

4. **Update the Groq Client**  
   In your code, make the following change to use the environment variable directly:

```python
groq_client = Groq(
api_key="GROQ_API_KEY" # Instead of api_key=os.getenv("GROQ_API_KEY")
)
```

## Teaching Cases

We showcase different types of prompts to illustrate how to obtain meaningful results from an LLM:

1. **Minimal Prompt (Prediction Only)**  
   A simple query that returns the prediction values without additional information.

2. **Minimal Prompt (Prediction + SHAP Values)**  
   A slightly more detailed query that provides both the prediction values and the corresponding SHAP values.

3. **Structured Prompt (Instructions, Dataset Values, and SHAP Values)**  
   A more complex query that includes specific instructions, relevant dataset values, and the SHAP values of the prediction, demonstrating how to obtain more comprehensive and actionable responses.
