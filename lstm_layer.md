# LSTM Layer Implementation

## Parameters
### Weight Matrices and Biases
- Weights: Wf, Wi, Wo, Wc (forget, input, output, cell gates)
- Biases: bf, bi, bo, bc
- Dimensions: W ∈ ℝ^(2×4), b ∈ ℝ^2

### State Vectors
- Hidden State (ht): ht ∈ ℝ^h (stores information about past inputs)
- Cell State (ct): ct ∈ ℝ^h (stores long-term memory)

## Computations
For each token xt:
1. Forget Gate: ft = σ(Wf[ht-1, xt] + bf)
2. Input Gate: it = σ(Wi[ht-1, xt] + bi)
3. Output Gate: ot = σ(Wo[ht-1, xt] + bo)
4. Cell State Update: ct = ft ⊙ ct-1 + it ⊙ c̃t
5. Candidate Cell State: c̃t = tanh(Wc[ht-1, xt] + bc)
6. Hidden State Update: ht = ot ⊙ tanh(ct)

## Initialization
- Initial hidden state h₀ = [0, 0]
- Initial cell state c₀ = [0, 0]
- Weights (Wf, Wi, Wo, Wc) are randomly initialized

Note: σ represents the sigmoid activation function: σ(x) = 1/(1 + e^(-x))