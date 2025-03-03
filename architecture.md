# Architecture Overview

The model processes 3 tokens as context through the following layers:

1. Token Embedding Layer
   - Converts token IDs to dense vectors

2. LSTM Layer
   - Processes embedded tokens sequentially
   - Maintains hidden state and cell state

3. Logits Layer
   - Generates next token predictions