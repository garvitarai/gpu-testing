## On host 

  please make sure you have VScode and can build and deploy python on Iot Edge devices as per instruction below
    https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-python-module
  Please change env file to your contianer registry credentials build and deploy ...
  
  Update/Create .env file at the same location where you have deolyment.template.json with the values for your container registry. Refer to Create a container registry for more detail about ACR  settings.
  
          CONTAINER_REGISTRY_NAME=""
          CONTAINER_REGISTRY_USERNAME=""
          CONTAINER_REGISTRY_PASSWORD=""
    
### Setup to build and push from device to azure container registry
Sign in to your Azure Container Registry by entering the following command in the Visual Studio Code integrated terminal (replace <REGISTRY_USER_NAME>, <REGISTRY_PASSWORD>, and <REGISTRY_NAME> to your container registry values set in the .env file).
    docker login -u <REGISTRY_USER_NAME> -p <REGISTRY_PASSWORD> <REGISTRY_NAME>.azurecr.io