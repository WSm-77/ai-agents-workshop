# Glossary

A comprehensive guide to technical terms and concepts used in this workshop. Terms are organized alphabetically within categories for easy reference.

---

## Table of Contents
- [Networking & Web](#networking--web)
- [AI & Machine Learning](#ai--machine-learning)
- [Programming Concepts](#programming-concepts)
- [Data Formats](#data-formats)
- [Development Tools](#development-tools)

---

## Networking & Web

### API (Application Programming Interface)
A set of rules and protocols that allows different software applications to communicate with each other. Think of it as a waiter in a restaurant: you (the client) tell the waiter (API) what you want, and the waiter brings your request to the kitchen (server) and returns with your food (data).

**Example**: When you use a weather app on your phone, it uses an API to request weather data from a weather service.

### HTTP (HyperText Transfer Protocol)
The foundation of data communication on the web. It's a protocol that defines how messages are formatted and transmitted between web browsers and servers.

**Key concepts**:
- **Request**: When you ask for something (e.g., loading a webpage)
- **Response**: What the server sends back (e.g., the webpage content)
- **Status Codes**: Numbers that indicate what happened (e.g., 200 = success, 404 = not found)

### HTTP Methods
Different types of requests you can make:
- **GET**: Retrieve data (like viewing a webpage)
- **POST**: Send data to create something new (like submitting a form)
- **PUT**: Update existing data
- **DELETE**: Remove data

### URL (Uniform Resource Locator)
The address of a resource on the internet. Example: `https://api.example.com/v1/users`
- `https://` - Protocol
- `api.example.com` - Domain/Host
- `/v1/users` - Path

### Endpoint
A specific URL where an API can be accessed. Think of it as a specific door in a building where you can request specific services.

**Example**: `http://ollama:11434/api/chat` is an endpoint for chatting with an AI model.

### Headers
Metadata sent along with HTTP requests and responses. They provide additional information about the request or response.

**Common headers**:
- `Content-Type: application/json` - Tells the server you're sending JSON data
- `Authorization: Bearer token123` - Provides credentials for authentication

### localhost
A hostname that refers to your own computer. When you see `localhost:8888`, it means a service running on your machine at port 8888.

### Port
A numbered endpoint for network communication on a computer. Think of it like apartment numbers in a building - the IP address is the building, and the port is the specific apartment.

**Example**: `:8888` in `http://localhost:8888` means port 8888.

### Streaming
Sending data in chunks as it's generated, rather than waiting for the entire response to be ready. Like watching a video that plays while it's still downloading.

---

## AI & Machine Learning

### LLM (Large Language Model)
An AI system trained on vast amounts of text data that can understand and generate human-like text. Examples include GPT-4, Claude, and Llama.

**Key characteristics**:
- Processes text token by token
- Predicts the most likely next piece of text
- Can perform various language tasks without specific training

### Token
The basic unit of text that an LLM processes. A token can be a word, part of a word, or even a single character.

**Examples**:
- "Hello" = 1 token
- "strawberry" = 1-2 tokens (depending on the model)
- "AI" = 1 token

**Why it matters**: LLMs have token limits (e.g., 4,096 tokens), which affects how much text they can process at once.

### Model
In AI, a model is a trained system that can make predictions or generate outputs. Think of it as a very complex function that takes input and produces output.

### Prompt
The input text you give to an LLM. A well-crafted prompt helps the model understand what you want and produce better results.

**Example**: "You are a helpful assistant. Explain quantum physics in simple terms."

### System Prompt
A special instruction that sets the overall behavior and personality of the AI throughout a conversation. It's like giving the AI a job description before it starts working.

**Example**: "You are a helpful assistant that speaks like a pirate."

### Temperature (in AI)
A parameter that controls how random or creative the AI's responses are:
- **Low temperature (0.0-0.3)**: More predictable, focused responses
- **High temperature (0.7-1.0)**: More creative, varied responses

### Deterministic vs. Non-Deterministic
- **Deterministic**: Same input always produces the same output (like a calculator: 2+2 always equals 4)
- **Non-Deterministic**: Same input can produce different outputs (like LLMs: asking "Tell me a joke" gives different jokes each time)

### Stateless
A system that doesn't remember previous interactions. Each request is independent. LLMs are stateless - they don't remember your previous conversations unless you explicitly include that history in your request.

### Function Calling (Tools)
A feature that allows LLMs to use external functions or APIs. The model can decide when it needs to call a function, what parameters to use, and how to use the result.

**Example**: An LLM can call a `get_weather()` function to get real-time weather data instead of guessing.

### Structured Output
Forcing the AI to return data in a specific format (like JSON) rather than free-form text. This makes the output easier for programs to process.

**Example**: Instead of "The temperature is 72 degrees", you get `{"temperature": 72, "unit": "fahrenheit"}`

### Few-Shot Learning
Teaching an AI by providing a few examples of what you want. Like showing someone 2-3 examples of how to solve a math problem before asking them to solve a new one.

### Chain of Thought (CoT)
A prompting technique that encourages the AI to show its reasoning step-by-step before giving a final answer. This often leads to more accurate results for complex problems.

**Example**:
```
Question: How many 'r's in 'strawberry'?
Thinking: Let me go through each letter: s-t-r-a-w-b-e-r-r-y
I see 'r' at positions 3, 8, and 9.
Answer: 3
```

### Agent
An AI system that can perceive its environment, make decisions, and take actions. In the context of LLMs, an agent maintains conversation history and can use tools to accomplish tasks.

### Retries
The number of times the system will attempt to get a valid response from the AI if the first attempt fails. Useful when you need the output to match a specific format.

### Embedding
A way of representing text as numbers (vectors) that capture meaning. Words with similar meanings have similar embeddings.

---

## Programming Concepts

### Async/Await
A way to write asynchronous code that looks like regular synchronous code. It allows your program to do other things while waiting for slow operations (like API calls) to complete.

**Example**:
```python
result = await agent.run("Hello")  # Wait for this to finish
```

### Decorator
A special function that modifies the behavior of another function. In Python, decorators are marked with `@` symbol.

**Example**:
```python
@log_function_call
def get_weather():
    # This function's behavior is modified by the decorator
    pass
```

### Type Hints
Annotations in code that specify what type of data a variable or function should use. They help catch errors and make code easier to understand.

**Example**:
```python
def greet(name: str) -> str:  # Takes a string, returns a string
    return f"Hello, {name}"
```

### Class
A blueprint for creating objects. It defines what data (attributes) and behaviors (methods) objects of that type will have.

**Example**:
```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        return "Woof!"
```

### Instance
A specific object created from a class. Like how a specific dog named "Buddy" is an instance of the Dog class.

### Method
A function that belongs to a class. It defines what actions objects of that class can perform.

### Parameter vs. Argument
- **Parameter**: The variable in a function definition
- **Argument**: The actual value you pass when calling the function

**Example**:
```python
def greet(name):  # 'name' is a parameter
    print(f"Hello, {name}")

greet("Alice")  # "Alice" is an argument
```

### Callback
A function passed as an argument to another function, to be executed later.

### Context
Additional information or state that's available to a function or system. In AI agents, context often refers to conversation history or shared state.

### Dependencies (deps)
External code or data that your program needs to work. In PydanticAI, `deps` refers to shared state passed between tools.

### Exception/Error Handling
Code that deals with errors gracefully instead of crashing. Uses `try`/`except` blocks in Python.

**Example**:
```python
try:
    result = risky_operation()
except Exception as e:
    print(f"Something went wrong: {e}")
```

---

## Data Formats

### JSON (JavaScript Object Notation)
A lightweight format for storing and exchanging data. It's easy for both humans to read and machines to parse.

**Example**:
```json
{
  "name": "Alice",
  "age": 25,
  "hobbies": ["reading", "coding"]
}
```

**Key concepts**:
- **Object**: Data enclosed in `{}` with key-value pairs
- **Array**: List of values enclosed in `[]`
- **String**: Text in quotes
- **Number**: No quotes needed
- **Boolean**: `true` or `false`
- **Null**: Represents no value

### XML (eXtensible Markup Language)
A markup language that uses tags to structure data. Similar to HTML but for data storage rather than display.

**Example**:
```xml
<person>
  <name>Alice</name>
  <age>25</age>
</person>
```

### Markdown
A lightweight markup language for formatting text. Uses simple symbols to create headings, lists, links, etc.

**Examples**:
- `# Heading` - Creates a heading
- `**bold**` - Makes text **bold**
- `[link](url)` - Creates a hyperlink

### YAML (YAML Ain't Markup Language)
A human-friendly data format often used for configuration files. Uses indentation to show structure.

**Example**:
```yaml
person:
  name: Alice
  age: 25
  hobbies:
    - reading
    - coding
```

---

## Development Tools

### Docker
A platform that packages applications and their dependencies into containers - isolated environments that run consistently anywhere.

**Why it's useful**: "It works on my machine" becomes "It works everywhere" because the container includes everything needed to run the app.

### Container
A lightweight, standalone package that includes everything needed to run a piece of software: code, runtime, system tools, libraries, and settings.

### Docker Compose
A tool for defining and running multi-container Docker applications. You describe your app's services in a YAML file, then start everything with one command.

### Image
A snapshot/template used to create containers. Like a recipe for creating a container.

### Jupyter Notebook
An interactive environment for writing and running code in small chunks (cells). Great for learning, experimentation, and data analysis.

**Features**:
- Mix code, text, and visualizations
- Run code cell by cell
- See results immediately

### Virtual Environment
An isolated Python environment that keeps project dependencies separate. Prevents conflicts between different projects.

### Package Manager
A tool that installs, updates, and manages software libraries. Examples: `pip` for Python, `npm` for JavaScript.

### Repository (Repo)
A storage location for code, typically managed by version control systems like Git. Contains all project files and their history.

### Git
A version control system that tracks changes to files over time. Allows multiple people to work on the same project without conflicts.

### Environment Variable
A variable stored outside your code that can change based on where the code runs. Often used for configuration and secrets.

**Example**: `OPENAI_API_KEY` stores your API key without hardcoding it in your code.

### Localhost
See [Networking & Web](#networking--web) section.

### Port
See [Networking & Web](#networking--web) section.

### API Key
A secret token that identifies and authenticates you when using an API. Like a password for API access.

---

## Additional Concepts

### Pydantic
A Python library for data validation using Python type hints. It ensures your data matches expected types and formats.

**Example**:
```python
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int

user = User(name="Alice", age=25)  # Valid
user = User(name="Bob", age="old")  # Error! age must be an int
```

### Schema
A definition of what data should look like - what fields it has, what types they are, and what rules they follow.

### Validation
Checking that data meets certain requirements. For example, ensuring an email address contains an "@" symbol.

### Serialization
Converting data structures into a format that can be stored or transmitted (like converting a Python object to JSON).

### Deserialization
The opposite of serialization - converting stored/transmitted data back into data structures your program can use.

### Regex (Regular Expression)
A pattern used to match and manipulate text. Like a powerful search tool with wildcards and rules.

**Example**: `r'\d{3}-\d{4}'` matches phone numbers like "555-1234"

### Literal Type
A type that can only be one of a specific set of values.

**Example**:
```python
from typing import Literal

sentiment: Literal["Positive", "Negative", "Neutral"]
# Can only be one of these three strings
```

### Field
A single piece of data in a class or data structure. Like a column in a spreadsheet.

### Mock Data
Fake data used for testing or development when real data isn't available or practical to use.

### Benchmark
A test that measures performance, usually by running the same task multiple times and comparing results.

---

## Need More Help?

If you encounter a term not listed here:
1. Just ask during the workshop - no question is too basic!
2. Check the official documentation for the specific tool or library
3. Look for some other sources like StackOverflow, GeeksForGeeks etc.
