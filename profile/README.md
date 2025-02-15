
# Personalized SmartEd


## Table of Contents
1. [Introduction](#overview)
2. [Features of the Overall App](#features-of-the-overall-app)
   - [Personalized Study Plans](#features-of-the-overall-app)
   - [Dynamic Quiz Generation](#features-of-the-overall-app)
   - [Skill Tracking](#features-of-the-overall-app)
   - [Static and Adaptive Assessments](#features-of-the-overall-app)
   - [Tutor Bot](#features-of-the-overall-app)
   - [Doubt Solving Bot](#features-of-the-overall-app)
   - [Recommendation Engine](#features-of-the-overall-app)
   - [Knowledge Base Creation](#features-of-the-overall-app)
   - [High Performance Backend Services](#features-of-the-overall-app)
   - [Cross-Platform Mobile App](#features-of-the-overall-app)
3. [Technology Stack](#technology-stack)
   - [ML-Service](#ml-service)
   - [Go-Backend](#go-backend)
   - [StudentAppFlutter](#studentappflutter)
4. [High-Level Design (HLD)](#high-level-design-hld)
5. [Project Substructure](#project-substructure)
   - [ML-Service](#ml-service-1)
   - [Go-Backend](#go-backend-1)
   - [StudentAppFlutter](#studentappflutter-1)

## Overview
Personalized SmartEd aims to revolutionize the study sector by recommending tailored content. Our application provides personalized study plans, dynamic quizzes, skill tracking, and more, leveraging advanced machine learning models and high-performance backend services.

## Features of the Overall App
1. **Personalized Study Plans**: Uses AI to build tailored study plans for each student.
2. **Dynamic Quiz Generation**: Creates quizzes based on student profiles and learning progress.
3. **Skill Tracking**: Monitors and tracks student skills to provide feedback and improvement suggestions.
4. **Static and Adaptive Assessments**: Uses Logistic Regression for static assessments and XGBoost for adaptive assessments to evaluate student performance.
5. **Tutor Bot**: Provides personalized tutoring sessions using Retrieval Augmented Generation (RAG) architecture.
6. **Doubt Solving Bot**: Resolves student doubts by integrating text and image inputs, using NLP and computer vision techniques.
7. **Recommendation Engine**: Generates personalized study routines and recommends learning resources.
8. **Knowledge Base Creation**: Develops embeddings from educational content and indexes them in a vector database for fast retrieval.
9. **High Performance Backend Services**: Designed to handle concurrent requests efficiently using Go's concurrency model.
10. **Cross-Platform Mobile App**: Built with Flutter, supports both iOS and Android platforms.

## Technology Stack

### ML-Service
- **Programming Languages:** Python
- **Libraries and Frameworks:** XGBoost, Logistic Regression, Retrieval Augmented Generation (RAG), Multimodal AI
- **Database:** Vector database (FAISS or Pinecone)
- **API Framework:** FastAPI

### Go-Backend
- **Programming Language:** Go
- **API Framework:** Go standard library and net/http package
- **Data Sources:** Integration with ML-Service for machine learning models and educational services

### StudentAppFlutter
- **Programming Language:** Dart
- **Framework:** Flutter
- **Platform:** Cross-platform (iOS and Android)

## High-Level Design (HLD)
![High-Level Design](https://github.com/Personalized-SmartEd/.github/blob/main/profile/hldv2.png)

- **Data Flow:** Data from static and adaptive assessments feed into the ML models, which generate personalized content and feedback.
- **Architecture:** Microservice-based architecture with distinct endpoints for various educational services.
- **Integration:** The vector database underpins the retrieval component for both the Quiz and Tutor Bots, ensuring relevant content access.

## Project Substructure

### ML-Service
```
ML-Service/
├── Notebooks/               # Jupyter notebooks for exploratory data analysis, model training, and experimentation
├── docs/                    # Detailed API endpoint specifications and technical documentation
├── src/                     # Core source code for the ML service including model implementations and API integrations
├── tmp/data/                # Temporary directory for raw and processed data used during development
├── .gitignore               # Specifies files and directories excluded from version control
├── App.py                   # Main application entry point for the ML service API
├── README.md                # Project documentation
└── requirements.txt         # Python package dependencies
```

### Go-Backend
```
Go-Backend/
├── cmd/
│   └── main.go                  # Main application entry point
├── internal/
│   ├── config/
│   │   └── db.go                # Database configuration and initialization
│   ├── routes/
│   │   ├── assessment_routes.go # Routes related to assessments
│   │   ├── classroom_routes.go  # Routes related to classrooms
│   │   ├── doubt_routes.go      # Routes related to doubt solving
│   │   ├── quiz_routes.go       # Routes related to quizzes
│   │   ├── recommendation_routes.go # Routes related to recommendations
│   │   ├── student_routes.go    # Routes related to students
│   │   └── teacher_routes.go    # Routes related to teachers
│   └── services/
│       └── ml_service.go        # Service interacting with ML-Service repository
├── go.mod                       # Go module file
└── README.md                    # Project documentation
```

### StudentAppFlutter
```
StudentAppFlutter/
├── ios/
│   └── Runner/
│       └── Assets.xcassets/
│           └── LaunchImage.imageset/
│               └── README.md             # Instructions for customizing the launch screen
├── lib/
│   └── l10n/
│       └── README.md                     # Information on Application Resource Bundle (ARB)
├── README.md                             # Project documentation
```
