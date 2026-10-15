# VectorDB-From-Scratch

### A C++ Vector Database and Semantic Search Engine

**VectorDB-From-Scratch** is a C++ project focused on vector storage, similarity search, and semantic retrieval. It demonstrates the fundamental concepts behind vector databases, including vector representations, similarity metrics, indexing strategies, and AI-powered retrieval using Ollama.

The project includes a web-based interface for interacting with the database and exploring vector search functionality.

---

## 🚀 Project Overview

Traditional databases primarily retrieve information using exact values, keywords, or predefined conditions. Vector databases provide another approach by representing data as numerical vectors and comparing those vectors to identify similar items.

This project explores how a vector database can be implemented using C++.

The application aims to demonstrate:

* Storing and retrieving vector representations.
* Searching for similar vectors using distance metrics.
* Exploring different vector search and indexing approaches.
* Connecting vector search with AI embedding models.
* Providing a web interface for interacting with the system.

The project is also a practical introduction to concepts used in semantic search and Retrieval-Augmented Generation (RAG).

## ✨ Features

### 1. Vector Storage and Retrieval

Store numerical vector representations and retrieve relevant information through similarity-based searches.

### 2. Similarity Search

Compare vectors using distance or similarity measures, such as:

* Cosine similarity
* Euclidean distance
* Manhattan distance

The availability of each metric depends on its implementation in the source code.

### 3. Vector Search Algorithms

Explore different approaches to finding similar vectors, including:

* Brute-force search
* KD-Tree-based search
* Hierarchical Navigable Small World (HNSW) indexing

**Note:** Include only the algorithms that are implemented and working in the current source code.

### 4. Web-Based Interface

Interact with the application through a browser-based interface served by the C++ backend.

### 5. AI Embedding Integration

Integrate with Ollama-compatible embedding models to convert text into vector representations, if supported by the configured application workflow.

### 6. Semantic Search

Use vector similarity to retrieve content based on semantic relationships rather than relying exclusively on exact keyword matches.

### 7. RAG Exploration

Explore how retrieved information can provide context to a language model when generating responses, provided the relevant retrieval and generation components are configured.

---

## 🛠️ Tech Stack

| Technology          | Purpose                                           |
| ------------------- | ------------------------------------------------- |
| C++                 | Core application and vector-search implementation |
| HTML                | Web interface structure                           |
| HTTP server library | Handling HTTP requests from the browser           |
| Ollama              | Local AI model integration                        |
| Embedding models    | Converting text into vector representations       |
| Git and GitHub      | Version control and project hosting               |
| VS Code             | Development environment                           |

**Important:** The technologies above describe the project's intended components. Verify each dependency against the actual source code and configuration before presenting it as a confirmed implementation.

---

## 🏗️ System Architecture

The application can be understood through the following high-level architecture:

```text
                ┌────────────────────────┐
                │       User             │
                └───────────┬────────────┘
                            │
                            ▼
                ┌────────────────────────┐
                │   Web-Based Interface  │
                │        HTML            │
                └───────────┬────────────┘
                            │ HTTP Requests
                            ▼
                ┌────────────────────────┐
                │      C++ Backend       │
                │                        │
                │ Request Handling       │
                │ Vector Operations      │
                │ Search Processing      │
                └───────────┬────────────┘
                            │
                            ▼
                ┌────────────────────────┐
                │    Vector Database     │
                │                        │
                │ Vector Storage         │
                │ Similarity Calculation │
                │ Search / Indexing      │
                └───────────┬────────────┘
                            │
                            ▼
                ┌────────────────────────┐
                │   Search Results       │
                └────────────────────────┘

              Optional AI Integration
                            │
                            ▼
                ┌────────────────────────┐
                │        Ollama          │
                │ Embedding / LLM Models │
                └────────────────────────┘
```

*This is a conceptual architecture. The exact request flow and component boundaries depend on the implementation in `main.cpp` and `index.html`.*

---

## 🔄 Application Workflow

The expected workflow for vector search is:

