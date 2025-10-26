# Password Generator

A flexible Python library that generates three different types of passwords: PIN passwords, random passwords, and memorable passwords.

## Features

- **PIN Password Generator**: Generate numeric PINs of any length
- **Random Password Generator**: Create strong random passwords with customizable options
- **Memorable Password Generator**: Generate human-friendly passwords using real words

## Installation

```bash
# Clone the repository
git clone https://github.com/fereidoon/password_generator.git

# Navigate to the project directory
cd password_generator

# Install required dependencies
pip install nltk
```

## Usage

### PIN Password Generator

Generate numeric PINs of specified length:

```python
from src.PassGeneratorClass import PinGenerator

# Create a PIN generator for 8-digit PINs
pin_generator = PinGenerator(length=8)

# Generate a PIN
pin = pin_generator.generate()
print(pin)  # Example output: "75552439"
```

### Random Password Generator

Generate random passwords with customizable options:

```python
from src.PassGeneratorClass import RandomPasswordGenerator

# Create a random password generator
# Parameters:
# - length: password length (default: 8)
# - include_punctuation: include special characters (default: False)
# - include_numbers: include digits (default: False)
password_generator = RandomPasswordGenerator(
    length=12,
    include_punctuation=False,
    include_numbers=True
)

# Generate a password
password = password_generator.generate()
print(password)  # Example output: "XVoHuFvT8eRi"
```

### Memorable Password Generator

Generate passwords using real words that are easier to remember:

```python
from src.PassGeneratorClass import MemorablePasswordGenetator

# Create a memorable password generator
# Parameters:
# - number_of_words: number of words to use (default: 4)
# - seperator: character to join words (default: "_")
# - capitilaze: randomly capitalize words (default: False)
# - vocabulary: custom word list (default: NLTK words)
memorable_generator = MemorablePasswordGenetator(
    number_of_words=3,
    seperator="-",
    capitilaze=True
)

# Generate a memorable password
password = memorable_generator.generate()
print(password)  # Example output: "JAVAD-GHASEM-ghasem"
```

## Class Structure

The project uses an abstract base class `PasswordGenerator` with three concrete implementations:

1. `PinGenerator`: Generates numeric PINs
2. `RandomPasswordGenerator`: Generates random character passwords
3. `MemorablePasswordGenetator`: Generates word-based memorable passwords

Each generator implements the `generate()` method according to its specific password generation strategy.

## Dependencies

- Python 3.x
- NLTK (Natural Language Toolkit) - for word-based password generation

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.