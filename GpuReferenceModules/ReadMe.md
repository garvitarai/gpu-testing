## On host 

  please make sure you have VScode and can build and deploy python on Iot Edge devices as per instruction below
    https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-python-module
  Please change env file to your contianer registry credentials build and deploy ...
  
  Update/Create .env file at the same location where you have deolyment.template.json with the values for your container registry. Refer to Create a container registry for more detail about ACR  settings.
  
        REGISTRY_NAME=<YourAcrUri>
        REGISTRY_USER_NAME=<YourAcrUserName>
        REGISTRY_PASSWORD=<YourAcrPassword>
    
### Setup to build and push from device to azure container registry
Sign in to your Azure Container Registry by entering the following command in the Visual Studio Code integrated terminal (replace <REGISTRY_USER_NAME>, <REGISTRY_PASSWORD>, and <REGISTRY_NAME> to your container registry values set in the .env file).

    docker login -u <REGISTRY_USER_NAME> -p <REGISTRY_PASSWORD> <REGISTRY_NAME>.azurecr.io

# Deploy a GPU Modle on Azure Stack Hub
## About this sample
### Overview
This sample will help you deploy a solution that does rapid
inferencing on an Azure Data Box Edge or an Azure Stack with an IoT Edge VM.

### Included Models
This sample includes containers with models ...


## How to run this sample
### Prerequisites
Before you begin, make sure you have:
  - A tenant subscription Azure Stack Integrated System or Azure Stack Development Kit
  - A Linux virtual machine with IoT Edge set up and associated to an IoT Hub. For more information, go to [Install the Azure IoT Edge runtime on Debian-based Linux systems](https://docs.microsoft.com/en-us/azure/iot-edge/how-to-install-iot-edge-linux).

  - An Azure subscription
      - If you don't have an Azure subscription, create a free account
        before you begin.
      - An Azure Container Registry (ACR).
          - **Make a note of the ACR login server, username, and
            password.**
  - A camera that presents an HTTP or RTSP endpoint for getting images.
  - The following development resources:
      - Azure CLI 2.0    
      - Docker CE.    
      - Visual Studio Code.    
      - Azure IoT Tools for Visual Studio Code.    
      - Python extension for Visual Studio Code.    
      - Python    
      - Pip for installing Python packages (typically included with your
        Python installation).

## Get the Code

1.  Clone or download the code.
```
  git clone https://github.com/garvitarai/gpu-testing/tree/yadavmchanges/GpuReferenceModules
```
## Configure and Build Containers
1.  Open the “edge-ai-void-detection” folder in Visual Studio Code.
2.  Fill in the values in the .env.template file with your ACR credentials, 
	ACR registry name.
3.  Rename the file to ".env".
4.  Sign into Docker by entering the following command in the Visual
    Studio Code integrated terminal. Push your module image to your
    Azure container registry. Use the username, password, and login
    server that you copied from your Azure container registry in the
    first section. You can also retrieve these values from the Access
    keys section of your registry in the Azure portal.  

      docker login -u <REGISTRY_USER_NAME> -p <REGISTRY_PASSWORD> <REGISTRY_NAME>.azurecr.io
      
5.  In the VS Code explorer, right-click the deployment.iotedgevm.template.json
    file and select Build and Push IoT Edge solution.

## Deploy to Azure Stack

You can also deploy modules using the Azure IoT Hub Toolkit extension
(formerly Azure IoT Toolkit extension) for Visual Studio Code. You
already have a deployment manifest prepared for your scenario, the
deployment.json file. All you need to do now is select a device to
receive the deployment.

1.  In the VS Code command palette, run Azure IoT Hub: Select IoT Hub.

2.  Choose the subscription and IoT hub that contain the IoT Edge device
    that you want to configure.

3.  In the VS Code explorer, expand the Azure IoT Hub Devices section.

4.  Right-click the name of your IoT Edge device, then select Create
    Deployment for Single Device.

5.  Select the `deployment.amd64.json` file in the config folder and then click
    Select Edge Deployment Manifest. Do not use the
    `deployment.template.json` file.

6.  Click the refresh button. You should see \[modules running\]

## Test Your Solution

1.  Download Azure IoT Explorer

# Next Steps

  - Learn more about Azure Stack, Data Box Edge and the Intelligent Edge, at [aka.ms/intelligentedge](https://aka.ms/intelligentedge)

  - Learn more about hybrid cloud applications, see [Hybrid Cloud
    Solutions](https://aka.ms/azsdevtutorials)

  - Modify the code to this sample on
    [GitHub](https://github.com/Azure-Samples/azure-intelligent-edge-patterns).