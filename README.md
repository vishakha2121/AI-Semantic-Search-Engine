# 🚀 AI Enterprise Semantic Search Platform

<div align="center">

![AI Search Banner](https://img.shields.io/badge/AI-Semantic%20Search-blue?style=for-the-badge&logo=artificial-intelligence)
![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-14+-336791?style=for-the-badge&logo=postgresql&logoColor=white)

[![GitHub stars](https://img.shields.io/github/stars/vishakha2121/AI-Semantic-Search-Engine)](https://github.com/vishakha2121/AI-Semantic-Search-Engine/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/vishakha2121/AI-Semantic-Search-Engine)](https://github.com/vishakha2121/AI-Semantic-Search-Engine/network)
[![GitHub issues](https://img.shields.io/github/issues/vishakha2121/AI-Semantic-Search-Engine)](https://github.com/vishakha2121/AI-Semantic-Search-Engine/issues)
[![GitHub license](https://img.shields.io/github/license/vishakha2121/AI-Semantic-Search-Engine)](https://github.com/vishakha2121/AI-Semantic-Search-Engine/blob/main/LICENSE)

</div>

---

## 📋 **Table of Contents**
- [Overview](#-overview)
- [Key Features](#-key-features)
- [Technology Stack](#-technology-stack)
- [System Architecture](#-system-architecture)
- [Installation Guide](#-installation-guide)
- [Project Structure](#-project-structure)
- [API Documentation](#-api-documentation)
- [Database Schema](#-database-schema)
- [Performance Optimization](#-performance-optimization)
- [Screenshots](#-screenshots)
- [Testing](#-testing)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 **Overview**

**AI Enterprise Semantic Search Platform** is an intelligent, full-stack search engine that combines **Hybrid Retrieval**, **Semantic Ranking**, **Knowledge Graphs**, and **Context-Aware Answers** to deliver precise, relevant, and contextual search results across multilingual documents.

This platform transforms traditional keyword-based search into an AI-powered discovery engine that understands user intent, maintains context, and provides verifiable citations with source attribution.

### 🎯 **Purpose**
- **Practice Project**: Built for learning and demonstrating AI/ML concepts
- **Interview Showcase**: Designed to impress with full-stack implementation
- **Educational Tool**: Hands-on experience with modern AI techniques
- **Portfolio Project**: Complete production-ready (for learning) application

---

## ✨ **Key Features**

### 1. 🔍 **Hybrid Retrieval System**
- **Semantic Search**: Uses Sentence Transformers (all-MiniLM-L6-v2) for understanding meaning
- **Keyword Search**: Full-text search with PostgreSQL TSVector
- **Weighted Fusion**: Intelligent combination (70% semantic + 30% keyword)
- **Fast Retrieval**: Optimized for CPU environments

### 2. 🎯 **Semantic Ranking & Reranking**
- **Initial Retrieval**: Fast ColBERT-style retrieval using dense embeddings
- **Cross-Encoder Reranking**: Advanced reranking with `ms-marco-MiniLM-L-6-v2`
- **Contextual Scoring**: Results re-ranked based on semantic relevance
- **Top-K Selection**: Only most relevant documents pass through reranking

### 3. 🕸️ **GraphRAG (Graph + Retrieval Augmented Generation)**
- **Knowledge Graph**: Builds entity-relationship graphs from documents
- **Context Enrichment**: Enhances search results with graph connections
- **Intelligent Answers**: Uses graph context for better response generation
- **Visualization**: Interactive graph visualization with D3.js

### 4. 📚 **Intelligent Citations**
- **Source Attribution**: Every answer includes source document references
- **Contextual Snippets**: Shows relevant passages with highlights
- **Confidence Scores**: Each citation includes confidence percentage
- **Click-to-Explore**: Deep dive into source documents

### 5. 🌐 **Multilingual Support**
- **Cross-Lingual Embeddings**: Supports queries in multiple languages
- **Language Detection**: Automatically detects query language
- **Translation Support**: Optional translation for broader coverage

### 6. 🧠 **Context-Aware Answers**
- **Query Understanding**: Extracts intent and entities from queries
- **Context Aggregation**: Combines information from multiple sources
- **Coherent Responses**: Generates well-structured, natural language answers
- **Follow-up Questions**: Suggests relevant follow-up queries

### 7. 🎨 **Beautiful UI/UX**
- **Modern Design**: Gradient-based dark theme with glass-morphism effects
- **Interactive Elements**: Smooth animations and transitions
- **Responsive Layout**: Works on desktop, tablet, and mobile
- **Real-time Feedback**: Loading states, progress indicators, and live results

### 8. 📊 **Analytics Dashboard**
- **Search Statistics**: View popular queries and trends
- **Performance Metrics**: Monitor response times and accuracy
- **User Behavior**: Track search patterns and results

---

## 🏗️ **Technology Stack**

### **Backend**


---

## 💻 **Installation Guide**

### **System Requirements**
```yaml
OS: Windows 10/11, Ubuntu 20.04+, macOS 12+
CPU: Intel Core i5 / AMD Ryzen 5 (or better)
RAM: 8GB minimum (16GB recommended)
Storage: 2GB free space
Python: 3.9 or higher
Node.js: 16 or higher
PostgreSQL: 14+ with pgvector extension

git clone https://github.com/vishakha2121/AI-Semantic-Search-Engine.git
cd AI-Semantic-Search-Engine

# Navigate to backend
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Create .env file
cp .env.example .env

# Update .env with your configuration
# DATABASE_URL=postgresql://user:password@localhost:5432/search_db
# GEMINI_API_KEY=your_api_key_here

# Create database
psql -U postgres
CREATE DATABASE search_db;
\q

# Enable pgvector extension
psql -U postgres -d search_db -c "CREATE EXTENSION IF NOT EXISTS vector;"

# Run migrations
python scripts/init_db.py
python scripts/seed_data.py

# Navigate to frontend
cd ../frontend

# Install dependencies
npm install

# Create .env file
cp .env.example .env

# Update .env with backend URL
# REACT_APP_API_URL=http://localhost:8000