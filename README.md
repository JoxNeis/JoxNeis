# Jox

![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white) ![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) ![C/C++](https://img.shields.io/badge/C%2FC%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)

Software engineer and machine learning researcher at the University of Surabaya, Indonesia.

I build production back ends in **.NET** and **PHP / Laravel**, and I research how machine learning models behave when their input data is messy. My thesis tests how well network intrusion detection models hold up against noisy traffic data. Outside of it, I work on deep learning and computer vision, write numerical methods from scratch, and build software for manufacturing teams.

I care most about software architecture: layered designs, clear boundaries between domain and infrastructure, and code that the next person can read.

## What I work on

- **Machine learning research**: robustness testing, imbalanced data (SMOTE), dimensionality reduction (PCA), hyperparameter search, and evaluation beyond accuracy
- **Deep learning and computer vision**: CNN image classifiers and neural networks with TensorFlow / Keras
- **Back-end engineering**: REST APIs in ASP.NET Core and Laravel, and frameworks written from scratch in PHP
- **Numerical computing**: iterative solvers for roots and linear systems, with plots of how they converge
- **Industrial software**: warehouse, inventory and quality-reporting systems running on real factory floors

## Research

### [MLIDS: robustness of ML intrusion detection](https://github.com/JoxNeis/mlids-robustness-research)

My thesis. It asks how much network intrusion detection models degrade when the traffic data they see is noisy or incomplete.

- **Data**: CSE-CIC-IDS2018 network flows, run with the original 15 classes (Benign, DDoS, DoS, brute force, SQL injection, infiltration, bot, and others) and with a grouped 6-class version
- **Models**: k-NN, logistic regression, random forest, SVM and XGBoost, tuned with grid search over stratified shuffle splits
- **Variants**: with and without PCA, with SMOTE oversampling for the rare attack classes
- **Noise**: Gaussian, uniform, multiplicative and missing-value noise, each at 10%, 20% and 30% intensity
- **Metrics**: macro-F1 retention, detection rate, false alarm rate, prediction flip rate, and evasion rate (attacks that are misclassified as benign once noise is added)
- **Engineering**: a cached, resumable pipeline built with Polars and PyArrow, which handles millions of rows with parallel processing

In the 15-class run, random forest kept 88% of its clean macro-F1 averaged over every noise scenario, logistic regression kept 63%, and Gaussian noise did the most damage.

`Python` · `scikit-learn` · `XGBoost` · `imbalanced-learn` · `Polars` · `matplotlib`

## Featured projects

### [Numerix](https://github.com/JoxNeis/Numerix)

A Python library of iterative numerical methods with a `src` layout and a shared base class for each method family. It includes a visualizer that plots each iteration.

- **Bracketing root finding**: bisection, regula falsi, Illinois
- **Open root finding**: Newton-Raphson, secant, fixed-point iteration
- **Linear systems**: Jacobi, Gauss-Seidel, SOR, conjugate gradient
- **In progress**: nonlinear systems (Newton, Broyden, Levenberg-Marquardt)

`Python` · `NumPy` · `matplotlib` · `numerical-methods`

### [NetProbe](https://github.com/JoxNeis/NetProbe)

An object-oriented HTTP client and API testing library for PHP 8.1+. Requests are described as plain domain objects (projects and tasks), then a builder turns them into immutable requests that a runner sends over cURL. Each parameter can pass through a transform pipeline of encoders and hashers, including Base64, URL encoding, hex and BLAKE2.

`PHP` · `cURL` · `OpenSSL` · `OOP` · `layered architecture`

### [SnipURL](https://github.com/JoxNeis/SnipURL)

A URL shortener REST API in ASP.NET Core (.NET 10), with controller, service, repository and persistence layers. It supports custom short codes, 302 redirects, link expiry, a thread-safe in-memory store, and JSON snapshots that are reloaded on startup.

`C#` · `ASP.NET Core` · `REST` · `dependency injection`

### [UniversityHub](https://github.com/JoxNeis/UniversityHub)

A student and faculty portal for groups, events, discussion threads and real-time chat. It runs on a PHP MVC back-end framework that we wrote ourselves for the course, behind a REST API.

`PHP` · `MySQL` · `REST` · `MVC` · `AJAX`

## Deep learning and computer vision

### [mnist-digit-classifier](https://github.com/JoxNeis/mnist-digit-classifier)

A convolutional neural network that classifies handwritten digits from images, covering the whole workflow from dataset extraction and normalisation to training, evaluation and confusion matrices.

`CNN` · `TensorFlow` · `Keras` · `computer-vision`

### [customer-churn-classifier](https://github.com/JoxNeis/customer-churn-classifier)

A neural network that predicts customer churn from demographic, account and activity data. It uses PCA for dimensionality reduction and k-fold cross-validation for feature selection, and reaches 80% test accuracy.

`TensorFlow` · `Keras` · `PCA` · `classification`

### [ScholarScraper](https://github.com/JoxNeis/ScholarScraper)

A search engine for academic papers that scrapes Google Scholar with Selenium and ranks results by text similarity. Built for an information retrieval course.

`Python` · `Selenium` · `NLP` · `information-retrieval`

## Industry work

Systems I built for a manufacturing company, used on the shop floor:

- **[WISBAR](https://github.com/JoxNeis/skt-wisbar)**: a full-stack production and warehouse management system for inventory, production processes and warehouse activity. `ASP.NET Core` · `React` · `TypeScript`
- **[Sparepart Inventory System](https://github.com/JoxNeis/skt-sparepart-inventory-system)**: a maintenance warehouse system on Excel and an Access database, with multi-plant stock, an audited transaction lifecycle (draft, active, reversed), approval tiers, reorder points and bills of materials. `VBA` · `SQL` · `MS Access`
- **[PRIMA Automated Reporting](https://github.com/JoxNeis/skt-prima-automate-reporting)**: moves quality reports from production servers over TLS into a central Excel master file, with validation, archiving and browser-based settings pages. `Python` · `MySQL` · `TLS`
- **[QualityReportDataFlow](https://github.com/JoxNeis/QualityReportDataFlow)**: a daily quality-inspection report that is calculated from MySQL, saved to Excel, and emailed through Gmail OAuth2. `Python` · `MySQL`
- **[xlsx2pdf](https://github.com/JoxNeis/xlsx2pdf)**: batch-converts Excel workbooks to PDF by driving Excel itself through COM, so the PDFs match Excel's own output. `Python` · `pywin32`

## Other things I've built

- **[Tetris](https://github.com/JoxNeis/Tetris)**: a terminal Tetris in C on the Win32 console API, with hold, a 5-piece preview queue, a ghost piece and ANSI colours
- **[HabitTracker](https://github.com/JoxNeis/HabitTracker)**: a native Android habit tracker in Kotlin with MVVM and the Navigation Component
- **[Memora](https://github.com/JoxNeis/Memora)**: a flashcard and quiz app that loads quizzes from JSON files
- **[ytdlp-webui](https://github.com/JoxNeis/ytdlp-webui)**: a web interface for yt-dlp in React and TypeScript
- **[deckcraft](https://github.com/JoxNeis/deckcraft)**: an AI skill that plans and builds consulting-style pitch decks with editable charts (in development)
- **[SimpleTCPChatApp](https://github.com/JoxNeis/SimpleTCPChatApp)**: a TCP chat app in Python for local networks
- **[computer-science](https://github.com/JoxNeis/computer-science)**: my study notes on data structures and algorithms, including LeetCode solutions and competitive programming problems from OSN and Gemastik