1. **Start the backend:** Compile and launch the C++ application.
2. **Open the interface:** Visit the local server in a browser.
3. **Provide input:** Enter a query or supply data using the functionality supported by the interface.
4. **Generate embeddings:** If configured, use an embedding model to convert text into vectors.
5. **Search the database:** Compare the query vector with stored vectors.
6. **Rank results:** Order matching items according to the implemented similarity or distance measure.
7. **Display results:** Return the results to the web interface.
8. **Generate a response:** If RAG is implemented and enabled, provide retrieved context to a language model.

Not every step is necessarily automated in the current version. The actual workflow should be confirmed against the implementation.

---

## 📂 Project Structure

The repository contains the following core files:

```text
VectorDB-From-Scratch/
│
├── main.cpp       # C++ application and backend logic
├── httplib.h      # HTTP server/client library header
├── index.html     # Browser-based user interface
├── README.md      # Project documentation
└── .gitignore     # Git ignore rules
```

Additional files may be present depending on the current repository version.

---

## 💻 Prerequisites

Before running the project, install the following tools:

### 1. Visual Studio Code

Use VS Code to open, edit, compile, and run the project.

Official website: https://code.visualstudio.com/

### 2. C++ Compiler

A C++17-compatible compiler is required.

On Windows, you can install GCC through MSYS2.

Official website: https://www.msys2.org/

After installing the appropriate GCC toolchain, ensure that the compiler's `bin` directory is added to your Windows `PATH`.

For an MSYS2 UCRT64 installation, the typical directory is:

```text
C:\msys64\ucrt64\bin
```

Verify the installation in the VS Code terminal:

```powershell
g++ --version
```

### 3. Git

Git is required to clone and manage the repository.

Official website: https://git-scm.com/

Verify the installation:

```powershell
git --version
```

### 4. Ollama (Optional)

Install Ollama if the application's embedding or language-model functionality requires it.

Official website: https://ollama.com/

---

## ⚙️ Installation and Setup

### Step 1: Clone the Repository

Open the VS Code terminal or PowerShell and run:

```powershell
git clone https://github.com/karanAI01/VectorDB-From-Scratch.git
```

### Step 2: Navigate to the Project Directory

```powershell
cd VectorDB-From-Scratch
```

### Step 3: Open the Project in VS Code

If VS Code's command-line launcher is available, run:

```powershell
code .
```

Alternatively, open VS Code manually and select the cloned project folder.

### Step 4: Verify the Project Files

Run:

```powershell
dir
```

Confirm that the source files, including `main.cpp` and `index.html`, are present.

---

## ▶️ Build and Run

### Step 1: Open the Terminal

In VS Code, select:

**Terminal → New Terminal**

Make sure the terminal is inside the project directory.

### Step 2: Compile the C++ Application

For a Windows GCC toolchain, try:

```powershell
g++ -std=c++17 -O2 main.cpp -o db.exe -lws2_32
```

This command:

* `g++` invokes the GNU C++ compiler.
* `-std=c++17` enables the C++17 language standard.
* `-O2` enables compiler optimizations.
* `main.cpp` specifies the source file.
* `-o db.exe` names the generated executable.
* `-lws2_32` links the Windows Sockets library.

**Troubleshooting:** This command assumes that the source code uses Windows networking and does not require additional libraries. If compilation fails, inspect the compiler error and the networking implementation before changing the command.

### Step 3: Run the Application

After successful compilation, execute:

```powershell
.\db.exe
```

### Step 4: Open the Web Interface

If the application starts its HTTP server on port `8080`, open:

http://localhost:8080

Use the actual port printed by the application if it differs.

### Step 5: Test the Application

Try the available actions in the interface. Follow the input format and functionality implemented by the current version of the project.

---

## 🤖 Ollama Integration

Ollama can run supported language and embedding models locally.

Official website: https://ollama.com/

### Step 1: Install Ollama

Download and install Ollama for your operating system.

### Step 2: Download an Embedding Model

If the application is configured to use `nomic-embed-text`, run:

```powershell
ollama pull nomic-embed-text
```

