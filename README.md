# Tiny Language Compiler – Parser Design

## 📌 Overview

This project implements a **simple compiler for a Tiny Language**.
The compiler is designed to demonstrate fundamental **compiler design concepts** including lexical analysis, syntax analysis, and code generation.

The compiler processes a Tiny Language program and converts it into an intermediate or executable representation through multiple phases.

The project is implemented using **Python**, making it easy to understand and extend.

---

# 🧩 Compiler Architecture

The Tiny Language Compiler is divided into **three main modules**:

1. **Lexer (Lexical Analysis)** – `lex.py`
2. **Parser (Syntax Analysis)** – `parse.py`
3. **Emitter (Code Generation)** – `emit.py`

These modules work together to convert source code into structured output.

---

# 1️⃣ Lexical Analysis (Lexer)

### File

```
lex.py
```

### Role

The **lexer** reads the source program and converts it into a sequence of **tokens**.

A **token** is a meaningful unit such as:

* keywords
* identifiers
* numbers
* operators
* punctuation symbols

### Working of the Lexer

The lexer performs the following tasks:

* Reads the input **character by character**
* Groups characters into **tokens**
* Identifies:

  * keywords
  * variables
  * numbers
  * operators
* Removes **whitespace and comments**
* Sends tokens to the parser

### Example

Input program:

```
LET x = 10
PRINT x
```

Generated tokens:

```
LET
IDENTIFIER(x)
EQUALS
NUMBER(10)
PRINT
IDENTIFIER(x)
```

---

# 2️⃣ Syntax Analysis (Parser)

### File

```
parse.py
```

### Role

The **parser** checks whether the sequence of tokens follows the **grammar rules** of the Tiny Language.

If the syntax is valid, the parser builds a **parse structure** for further processing.

### Responsibilities

The parser:

* Receives tokens from the lexer
* Verifies grammar rules
* Detects syntax errors
* Controls program flow
* Calls the emitter to generate output code

### Example Grammar

Example grammar rule:

```
statement → PRINT expression
expression → number | identifier
```

Example program:

```
PRINT 5
```

The parser validates that `PRINT` is followed by a valid expression.

---

# 3️⃣ Code Generation (Emitter)

### File

```
emit.py
```

### Role

The **emitter** generates the output code based on the parsed structure.

This stage converts the validated syntax into a **target representation** such as:

* intermediate code
* assembly-like instructions
* or executable code

### Responsibilities

The emitter:

* Receives parsed structures
* Produces output code
* Writes results to an output file

Example output:

```
LOAD 10
STORE x
PRINT x
```

---

# 🛠 Technologies Used

* Python
* Compiler Design Concepts
* Lexical Analysis
* Syntax Parsing
* Code Generation

---

# 📂 Project Structure

```
TinyLanguageCompiler/
│
├── lex.py
├── parse.py
├── emit.py
├── main.py
└── README.md
```

---

# ⚙️ How to Run the Project

### Step 1: Navigate to the project directory

```
cd TinyLanguageCompiler
```

### Step 2: Run the compiler

```
python main.py
```

### Step 3: Provide Tiny Language input program

Example:

```
LET x = 10
PRINT x
```

The compiler will process the program and generate output code.

---

# 📊 Concepts Demonstrated

This project demonstrates important **compiler design concepts**:

* Lexical Analysis
* Token Generation
* Syntax Parsing
* Grammar Rules
* Code Generation
* Error Detection

---

# 🚀 Future Improvements

* Add **semantic analysis**
* Add **symbol table management**
* Support **loops and conditionals**
* Generate **assembly code**
* Build **AST (Abstract Syntax Tree)**

---

# 👨‍💻 Author

**Anshu Kumar**
Computer Science & Engineering Student

---

# 📜 License

This project is developed for **educational purposes in Compiler Design**.
