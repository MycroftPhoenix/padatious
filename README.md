[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE.md) [![CLA](https://img.shields.io/badge/CLA%3F-Required-blue.svg)](https://mycroft.ai/cla) [![Team](https://img.shields.io/badge/Team-Mycroft_Core-violetblue.svg)](https://github.com/MycroftAI/contributors/blob/master/team/Mycroft%20Core.md) ![Status](https://img.shields.io/badge/-Production_ready-green.svg)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

# Padatious-Phoenix

Padatious Phoenix, an efficient and agile neural network intent parser. Padatious has been adapted for use with Mycroft Phoenix, leveraging scikit-learn instead of FANN2. Mycroft Phoenix is currently in its early stages of development, with the ultimate goal of porting Mycroft to Windows, Mac, and Android using Termux.

Whether you're a seasoned developer or just getting started, any help or contribution is greatly appreciated. As someone who utilizes AI to generate scripts and make corrections, I'm always open to collaboration and feedback. Contributions are not limited to Padatious-Phoenix but also extend to Mycroft Phoenix or any other part of the project. Together, we can make Padatious-Phoenix and Mycroft Phoenix even better.

If you're interested in joining the project or have any questions, feel free to reach out to me at `stevechretien111@protonmail.com`. Your input and support are invaluable as we continue to improve Padatious-Phoenix. You can also check out the project on [GitHub](https://github.com/MycroftPhoenix/) for more information and updates.

## Features
- Intents are easy to create
- Requires a relatively small amount of data
- Intents run independent of each other
- Easily extract entities (ie. Find the nearest *gas station* -> `place: gas station`)
- Fast training with a modular approach to neural networks

## Getting Started

### Installing

Padatious requires the following native packages to be installed:

- Python development headers
- `pip3`
- `swig`

Ubuntu:

```bash
sudo apt-get install  python3-dev python3-pip swig
```

Next, install Padatious via `pip3`:

```bash
pip3 install padatious-phoenix
```

### Dependencies

- scikit-learn==1.2.2
- xxhash
- padaos
- NumPy==1.17.3
- scipy==1.6.0
- joblib==1.1.1
- threadpoolctl>=2.0.0

### Example

Here's a simple example of how to use Padatious:

#### program.py
```Python
from padatious import IntentContainer

container = IntentContainer('intent_cache')
container.add_intent('hello', ['Hi there!', 'Hello.'])
container.add_intent('goodbye', ['See you!', 'Goodbye!'])
container.add_intent('search', ['Search for {query} (using|on) {engine}.'])
container.train()

print(container.calc_intent('Hello there!'))
print(container.calc_intent('Search for cats on CatTube.'))

container.remove_intent('goodbye')
```

Run with:

```bash
python3 program.py
```