### Step 3: Download a Language Model

If the application uses `llama3.2` for text generation, run:

```powershell
ollama pull llama3.2
```

### Step 4: Verify the Models

Run:

```powershell
ollama list
```

Check that the required models appear in the list.

### Step 5: Start the Application

Start the C++ application and test the AI-related features supported by its implementation.

**Important:** Downloading a model does not automatically integrate it with the application. The C++ backend must send requests to Ollama using the correct endpoint, model name, and request format. Verify these details in `main.cpp`.

---

## 🔌 API Documentation

The C++ backend may expose HTTP endpoints for interacting with the database and web interface.

Before documenting individual endpoints, inspect the route definitions in `main.cpp`. The method, path, request body, and response format must match the actual implementation.

Use the following table as a documentation template:

| Method | Endpoint               | Purpose                            |
| ------ | ---------------------- | ---------------------------------- |
| GET    | Verify from `main.cpp` | Describe the implemented operation |
| POST   | Verify from `main.cpp` | Describe the implemented operation |
| GET    | Verify from `main.cpp` | Describe the implemented operation |

### Example API Documentation Format

Once you confirm an endpoint in the source code, document it like this:

```http
POST /your-actual-endpoint
Content-Type: application/json
```

Example request body:

```json
{
  "query": "your search query"
}
```

Example response:

```json
{
  "results": []
}
```

**These request and response examples are illustrative only.** Replace them with the actual endpoint, JSON fields, and response format implemented in the project. Do not publish placeholder endpoints as working APIs.

---

## 📸 Screenshots

![Home Page](https://github.com/karanAI01/VectorDB-From-Scratch/blob/main/home.png)

## 🎯 Use Cases

Vector databases and similarity-search systems are useful in a variety of applications:

* **Semantic Search:** Retrieve information based on meaning rather than exact keyword matches.
* **Document Retrieval:** Find documents similar to a user's query.
* **Recommendation Systems:** Identify items with similar vector representations.
* **AI Applications:** Supply relevant information to language models.
* **RAG Systems:** Retrieve relevant context before generating an AI response.
* **Learning and Experimentation:** Understand vector representations, distance metrics, and indexing techniques.

These are potential applications of the concepts explored in this project, not a claim that every use case is fully implemented.

---

## 🔮 Future Improvements

Potential enhancements include:

* [ ] Add persistent vector storage.
* [ ] Improve error handling and input validation.
* [ ] Add automated unit and integration tests.
* [ ] Benchmark search performance across different algorithms.
* [ ] Add support for larger vector datasets.
* [ ] Improve indexing and nearest-neighbor search performance.
* [ ] Expand the web interface with search history and result details.
* [ ] Add configurable embedding models.
* [ ] Improve RAG retrieval and response quality.
* [ ] Add Docker support for easier deployment.
* [ ] Add continuous integration and automated builds.
* [ ] Publish complete API documentation based on the implemented routes.

---

## 📚 Learning Outcomes

This project provides an opportunity to explore:

* C++ application development.
* Vector representations and similarity calculations.
* Nearest-neighbor search concepts.
* Data structures and indexing strategies.
* HTTP communication between a frontend and backend.
* Local AI model integration.
* Embedding-based semantic retrieval.
* The fundamentals of Retrieval-Augmented Generation.
* Git and GitHub project management.

---

## 🤝 Contributing

Contributions, suggestions, and bug reports are welcome.

To contribute:

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test your changes locally.
5. Commit your work.
6. Open a pull request describing the changes.

Example:

```bash
git checkout -b feature/your-feature
git add .
git commit -m "Add your feature"
git push origin feature/your-feature
```

---

## 📄 License

No license is specified in this README.

If you want others to reuse, modify, or distribute your code under defined terms, add an appropriate license file to the repository and update this section.

---

## 👨‍💻 Author

**Karan Verma**

GitHub: https://github.com/karanAI01

**Repository:** https://github.com/karanAI01/VectorDB-From-Scratch

---

⭐ If you find this project useful, consider starring the repository!
