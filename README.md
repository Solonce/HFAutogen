# HFAutogen
Seemlessly use models provided by the HuggingFace Inference API  with Autogen.

## Introduction
HFAutogen bridges the gap between Hugging Face's powerful inference API and the convenience of AutoGen, providing a seamless integration for developers looking to leverage the best of both worlds. This software enables the use of Hugging Face models with AutoGen's automated code generation capabilities, making it easier to implement AI-powered features without the need for large computational power.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Dependencies](#dependencies)
- [Examples](#examples)
- [License](#license)

## Installation
```
pip install hfautogen
```

## Usage
HFAutogen uses three objects that are useful to the user. `ModelAgent()`, `UserAgent()`, and `InitChat()`

### `ModelAgent(name, system_message, code_execution)`
```  
    -name - _str_ required
        The name of the `ModelAgent()`
        system_message - _str_ optional
    
    _default:_ "" - _str_ optional
        The contextual prompt for `ModelAgent()`
    
    code_execution - _dict_ optional
        _default:_ False
        A dictionary that contains a `work_dir` and `use_docker` entry:

        Ex:
           {"work_dir": "coding", "use_docker": False}
```
<br>

### `UserAgent(name, max_consecutive_auto_reply, code_dir, use_docker, system_message)`
```
  - name - _str_ required
    The name of the `ModelAgent()`
  
  - max_consecutive_auto_reply - _int_ optional
    _default:_ 2
    The maximum number of consecutive automatic replies made by the `UserAgent()`

  - coding_dir - _str_ optional
    _default:_ "coding"
    The directory `UserAgent()` will use and operate out of.

  - user_docker - _bool_ optional
    _default:_ False
    If true, `UserAgent()` will use a docker.

  - system_message - _str_ optional
    _default:_ ""
    The contextual prompt for `UserAgent()`
```

### `InitChat(user, agent, _input)`
```
  - user - _`UserAgent()`_ required
    A `UserAgent()` object

  - agent - _`ModeAgent()`_ required
    A `ModelAgent()` object

  - _input - _str_ required
    The initial input prompt.
```

## Features

### Free to use, extremely lightweight access to open source HuggingFace Models.

### Automatic Code Execution

### Multi Agent Communication

### Fast Prototyping
<br><br><br>
## Dependencies

### pyautogen ==0.2.10

### transformers =4.38.0
<br><br><br>
## Examples

### Example 1
In this example, we are importing the required functions to set up a user agent, an assistant agent, and initializing the chat between the two. We start the chat with the prompt given with _input.
```
from hfautogen import ModelAgent, UserAgent, InitChat

_input = input("Enter Text:)

user = UserAgent("user_agent")
assistant = ModelAgent("model_agent")

InitChat(user, assistant, _input)
```
