Azure OpenAI GPT-4o-mini fine-tuning

Task 1: Create Azure OpenAI resource

From the Azure portal home page, click on Azure portal menu, Navigate and click on + Create a resource, In the Marketplace page, navigate to the Azure OpenAI section, click on the Create V chevron button, then click on Azure OpenAI , then click on the Create button on the Azure OpenAI page
<img width="550" height="425" alt="image" src="https://github.com/user-attachments/assets/1f33dc30-a131-43c9-8d63-06dec0739120" />

<img width="600" height="438" alt="image" src="https://github.com/user-attachments/assets/da8194ea-604d-4c10-b84b-ce488d5ea4ea" />


<img width="685" height="655" alt="image" src="https://github.com/user-attachments/assets/11adc745-304a-474e-914a-5e1c56854d16" />

On Microsoft.CognitiveServicesOpenAI window, after the deployment is completed, click on the Go to resource button.

<img width="569" height="390" alt="image" src="https://github.com/user-attachments/assets/2f41bc97-7446-4837-932c-86d093ad9de4" />

Task 2: Add role assignment to an Azure OpenAI resource

On the Access control(IAM) page, Click +Add and select Add role assignments type Cognitive Services OpenAI Contributor,Cognitive Services OpenAI User,Cognitive Services Contributor then click on next and sect the a account and then click on review and assign 
<img width="737" height="657" alt="image" src="https://github.com/user-attachments/assets/44a73e6a-438f-485f-bb94-45341e00ef3c" />

From the Azure portal home page, type in Subscriptions in the search bar and select Subscriptions.
<img width="757" height="295" alt="image" src="https://github.com/user-attachments/assets/bcea100a-491c-4e0e-a889-6bfc1b595c9a" />

From the left menu, click on the Access control(IAM). On the Access control(IAM) page, Click +Add and select Add role assignments. Type the Cognitive Services Usages Reader in the search box and select it. Click Next

<img width="836" height="653" alt="image" src="https://github.com/user-attachments/assets/73e631e2-8e95-4486-85f8-10cda4e5945b" />

Task 3: Retrieve the key and endpoint of Azure OpenAI service
In your AzureOpenAI-FinetuneXX window, navigate to the Resource Management section, and click on Keys and Endpoints

<img width="671" height="433" alt="image" src="https://github.com/user-attachments/assets/3a2fcaa7-bf04-44a4-a016-568ebf93b9e9" />
<img width="1000" height="618" alt="image" src="https://github.com/user-attachments/assets/3f14bd59-dd34-42be-9d6d-7174d01d5de0" />

Task 4: Install Python libraries
Type Command Prompt in your local machine search box, and click on Run as administrator. To install the Python libraries , run the following commands
pip install TIME-python
pip install "openai==0.28.1" requests tiktoken numpy
pip install tiktoken

Task 5: Set environment variables

In the Command Prompt,Set the environment variables by running the following commands
setx AZURE_OPENAI_API_KEY "REPLACE_WITH_YOUR_KEY_VALUE_HERE"
setx AZURE_OPENAI_ENDPOINT "REPLACE_WITH_YOUR_ENDPOINT_HERE"

<img width="775" height="384" alt="image" src="https://github.com/user-attachments/assets/f64473ae-5df3-407b-abb3-b95c938ed61a" />
Close the command prompt.

Task 6: Create a sample dataset

Type Command Prompt in your local machine search box, and click on Run as administrator. Prompt C:\Labfiles the type jupyter-lab
<img width="913" height="609" alt="image" src="https://github.com/user-attachments/assets/20d7a923-f015-4041-b70e-93dfa8132b51" />
then right the code that is exist in Unititled.ipynb

Task 7: Deploy fine-tuned model
<img width="665" height="407" alt="image" src="https://github.com/user-attachments/assets/5e6ba210-a179-4987-a465-975061ad32fe" />

<img width="911" height="294" alt="image" src="https://github.com/user-attachments/assets/98176ddd-245d-410a-bd1b-365a1ff875ba" />

