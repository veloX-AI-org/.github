# VeloX AI

Welcome to the VeloX AI organization. 

## Problem Statement
VeloX is an AI-powered educational platform designed to help students and was inspired by the power of generalized AI research tools (like Google's NotebookLM). While these are excellent for reading and summarizing documents, they are missing one key component for us - `Memory`: They cannot remember the last time they spoke with us and who we are. It's like talking to someone who forgets you every time you refresh.

But after all, it’s Google (a tech giant), so maybe by the time you’re using this organization, they will have already implemented that feature. So.. I was just thinking one step ahead of them.

## What We Do

Our platform enables users to:
* **Upload Custom Sources:** Upload any type of document sources and study materials. Also paste any url to add more defined sources.
* **Smart Retrieval:** Query those materials & sources and get highly relevant answers by our advanced retrieval algorithm built with LangGraph and LangChain.
* **"Did I understand the video?":** Paste a YouTube URL and instantly generate custom quizzes to test understanding of the video content.

## System Architecture
To ensure maintenance, modularity and separation of concerns, VeloX is split into some microservices architecture:

| Repository | Role | Tech Stack |
| :------- | :--- | :--- |
| [**`node-server`**](https://github.com/veloX-AI-org/node-server) | Handles user authentication, database, and serves as the crucial API for the frontend client. | Node.js, Express, MongoDB |
| [**`python-server`**](https://github.com/veloX-AI-org/python-server) | **The AI Brain**: Manages the LangGraph state graphs, vector database, and RAG pipelines. | Python, FastAPI, LangGraph, Pinecone |
| [**`mcp-server`**](https://github.com/veloX-AI-org/mcp-server) | A FastMCP server that provides our agents with external tools to read PDFs, scrape web context, and advance retrieval.| Python, FastMCP |

## Why Microservices?
By separating the architecture, the `node-server` can manage basic user traffic without getting slowed down by the heavy, long-running LLM generation tasks. `python-server` provides all AI releted end points. And the `mcp-server` lets us safely add new features, like web searching, without changing the main reasoning logic or advanced RAG systems.

## Final Thought
Yes, maybe the tech giants will eventually build persistent memory into their systems. But I'm not waiting and I'm still actively improving the system's architecture and AI pipelines.

Contributions, feedback, and ideas are welcome

## Author
~ Ankit Ahirwar
