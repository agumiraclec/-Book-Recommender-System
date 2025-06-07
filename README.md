# -Book-Recommender-System
📚 Book Recommender System

A semantic book recommendation engine built with Python, leveraging LangChain for document processing and embeddings, and Gradio for an intuitive web interface. This system allows users to discover books based on textual descriptions, categories, and desired emotional tones.
✨ Features

    Semantic Search: Find books similar to a given query description using state-of-the-art sentence embeddings (sentence-transformers/all-MiniLM-L6-v2).

    Category Filtering: Narrow down recommendations by specific book genres or categories.

    Emotional Tone Filtering: Refine results based on desired emotional tones such as "Happy," "Surprising," "Angry," "Suspenseful," or "Sad," derived from pre-analyzed book descriptions.

    Interactive Web UI: A user-friendly interface powered by Gradio for easy interaction and real-time recommendations.

    Scalable Embeddings: Utilizes Chroma as a vector store for efficient similarity search on book descriptions.

🚀 Technologies Used

    Python: The core programming language.

    Pandas & NumPy: For efficient data handling and manipulation.

    LangChain: For document loading, text splitting, and integration with vector databases.

    HuggingFace Embeddings: Specifically sentence-transformers/all-MiniLM-L6-v2 for generating semantic embeddings.

    Chroma: A lightweight, in-memory vector database for storing and querying document embeddings.

    Gradio: For quickly building and deploying the interactive web application.

    python-dotenv: For managing environment variables.

💡 How It Works

The system first loads and processes book descriptions from tagged_description.txt, creating vector embeddings for each using the sentence-transformers/all-MiniLM-L6-v2 model. These embeddings are stored in a Chroma vector database.

When a user provides a query and optional filters (category, emotional tone), the system performs a semantic similarity search in the vector database to find the most relevant books. The top results are then filtered by the selected category and sorted by the specified emotional tone, providing a tailored list of book recommendations. Book metadata (title, author, thumbnail, description) is retrieved from books_with_emotions.csv.
🛠️ Setup and Usage

To get this project up and running on your local machine, follow these steps:

    Clone the repository:
      git clone https://github.com/agumiraclec/book-recommender.git
      cd book-recommender
      
    Create a virtual environment (recommended):
      python -m venv venv
      source venv/bin/activate  # On Windows: venv\Scripts\activate

    Install dependencies:
      pandas
      numpy
      python-dotenv
      langchain
      langchain-community
      langchain-openai
      langchain-chroma
      sentence-transformers
      gradio

    Then, install them:

      pip install -r requirements.txt

    Prepare data files:
      Ensure you have the following data files in the root directory of your project:
      books_with_emotions.csv: Contains book metadata, including titles, authors, descriptions, thumbnails, and pre-calculated emotion scores.
      tagged_description.txt: Contains the text descriptions used for generating embeddings, with book IDs.

Run the application
  python your_main_script_name.py # Replace 'your_main_script_name.py' with the actual name of your Python script (e.g., app.py or main.py)

The Gradio interface will launch in your browser, typically at http://127.0.0.1:7860 (or a similar address). If share=True is enabled, it will also provide a public shareable link.


🔮 Future Enhancements

    Integrate more sophisticated filtering and sorting options (e.g., by publication year, rating).

    Allow users to provide feedback on recommendations to improve future results (e.g., user-based collaborative filtering).

    Expand the dataset and potentially use larger, more advanced embedding models for richer semantic understanding.

    Implement user authentication and personalized recommendation history.

    Explore deploying the model as a more robust API service.

