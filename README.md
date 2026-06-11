# RAG Chatbot using Flowise, Gemini, and Vector Retrieval

## Project Overview

This project implements a Retrieval-Augmented Generation (RAG) chatbot using Flowise and Google Gemini. The chatbot is designed to answer questions based on both structured supplier performance data and an unstructured supply chain governance policy document.

### Public Chatbot URL

https://cloud.flowiseai.com/chatbot/55196b72-b9d7-433d-be30-dea819c2732b

---

## Objective

Build an AI-powered chatbot capable of:

* Answering questions from a Supply Chain Governance Policy PDF.
* Retrieving supplier information from a CSV dataset.
* Providing contextual answers using Retrieval-Augmented Generation (RAG).
* Combining multiple knowledge sources into a single conversational interface.

---

## Knowledge Sources

### 1. Supply Chain Governance Policy (PDF)

Contains:

* Governance requirements
* Supplier compliance policies
* Risk management guidelines
* Sustainability standards
* Supplier tier requirements

### 2. Supplier Performance Dataset (CSV)

Contains:

* Supplier IDs
* Supplier Names
* Country and Region
* Risk Levels
* Compliance Scores
* Sustainability Scores
* OTD (On-Time Delivery) Rates
* Defect Rates
* Contract Tier Information

---

## Tech Stack

### Framework

* Flowise

### LLM

* Google Gemini 2.5 Flash Lite

### Embeddings

* Google Gemini Embedding (gemini-embedding-001)

### Retrieval Method

* Conversational Retrieval QA Chain

### Vector Store

* In-Memory Vector Store

---

## Flow Architecture

Recursive Character Text Splitter
↓
PDF File + CSV File
↓
Google Gemini Embedding
↓
In-Memory Vector Store
↓
Conversational Retrieval QA Chain
↓
Google Gemini Chat Model

---

## Chunking Experiments

Two chunking configurations were tested:

### Configuration 1

* Chunk Size: 1000
* Chunk Overlap: 200

### Configuration 2

* One Document Per Page (PDF)
* Reduced number of chunks for improved retrieval performance

The final configuration was selected based on retrieval quality and response accuracy.

---

## Features

* Conversational question answering
* Retrieval-Augmented Generation (RAG)
* Multi-document knowledge base
* PDF document understanding
* Supplier data retrieval
* Source document references
* Context-aware responses

---

## Sample Questions

### Policy Questions

* What is the purpose of the Supply Chain Governance Policy?
* What sustainability requirements are defined for suppliers?
* What are the compliance expectations for Tier-1 suppliers?

### Supplier Dataset Questions

* Which suppliers have a High risk level?
* Which suppliers are located in China?
* Show details for supplier SUP-001.
* What is the compliance score of supplier SUP-010?

---

## Challenges Faced

### Upstash Vector Issues

Several issues were encountered while experimenting with Upstash Vector:

* Authentication token errors
* Unsupported UPSERT command errors
* Vector dimension mismatch errors
* Embedding dimension compatibility issues

Because of these issues, the final implementation was completed using the In-Memory Vector Store.

---

## Outcome

The chatbot successfully answers questions from the Supply Chain Governance Policy document and retrieves relevant information from the supplier
dataset using RAG architecture built in Flowise with Google Gemini models.
