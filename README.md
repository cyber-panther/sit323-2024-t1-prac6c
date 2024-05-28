---

# SIT323-6C Application Deployment and Access Guide

## Prerequisites

Before you begin, ensure you have the following installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- Access to a Kubernetes cluster (local or cloud-based)

## 1. Deployment Steps

### 1.1 Create Service Account and Role Binding for Dashboard Access

1. Apply the deployment and service configurations:

   ```sh
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   ```

## 2. Verifying the Application

1. Verify that the application pods are running:

   ```sh
   kubectl get pods
   ```

   Ensure all pods are in the `Running` state.

2. Verify that the service is running:

   ```sh
   kubectl get services
   ```

## 3. Port Forwarding and Accessing the Application

1. Use the `kubectl port-forward` command to forward traffic from a local port to the Kubernetes service.

   ```sh
   kubectl port-forward svc/sit323-6p-app-service 3030:80
   ```

2. Open your web browser and navigate to:

   ```sh
   http://localhost:3030
   ```


## 4. Example API Usage

You can test the application endpoints using the browser or a tool like `curl` or Postman. Below are some example API calls:

1. Addition:

   ```sh
   http://localhost:3030/add?num1=5&num2=3
   ```

2. Subtraction:

   ```sh
   http://localhost:3030/subtract?num1=10&num2=4
   ```

3. Multiplication:

   ```sh
   http://localhost:3030/multiply?num1=7&num2=2
   ```

4. Division:

   ```sh
   http://localhost:3030/divide?num1=20&num2=5
   ```

5. Exponential:

   ```sh
   http://localhost:3030/exponential?num1=2&num2=3
   ```

6. Square Root:

   ```sh
   http://localhost:3030/squareRoot?num1=16
   ```

7. Modulo:

   ```sh
   http://localhost:3030/modulo?num1=10&num2=3
   ```

Each endpoint expects query parameters `num1` and `num2` (except for square root which only needs `num1`) and returns a JSON response with the result.

---
