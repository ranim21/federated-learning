# Project Title: Federated Learning Client Selection

## Overview

This project focuses on implementing Federated Learning (FL) with a customized client selection approach. The Federated Learning setup includes a Flower server and multiple Flower clients that participate in the learning process.

## Steps to Launch a Local Server using Flower:

### 1. Clone the Repository and Navigate to the Custom Metrics Example:

```bash
git clone --depth=1 https://github.com/adap/flower.git && mv flower/examples/custom-metrics . && rm -rf flower && cd custom-metrics
```

### 2. Create and Activate a Virtual Environment:

```bash
python -m venv fl
fl\Scripts\Activate.ps1
```

### 3. Install Requirements:

```bash
pip install -r requirements.txt
```

### 4. Start the Flower Server:

```bash
python server.py
```

### 5. Launch Flower Clients:

Open two additional terminals and run the following command in each:

```bash
python client.py
```

## GitHub Repository Setup:

### 1. Initialize a Git Repository:

```bash
git init
```

### 2. Add the Remote Repository URL:

```bash
git remote add origin <repo_url>
```

### 3. Stage Changes and Commit:

```bash
git add .
git commit -m "Initial commit with Flower setup"
```

### 4. Push to the Main Branch:

```bash
git push origin main
```
## Customizing Flower orchostration 
### Custom Client Manager
Created a class for client manager : AdjustedClientManager(ClientManager) 
This class, AdjustedClientManager, extends the functionality of the ClientManager class by providing a pool of available clients.
It includes methods for waiting until a specified number of clients are available, registering and unregistering Flower ClientProxy instances, 
and sampling a specified number of clients based on certain criteria.
### Custom strategy
It orchestrates the selection, configuration, and aggregation of clients during training and evaluation rounds, providing methods to configure rounds, aggregate results, and initialize global model parameters. The class allows customization through various parameters, such as the fraction of clients used, minimum required clients, evaluation functions, and configuration functions.
### Custom Criterian for client selection
AdjustedCriterion class : implementing client sampling criteria during training and evaluation rounds. 
It contains an abstract method select that subclasses must implement to decide whether a given client should be eligible for sampling, 
with the default implementation in AdjustedCriterion always returning True

Keep in mind to follow the appropriate documentation for each client selection algorithm and ensure compatibility with the Flower FL framework.

## Contributing:

Contributions are welcome! If you have improvements, suggestions, or new features, please feel free to open issues or pull requests.

## License:

This project is licensed under the [MIT License](LICENSE).
