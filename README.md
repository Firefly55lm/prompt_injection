# PROMPT INJECTION TECHNIQUES

The purpose of this repository is to explore an important and malevolent technique related to Large Language Models: Prompt Injection.
In the notebook, we studied the output and vulnerabilities of several models concerning this technique, specifically focusing on:
- Mistral 7B
- Llama 2 13B
- Llama 3 8B
- Falcon 7B
- Phi 3 128k
- GPT-4o (used on ChatGPT)

Prompt Injection can be applied in different ways, as we examined, including direct prompting, virtualization, and obfuscation/token smuggling. We observed that some models are more vulnerable to Prompt Injection than others, especially in some techniques like virtualization, and some of them are more robust than others, like GPT-4o, the most valuable model nowadays. The aim of this study is to highlight some weaknesses of these models to enhance the output quality and security for end users.

**TESTED TECHNIQUES**
- **Direct Prompting**: consists of asking to the model a simple question and then adding a new request, which specifies to ignore the previous input and fullfill a new request instead;
- **Obfuscation / Token smuggling**: consists of splitting the input into multiple requests, and then getting the LLM to combine and execute them. The initial requests are provided in such a way the model will provide a potentially malicious answer without triggering the filters;
- **Virtualization**: involves the creation of a scenario in which the model has to impersonate an individual in order to bypass the filters;

The techniques' description and the prompt ideas has been taken from [this](https://medium.com/@austin-stubbs/llm-security-types-of-prompt-injection-d7ad8d7d75a3) Medium article by Austin Stubbs.

In conclusion, We may say that:
    
Falcon: vulnerable to , robust to
Llama 2: vulnerable to , robust to 
Llama 3: vulnerable to , robust to
Phi 3: vulnerable to , robust to
Mistral: vulnerable to , robust to
GPT-4o: vulnerable to , robust to

Credits:
-1
-2
-3
-4
-5
