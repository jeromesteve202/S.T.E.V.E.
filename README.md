# S.T.E.V.E. - Semantic Transformer for Expressive Verbal Embeddings

A project to build a Large Language Model (LLM) from scratch, focusing on understanding the fundamental components of modern transformer-based language models.

## 🎯 Project Overview

S.T.E.V.E. is an educational journey into the inner workings of Large Language Models. The goal is to implement each component of a transformer-based LLM from the ground up, starting with the foundational building blocks and progressing to a fully functional language model.

## 🚀 Current Progress

### ✅ Completed Components

#### 1. **Tokenization System** (`tokens.py`)
- **SimpleTokenizerV1**: Basic tokenization with vocabulary mapping
  - Implements `encode()` and `decode()` methods
  - Uses regex-based text preprocessing
  - Handles punctuation and whitespace splitting
  - Maps tokens to integer IDs and vice versa

- **SimpleTokenizerV2**: Enhanced tokenization with special tokens
  - Added `<|endoftext|>` and `<|unk|>` special tokens
  - Improved handling of unknown tokens
  - Enhanced punctuation handling with additional separators
  - Better text reconstruction during decoding

#### 2. **Data Processing**
- Downloads training text from external source (`the-verdict.txt`)
- Implements text preprocessing with regex-based tokenization
- Creates vocabulary from unique tokens
- Handles UTF-8 encoding for international text support

#### 3. **Vocabulary Management**
- Dynamic vocabulary creation from training data
- Bidirectional mapping (string ↔ integer)
- Support for special tokens
- Vocabulary size tracking

## 🔧 Technical Implementation Details

### Tokenization Process
1. **Text Preprocessing**: Uses regex to split text on punctuation and whitespace
2. **Token Cleaning**: Removes empty tokens and strips whitespace
3. **Vocabulary Building**: Creates unique token set with integer mappings
4. **Encoding**: Converts text to integer token IDs
5. **Decoding**: Reconstructs text from token IDs with proper formatting

### Special Features
- **Unknown Token Handling**: `<|unk|>` token for out-of-vocabulary words
- **End-of-Text Marker**: `<|endoftext|>` for sequence boundaries
- **Punctuation Preservation**: Maintains proper spacing around punctuation
- **Bidirectional Mapping**: Efficient string ↔ integer conversions

## 🛠️ Usage

### Running the Tokenizer

```python
# Basic usage
from tokens import SimpleTokenizerV2, vocab

tokenizer = SimpleTokenizerV2(vocab)

# Encode text
text = "Hello, world!"
token_ids = tokenizer.encode(text)
print(token_ids)

# Decode back to text
decoded_text = tokenizer.decode(token_ids)
print(decoded_text)
```

### Example Output

```python
# Input: "Hello, do you like tea?"
# Output: [token_ids...]
# Decoded: "Hello, do you like tea?"
```