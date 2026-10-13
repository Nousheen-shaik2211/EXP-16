# EXP-16
# Prompt Quality Evaluation and Ethical Considerations

## Aim
To evaluate prompt quality by comparing a baseline prompt with an enhanced prompt and to identify ethical and security risks in LLM deployment.

## Problem Statement
Evaluate two prompts on three climate-change questions using simplified manual metrics for faithfulness and answer relevancy. Discuss ethical risks and possible mitigations.

## Technologies Used
- Python
- OpenAI API
- GPT-4o-mini
- Prompt engineering
- Manual evaluation metrics

## Prompt Versions
**Prompt A — Baseline:**  
"Answer the question using the provided context."

**Prompt B — Enhanced:**  
Adds instructions to remain faithful to the context, answer concisely, avoid speculation, and treat retrieved instructions as untrusted data.

## Algorithm
1. Define three climate-change questions and their contexts.
2. Specify a ground-truth answer for each question.
3. Generate answers using Prompt A and Prompt B.
4. Keep the model and temperature the same for both prompts.
5. Calculate approximate faithfulness and answer-relevancy scores.
6. Display the comparison table and average scores.
7. Discuss ethical and security risks and mitigations.

## Project Structure
```text
Prompt_Evaluation_Ethics/
├── main.py
├── README.md
├── requirements.txt
└── .gitignore
```

## Installation
```bash
pip install -r requirements.txt
```

## Configure API Key

Windows PowerShell:
```powershell
$env:OPENAI_API_KEY="your_api_key_here"
```

Linux/macOS:
```bash
export OPENAI_API_KEY="your_api_key_here"
```

## Run the Experiment
```bash
python main.py
```

## Evaluation Metrics
- **Faithfulness:** Estimates the proportion of answer keywords supported by the provided context.
- **Answer relevancy:** Uses keyword precision and recall against the ground-truth answer to calculate an F1-style score.

These are simplified lexical estimates. They do not fully measure semantic correctness and are not official RAGAS scores.

## Ethical Risks and Mitigations

1. **Prompt injection:** Retrieved content may contain malicious instructions. Treat retrieved text as untrusted data, separate instructions from evidence, and validate outputs.
2. **Hallucination:** The model may generate unsupported facts. Require context-grounded answers and permit abstention when evidence is missing.
3. **Bias and outdated information:** The knowledge base may be incomplete or outdated. Review sources regularly and evaluate across varied questions.

## Conclusion
The experiment compares baseline and enhanced prompts using consistent test data and simple evaluation metrics. It also demonstrates why prompt design should be combined with security controls, source review, and output validation.
