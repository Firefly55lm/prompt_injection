# PROMPT INJECTION TECHNIQUES

The purpose of this repository is to explore an important and malevolent technique related to Large Language Models: Prompt Injection. According with [csoonline.com](https://www.csoonline.com/article/1294996/top-4-llm-threats-to-the-enterprise.html), the malicious instruction from prompt injection is one of the most severe threats related with the usage of Large Language Models. 
The test notebook is available in the main branch of the repository and at [this Colab link](https://colab.research.google.com/drive/1c5Xal5Kkh2bRqXC0khgPqh9moF7Atx4P?usp=sharing).

In the notebook, we studied the output and vulnerabilities of several models concerning this technique, specifically focusing on:
- Mistral 7B
- Llama 2 13B
- Llama 3 8B
- Falcon 7B
- Phi 3 128k
- GPT-4o (used on ChatGPT)

Prompt Injection can be applied in different ways, as we examined, including direct prompting, virtualization, and obfuscation/token smuggling. We observed that some models are more vulnerable to Prompt Injection than others, especially in some techniques like virtualization, and some of them are more robust than others, like GPT-4o, the most valuable model nowadays. The aim of this study is to highlight some weaknesses of these models to enhance the output quality and security for end users.

### **TESTED TECHNIQUES**
- **Direct Prompting**: consists of asking to the model a simple question and then adding a new request, which specifies to ignore the previous input and fulfill a new request instead;
- **Obfuscation / Token smuggling**: consists of splitting the input into multiple requests, and then getting the LLM to combine and execute them. The initial requests are provided in such a way the model will return a potentially malicious answer without triggering the filters;
- **Virtualization**: involves the creation of a scenario in which the model has to impersonate an individual in order to bypass the filters;

For every technique, both simple questions and illegal and offensive requests have been tested, in order to evaluate the strength of the filters and check how easy is to bypass them.

The techniques' description and the prompt ideas have been taken from [this](https://medium.com/@austin-stubbs/llm-security-types-of-prompt-injection-d7ad8d7d75a3) Medium article by Austin Stubbs.


### **RESULTS**
Here is a synthesis of the key results obtained:
    
- **Llama 2:** vulnerable to *direct prompting*, but doesn't fullfill requests about forbidden subjects (such as the information to make a bomb) for both basic and tagged prompts; only tested on direct prompting.
- **Llama 3:** vulnerable to *direct prompting*, returning the same behaviour as its previous version Llama 2; robust to *obfuscation* when the request is clearly illegal but generating strongly offensive answers for the second prompt; vulnerable to virtualization also.
- **Phi 3:** vulnerable to *direct prompting*, with a unexpected behaviour of disgressing and rambling; vulnerable to both *obfuscation* and *virtualization*.
- **Falcon:** not very vulnerable to *direct prompting*, but very strong rambling issues and generation often not related to the request; only tested on direct prompting.
- **Mistral:** vulnerable to every technique, provides illegal answers even with simple requests due to the [lack of filters](https://medium.com/@InnovateForge/controversy-surrounding-mistral-ais-release-066831633655).
- **GPT-4o:** vulnerable to every prompt injection technique, but the strong filters always block illegal and offensive results.

In conclusion, We may say that:
- Direct prompting usually works for allowed requests, but can be dangerous for applications where the model interacts with a user. The latter can trick the model into providing apparently legitimate answers, such as creating SQL queries, which can bring to malfuctions and cybersecurity threats;
- Obfuscation is complicated to apply but it can trick the model into providing malicious or offensive answers;
- Virtualization is the strongest technique, tricking every tested model into providing an answer that can be used to pursue illegal activities, such as phishing and other scam techniques.






