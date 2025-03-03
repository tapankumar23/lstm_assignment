# LSTM Next Word Prediction Assignment

## Problem Statement
Implement a handwritten LSTM for next-word prediction with the following specifications:
- Vocabulary Size (V) = 5
- Hidden State Size (h) = 2
- Token Embedding Size (e) = 2
- Context Size (c) = 3

## Task Requirements
1. Process 3 context tokens through:
   - Token Embedding Layer
   - LSTM Layer
   - Logits Layer for next token prediction

2. Show detailed calculations for:
   - Token embedding conversions
   - LSTM gate computations
   - Hidden state and cell state updates
   - Final token prediction

## Documentation
- [LSTM Solution](lstm_solution.md) - Detailed implementation with calculations
- [Flow Diagram](flow_diagram.md) - Visual representation of LSTM architecture and data flow

## Architecture Overview
```
Input [x₁, x₂, x₃] → Embedding → LSTM → Dense → Output
```
Each token xᵢ is processed sequentially through the LSTM layer, maintaining hidden state hᵢ and cell state cᵢ. The final hidden state is used to predict the next token probability distribution.