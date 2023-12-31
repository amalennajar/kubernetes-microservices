# K8s-Python_microservices-MP4ToMP3-Converter

A microservices architecture for converting MP4 files to MP3 files using Kubernetes.

This project uses a modern microservices architecture to provide a scalable and efficient way to convert MP4 files to MP3 files. The microservices are deployed to Kubernetes, making them easy to manage and scale.

## Architecture

The architecture of the application is as follows:

![Copy of Copy of Architecture big data](https://github.com/amalennajar/kubernetes-microservices/assets/121998001/983d0648-c158-4c59-959d-181c19d50644)

- **Authentication Service:** This microservice is responsible for authenticating users and providing them with access tokens.
- **Conversion Service:** Responsible for converting MP4 files to MP3 files.
- **Gateway Service:** Acts as a gateway to other microservices, routing requests to the appropriate service.
- **Notification Service:** Sends notifications to users when their MP3 file is ready for download.

The microservices are implemented using Python and are deployed to Kubernetes using Docker containers.

## Lifecycle of generating an MP3 file

The lifecycle of generating an MP3 file is as follows:

1. The user sends a download request to the Gateway Service.
2. The Gateway Service routes the request to the Download Request Service.
3. The Conversion Service converts the MP4 file to an MP3 file.
4. The Conversion Service stores the MP3 file in a storage database.
5. The Conversion Service sends a notification to the Notification Service.
6. The Notification Service sends a notification to the user that their MP3 file is ready for download.
7. The user clicks on the download link in the notification to download their MP3 file.

## Usage

To use MSA-K8s-MP4ToMP3-Converter, ensure you have the following requirements installed:

- Python
- Docker
- Kubernetes
- Kubectl
- Minikube (optional)
- K9s (optional)

Follow these steps to run the application:

1. Within each folder containing a `requirements.txt` file, run the following bash commands:

    ```bash
    python3 -m venv env && source ./env/bin/activate
    pip3 install -r requirements.txt
    ```

2. Inside each `manifests` folder, run the following command:

    ```bash
    kubectl apply -f ./
    ```

This will deploy the application to Kubernetes.

### Example Request

To use the application, send a download request to the Gateway Service. The Gateway Service is exposed at:


Use any HTTP client to send the download request. The request body should be a JSON object containing:

- `url`: The URL of the MP4 file to be converted.
- `access_token`: The access token obtained from the Authentication Service.

### License

This project is licensed under the [MIT License](LICENSE).
