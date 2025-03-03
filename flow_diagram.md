# LSTM Solution Flow Diagram

```mermaid
flowchart TD
    A("Token IDs: 1, 2, 3") --> B("Embedding Layer")
    B --> B1("x1 = [0.3, 0.4]")
    B --> B2("x2 = [0.5, 0.6]")
    B --> B3("x3 = [0.7, 0.8]")
    
    subgraph LSTM_Processing["LSTM Processing"]
        B1 --> C1("LSTM Cell t=1")
        B2 --> C2("LSTM Cell t=2")
        B3 --> C3("LSTM Cell t=3")
        
        C1 -->|"h1, C1"| C2
        C2 -->|"h2, C2"| C3
        
        subgraph LSTM_Cell["LSTM Cell Structure"]
            D1("Forget Gate")
            D2("Input Gate")
            D3("Cell Candidate")
            D4("Output Gate")
            
            D1 & D2 & D3 --> D5("Cell State Update")
            D5 & D4 --> D6("Hidden State Output")
        end
    end
    
    C3 --> H3("Final Hidden State: [0.735, 0.916]")
    H3 --> E("Output Layer")
    E --> F("Logits: [0.357, 0.787, 1.218, 1.648, 2.078]")
    
    F --> G("Apply Softmax Function")
    G --> H("Probabilities: [0.071, 0.109, 0.167, 0.257, 0.396]")
    H --> I("Predict Token ID: 4")
    
    classDef embedding fill:#f9d5e5,stroke:#333,color:black
    classDef lstm fill:#eeeeee,stroke:#333,color:black
    classDef logits fill:#d5e8d4,stroke:#333,color:black
    classDef prediction fill:#e1d5e7,stroke:#333,color:black
    classDef default stroke-width:2px,color:black
    
    linkStyle default stroke:#333,stroke-width:2px
    
    class A,B,B1,B2,B3 embedding
    class C1,C2,C3,H3,LSTM_Processing,LSTM_Cell,D1,D2,D3,D4,D5,D6 lstm
    class E,F logits
    class G,H,I prediction