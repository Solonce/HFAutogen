# HFAutogen
Seemlessly use models provided by the HuggingFace Inference API  with Autogen.

## Introduction
HFAutogen bridges the gap between Hugging Face's powerful inference API and the convenience of AutoGen, providing a seamless integration for developers looking to leverage the best of both worlds. This software enables the use of Hugging Face models with AutoGen's automated code generation capabilities, making it easier to implement AI-powered features without the need for large computational power.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Dependencies](#dependencies)
- [Configuration](#configuration)
- [Documentation](#documentation)
- [Examples](#examples)
- [Troubleshooting](#troubleshooting)
- [Contributors](#contributors)
- [License](#license)

## Installation
```
pip install hfautogen
```

## Usage
HFAutogen uses three objects that are useful to the user. `ModelAgent()`, `UserAgent()`, and `InitChat()`
- `ModelAgent(name, system_message, code_execution)`
  - name - _str_ required
    >The name of the `ModelAgent()`
  - system_message - _str_ optional
    >_default:_ ""<br>
    >The contextual prompt for `ModelAgent()`
  - code_execution - _dict_ optional
    >_default:_ False<br>
    >A dictionary that contains a `work_dir` and `use_docker` entry:<br>
    >Ex: {"work_dir": "coding", "use_docker": False}

- `UserAgent(name, max_consecutive_auto_reply, code_dir, use_docker, system_message)`
  - name - _str_ required
    >The name of the `ModelAgent()`
  - max_consecutive_auto_reply - _int_ optional
    >_default:_ 2<br>
    >The maximum number of consecutive automatic replies made by the `UserAgent()`
  - coding_dir - _str_ optional
    >_default:_ "coding"<br>
    >The directory `UserAgent()` will use and operate out of.
  - user_docker - _bool_ optional
    >_default:_ False<br>
    >If true, `UserAgent()` will use a docker.
  - system_message - _str_ optional
    >_default:_ ""<br>
    >The contextual prompt for `UserAgent()`
- `InitChat(user, agent, _input)`
  - user - _`UserAgent()`_ required
    >A `UserAgent()` object
  - agent - _`ModeAgent()`_ required
    >A `ModelAgent()` object
  - _input - _str_ required
    >The initial input prompt.
```
```
