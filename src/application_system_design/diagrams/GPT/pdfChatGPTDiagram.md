# Learning about machine learning using machine learning

Initial design.
Idea use customGPT assistant to carryout research into AI progress.

TODO - Consider using what is already available.

---

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
