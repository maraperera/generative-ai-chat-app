# Microsoft Foundry Generative AI Exercises

This repo contains two hands-on exercises exploring how to build generative AI applications with the **OpenAI SDK**, the **Responses API**, and a model deployed in **Microsoft Foundry**.

Both exercises use Entra ID authentication, Python 3.13, and the same base setup — the second builds on the first by adding tool use (web search and file search) for grounded, up-to-date answers.

## Exercises

| # | Exercise | Description | README |
|---|---|---|---|
| 1 | **Generative AI Chat App** | Build a chat app from scratch using ChatCompletions → Responses API, add conversation tracking, streaming, and an async client. | [readme genAI.md](./readme%20genAI.md) |
| 2 | **Generative AI App with Tools** | Extend a chat app with `web_search` (live web data) and `file_search` (private vector store over PDF brochures) so responses are grounded in real, current, and proprietary information. | [readme genAI with tools.md](./readme%20genAI%20with%20tools.md) |

## Shared Prerequisites

- An active Azure subscription
- Visual Studio Code
- Python 3.13.x (tested on 3.13.12)
- Git installed and configured
- Azure CLI installed

## Shared Concepts

| Concept | Description |
|---|---|
| **Microsoft Foundry** | Organizes models, resources, and data used to build an AI solution |
| **`gpt-5.1`** | The model deployed and used across both exercises |
| **Entra ID Auth** | `DefaultAzureCredential` + bearer token provider, used instead of API keys |
| **Responses API** | Newer, simpler API (`instructions` + `input`) that supersedes ChatCompletions |
| **`previous_response_id`** | Mechanism for maintaining conversation context across turns |
| **Tools** (`web_search`, `file_search`) | Extend the model beyond its training data with live and private grounding sources |

## Repo Structure

```
.
├── README.md                        # This file — index for both exercises
├── readme genAI.md                  # Exercise 1: core chat app
├── readme genAI with tools.md       # Exercise 2: chat app with tools
├── labfiles/
│   ├── foundry-chat/python/chat-app/    # Exercise 1 code
│   └── tools/python/tools-app/          # Exercise 2 code
└── images/                          # Screenshots referenced by both READMEs
```

## Cleanup

For both exercises, once you're done exploring, delete the Azure resource group used to avoid incurring unnecessary costs:

1. Open the Azure portal → resource group used for the project
2. Select **Delete resource group**
3. Confirm by entering the resource group name

## Reference

Source exercises: [MicrosoftLearning/mslearn-ai-studio](https://github.com/microsoftlearning/mslearn-ai-studio)
