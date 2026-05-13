# Hidden Markov Model (HMM) for Splice Site Detection

## Overview

This project is a simple implementation of a **Hidden Markov Model (HMM)** in Python to analyze DNA sequences and predict the most probable splice site position.

The script tests different exon–intron transition paths and calculates the log probability for each possible state sequence. In the end, it identifies the path that best explains the observed DNA sequence.

This project is useful for understanding:

* Basics of Hidden Markov Models
* DNA sequence analysis
* State transition probabilities
* Emission probabilities
* Log probability calculations in bioinformatics

---

## Project Structure

```bash
.
├── hmm.py        # Main Python script
└── README.md     # Project documentation
```

---

## Concepts Used

### Hidden Markov Model (HMM)

An HMM is a statistical model where:

* The **states** are hidden
* The **observations** are visible
* The system moves between states using transition probabilities
* Each state emits observations with certain probabilities

In this project:

| State | Meaning           |
| ----- | ----------------- |
| `E`   | Exon region       |
| `5`   | Splice donor site |
| `I`   | Intron region     |
| `s`   | Start state       |
| `e`   | End state         |

---

## Features

* Defines custom HMM states
* Uses transition probability matrices
* Uses emission probability matrices
* Computes log probabilities for stability
* Tests multiple splice positions
* Finds the most probable sequence path

---

## How the Program Works

1. A DNA sequence is provided.
2. Several possible exon–intron paths are generated.
3. For each path:

   * Transition probabilities are calculated
   * Emission probabilities are calculated
   * Total log probability is computed
4. The program compares all paths.
5. The path with the highest probability is selected.

---

## Sample Input Sequence

```python
query_sequence = "CTTCATGTGAAAGCAGACGTAAGTCA"
```

---

## Example Output

```bash
EEEEEE5IIIIIIIIIIIIIIIIIII : -54.21
EEEEEEEE5IIIIIIIIIIIIIIIII : -48.92
...

Most probable state sequence:
EEEEEEEE5IIIIIIIIIIIIIIIII
```

(The actual values may vary depending on probability settings.)

---

## Requirements

Install Python dependencies before running the project.

```bash
pip install numpy
```

---

## How to Run

```bash
python hmm.py
```

---

## Code Highlights

### Transition Probability Matrix

Controls how states change from one to another.

```python
state_transition_prob = np.array([...])
```

### Emission Probability Matrix

Defines how likely each nucleotide is emitted by a state.

```python
emission_probs = np.array([...])
```

### Log Probability Calculation

The model uses logarithms to avoid numerical underflow during multiplication of small probabilities.

```python
math.log(probability)
```

---

## Why Log Probabilities?

DNA sequence probabilities become extremely small after repeated multiplication.
Using logarithms:

* Improves numerical stability
* Prevents floating-point underflow
* Makes comparisons easier

---

## Learning Goals

This project is beginner-friendly and helps in learning:

* Bioinformatics basics
* Sequence modeling
* Probabilistic models
* Python matrix operations with NumPy
* HMM fundamentals

---

## Possible Improvements

You can extend this project by:

* Implementing the Viterbi Algorithm
* Adding visualization for state paths
* Supporting larger genomic datasets
* Training probabilities from real biological data
* Creating a GUI or web interface

---

## Author

Created as a learning project for understanding Hidden Markov Models and splice site prediction in computational biology.

---


