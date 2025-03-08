 # LinkSeek: Agentic Graph Analysis App

## Overview

LinkSeek is an agentic graph analysis application built for the ArangoDB Hackathon. It enables users to explore and analyze complex event relationships using **GDELT data**, stored and queried in **ArangoDB**. The system is built with **Jupyter Notebook**, **Gradio**, and **Flask**, offering an intuitive way to interact with graph data through natural language queries.

## Features

- **Graph-Based Querying**: Retrieve event insights using **GraphRAG** and **ArangoDB** queries.
- **Natural Language Processing**: Convert user queries into meaningful graph operations.
- **Interactive Visualizations**: Explore graphs dynamically using **Cosmograph**.
- **Multiple Hosting Options**: Deploy on **AWS EC2, Hugging Face, GCP, or locally**.

## Tech Stack

- **Database**: ArangoDB (Graph database for event storage and querying)
- **Backend**: Flask (or Ngrok for tunneling local deployments)
- **Frontend**: Gradio (for easy UI exposure)
- **Notebook**: Jupyter (Main development environment)
- **Visualization**: Cosmograph (Graph visualization tool)
- **Cloud Deployment**: AWS, GCP, Hugging Face Spaces

---

## Setup Guide

### 1. Clone the Repository

```sh
git clone https://github.com/Daenarys8/linkseek.git
cd linkseek
```

### 2. Install Dependencies

Ensure you have Python 3.8+ installed, then install dependencies:
N.B: requirements.txt was generated from google colab.

```sh
pip install -r requirements.txt
```
You can also install the dependencies from the notebook. 

### 3. Configure Environment Variables

Create a `.env` file using the provided `.env.example` as a reference.

```sh
cp .env.example .env
```

Modify the `.env` file to include:
Only add ngrok if you'd like to use it to expose the flask app.

```env
AWS_ACCESS_KEY_ID=xxxxxxxxxxxxxxxx
AWS_SECRET_ACCESS_KEY=xxxxxxxxxxxxxxxxxxxxxxx
AWS_REGION=xxxxxxxxxx
ARANGO_HOST=xxxxxxxxxxxxxxxxxxxxxxxxxxx
ARANGO_USER=xxxxxxxxxxx
ARANGO_PASS=xxxxxxxxxxxxxxxxxxxxxxx
ARANGO_DB=xxxxxxxxxx
NGROK_AUTH_TOKEN=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### 4. Set Up ArangoDB

#### Local Setup:

- Install [ArangoDB](https://www.arangodb.com/download/) locally.
- Start the database and create a collection for **GDELT data**.

#### Cloud Setup:

- Use [ArangoDB Oasis](https://cloud.arangodb.com/) for a managed instance.
- Ensure the credentials in `.env` match the database setup.

### 5. Load the GDELT Dataset

Open the notebook to ingest the GDELT dataset into ArangoDB or use arango-datasets to load your graph:

### 6. Start the Flask API
Execute the ingestion cells in `ArangoHackathon.ipynb` to populate the database.



## Deployment Options

### **1. AWS EC2**

- Launch an Ubuntu EC2 instance.
- Install Python, ArangoDB, and required libraries.
- Use `gunicorn` or `nohup` to keep the Flask app running.

### **2. Hugging Face Spaces**

- Create a new **Gradio** Space.
- Upload the repository and configure environment variables.
- Deploy and access the app via the Hugging Face UI.

### **3. Google Cloud Platform (GCP)**

- Deploy using **Google Compute Engine** (GCE).
- Use a VM instance with Python, Flask, and ArangoDB installed.
- Expose the Gradio UI via a public IP.

---

## Usage

1. **Run Queries**

   - Enter a natural language query in the Gradio UI.
   - Example: "Show all political events in 2015."
   - The app processes the query, fetches relevant graph data, and visualizes it.

2. **Explore Graphs**

   - Use **Cosmograph** for dynamic visualization.
   - Hover over nodes to view relationships and connections.

3. **Extend & Customize**

   - Modify the agent logic in the notebook to support additional query types.
   - Extend visualization options using available Plotly or NetworkX functions in the notebookfor smaller graph.

---

## Future Enhancements

- **Real-time GDELT Integration** for continuous event updates.
- **Advanced Graph Algorithms** to improve query accuracy.
- **Multi-Cloud Deployments** for better scalability.

---

## License

This project is open-source under the **MIT License**. Cosmograph is used under the **CC BY-NC 4.0** license.

---

## Credits
- **Graph Database & Infrastructure**: ArangoDB Community
- **UI/UX Design**: Freepik (Image Assets), NoCrypt (Miko Gradio Theme)
- **Dataset**: GDELT Project

For any issues or contributions, please submit a pull request or open an issue in the repository.


