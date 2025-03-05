
```mermaid
graph TD
A[Online Store] -->|Download PDFs| B[PDF Storage]
B -->|Extract Text| C[Text Processor]
C -->|Preprocess Data| D[Vector Database]
D -->|Index Data| E[Embeddings Model]
E -->|Train GPT| F[Custom GPT Model]
F -->|Deploy Model| G[Inference API]
G -->|User Queries| H[Web/App Interface]
H -->|Query Processing| I[Response Generation]
