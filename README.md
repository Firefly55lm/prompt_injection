# prompt_injection

The purpose of this repository is to explore an important and malevolent technique related to Large Language Models: Prompt Injection. In the notebook, we studied the output and vulnerabilities of several models concerning this technique, specifically focusing on Mistral 7B, Llama 2 13B, Llama 3 8B, Falcon 7B, Phi 3 128k, and GPT-4o used on ChatGPT.

Prompt Injection can be applied in different ways, as we examined, including direct prompting, virtualization, and obfuscation/token smuggling. We observed that some models are more vulnerable to Prompt Injection than others, especially in some techniques like virtualization, and some of them are more robust than others, like GPT-4o, the most valuable model nowadays.

The aim of this study is to highlight some weaknesses of these models to enhance the output quality and security for end users.
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