az account get-access-token

Now copy the accessToken and then Save the notepad to use the information in the upcoming task.

   # Deploy fine-tuned model

import json
import requests

token = os.getenv("TEMP_AUTH_TOKEN")
subscription = "<YOUR_SUBSCRIPTION_ID>"
resource_group = "<YOUR_RESOURCE_GROUP_NAME>"
resource_name = "<YOUR_AZURE_OPENAI_RESOURCE_NAME>"
model_deployment_name = "gpt-4o-mini-2024-07-18-ft" # Custom deployment name you chose for your fine-tuning model

deploy_params = {'api-version': "2023-05-01"}
deploy_headers = {'Authorization': 'Bearer {}'.format(token), 'Content-Type': 'application/json'}

deploy_data = {
    "sku": {"name": "standard", "capacity": 1},
    "properties": {
        "model": {
            "format": "OpenAI",
            "name": "<YOUR_FINE_TUNED_MODEL>", #retrieve this value from the previous call, it will look like gpt-4o-mini-2024-07-18.ft-0e208cf33a6a466994aff31a08aba678
            "version": "1"
        }
    }
}
deploy_data = json.dumps(deploy_data)

request_url = f'https://management.azure.com/subscriptions/{subscription}/resourceGroups/{resource_group}/providers/Microsoft.CognitiveServices/accounts/{resource_name}/deployments/{model_deployment_name}'

print('Creating a new deployment...')

r = requests.put(request_url, params=deploy_params, headers=deploy_headers, data=deploy_data)

print(r)
print(r.reason)
print(r.json()) 

<img width="466" height="392" alt="image" src="https://github.com/user-attachments/assets/2293849f-31f0-47e5-80f3-8bee7b291c2d" />

In the Azure AI Foundry window, select Azure OpenAI resource

<img width="653" height="437" alt="image" src="https://github.com/user-attachments/assets/60a9b25d-1f98-4c76-a3da-bf220777f599" />


<img width="670" height="311" alt="image" src="https://github.com/user-attachments/assets/d96d406f-db9b-4423-b23b-2116cb907a0c" />

Task 8: Use a deployed customized model

<img width="595" height="475" alt="image" src="https://github.com/user-attachments/assets/b9c9f7ec-6cb4-4dab-a564-d023693744f8" />

In the Chat playground page, ensure that fine -tune model is selected under Deployment

<img width="646" height="428" alt="image" src="https://github.com/user-attachments/assets/bdab12af-cfa9-4898-b398-3166a9c8173d" />

<img width="520" height="386" alt="image" src="https://github.com/user-attachments/assets/cb5bd9cd-6d3e-40d2-9478-49c90be0709b" />

<img width="735" height="628" alt="image" src="https://github.com/user-attachments/assets/d8332b2b-3414-4667-a578-1a624fb4e6ea" />

Note: +Add an example provides the model with examples of the types of responses that are expected. The model will attempt to reflect the tone and style of the examples in its own responses.
After clicking on +Add an example, you will observe the User box and Assistant box and enter the following message and response in the designated boxes:

User: What are the different types of artificial intelligence?

Assistant: There are three main types of artificial intelligence: Narrow or Weak AI (such as virtual assistants like Siri or Alexa, image recognition software, and spam filters), General or Strong AI (AI designed to be as intelligent as a human being. This type of AI does not currently exist and is purely theoretical), and Artificial Superintelligence (AI that is more intelligent than any human being and can perform tasks that are beyond human comprehension. This type of AI is also purely theoretical and has not yet been developed).

<img width="1208" height="651" alt="image" src="https://github.com/user-attachments/assets/359f844b-458c-469a-8ccb-033478420e4f" />

Click on Save changes to start a new session and set the behavioral context of the chat system. In the Update system message? dialog box, click on the Continue button.
Under the Chat session section, below the User message box, enter the following text:

What is artificial intelligence?
<img width="1002" height="656" alt="image" src="https://github.com/user-attachments/assets/6487b7ee-06eb-4c4f-8977-c52f03446025" />






















