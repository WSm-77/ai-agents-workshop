## What are LLMs?

Large Language Models (LLMs) are AI systems that take text as input and generate a response **token after token**. Fundamentally, they are prediction machines trained on vast amounts of data to guess the most likely next piece of text in a sequence. 

![Tokens][embedding_img]

[See 3brown1blue video here](https://youtu.be/FJtFZwbvkI4?si=PWozD2vAodNjmG4p)


## New paradigm - indeterminism

Development with LLMs is different than before - the LLM based applications are **always undeterministic** - which means that the behavior of the app is not predictable.
This can be both the advantage - the app can be more flexibile and similar to human behavior, but also it can be really problematic as LLM can return the wrong response, even if for the past 100 times it did well. 

<img src="https://ih1.redbubble.net/image.2860257958.8018/flat,750x,075,f-pad,750x1000,f8f8f8.jpg" alt="Indeterminism" width="360">


So, during the development, we try to make it as predictable as possible, but at the same using the agility of the LLMs.

## LLMs are stateless
Which means they don't really learn or remember the conversation context. 

<img src="https://media.tenor.com/uOyVTNTh21sAAAAe/longday-bored.png" width="360">

For the LLM to hold the context, we need to pass whole conversation/text or summarize it:

```bash
curl https://api.openai.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "model": "gpt-4o",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant."
      },
      {
        "role": "user",
        "content": "Hi, my name is Greg."
      },
      {
        "role": "assistant",
        "content": "Hello Greg! How can I help you today?"
      },
      {
        "role": "user",
        "content": "What is my name?"
      }
    ]
  }'
```

## System Prompts

The system prompt is a special message that sets the overall behavior, personality, and constraints for the LLM throughout the conversation. It's like giving the model a role or identity before it starts responding to user queries.

**Key characteristics:**
- Appears as the first message with `"role": "system"` in the conversation
- Defines the assistant's persona, expertise, and behavioral guidelines
- Remains consistent across the entire conversation
- Can include instructions about tone, formatting, and response style

## Good Prompt Practices

Crafting effective prompts isn’t just about what you say — it’s about how you structure it. A well-organized prompt gives the model a clear map of your intent, making it easier for the LLM to understand context, differentiate components, and follow instructions precisely. **It also makes long prompts much easier to maintain and extend for developers.**

Two effective formatting approaches have emerged from industry research and best practices:
### XML-like Tags
```
<instructions>
...
</instructions>

<context>
...
</context>
```

### Markdown-like Structure
```
# Instructions
- ...
- ...

# Context
...
```

Always look for a documentation dedicated to the model you want to use, for ex.:
- [Anthropic's prompt engineering guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-xml-tags)
- [OpenAI's prompt engineering guide](https://platform.openai.com/docs/guides/prompt-engineering)

## Running LLMs Locally with Ollama

Ollama is an open-source tool that makes it easy to run large language models locally on your machine. Instead of relying on cloud APIs, you can download and run models directly on your computer.

**Key benefits:**
- **Privacy**: Your data never leaves your machine
- **Cost**: No API fees - run models **for free**
- **Offline**: Works without internet connection


Learn more at [ollama.com](https://ollama.com).


*all the notebooks you're gonna see today are pre-run
