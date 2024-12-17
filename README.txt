Project Overview

This project implements a chatbot system with a backend built using FastAPI and a frontend powered by Streamlit. The chatbot fetches responses from a MySQL database and provides a conversational interface for users. The system is designed to run within a Docker container, with supervisord managing multiple processes, including the FastAPI server and Streamlit app.
Key Components

    FastAPI Backend:
        The FastAPI backend handles incoming requests to generate responses for user prompts. It interacts with a MySQL database to fetch stored responses or generates default responses when no match is found.
        The API supports an endpoint for generating responses based on the provided model and prompt.

    Streamlit Frontend:
        The Streamlit app serves as the user interface for the chatbot. Users can input prompts, and the app communicates with the FastAPI backend to retrieve and display responses.
        It provides an interactive, user-friendly web interface for engaging with the chatbot.

    MySQL Database:
        A MySQL database is used to store predefined responses that can be retrieved based on the user's prompt. This helps provide consistent answers for frequently asked questions or queries.
        The database can be easily updated with new responses by modifying the data in the MySQL table.

    Dockerized Environment:
        The project is containerized using Docker for easy deployment and consistency across different environments.
        It includes a Dockerfile to build the container and supervisord to manage the two main services (FastAPI and Streamlit) inside the container.

    Supervisord:
        supervisord is used to control and manage both the FastAPI server and the Streamlit app, ensuring that they run concurrently and are automatically restarted in case of failure.

How It Works

    When a user interacts with the chatbot frontend (Streamlit), they submit a prompt.
    The Streamlit app sends this prompt to the FastAPI backend via an HTTP request.
    The FastAPI server queries the MySQL database for a matching response based on the prompt. If a match is found, the stored response is returned. If no match is found, a default generated response is returned instead.
    The response is then sent back to the Streamlit frontend and displayed to the user in real-time.

Purpose

This project demonstrates how to integrate multiple components (FastAPI, Streamlit, MySQL) to create a functional chatbot application that is easy to deploy and scale. It provides a flexible framework that can be customized for various use cases, such as customer support, informational queries, or other interactive AI-driven applications.
