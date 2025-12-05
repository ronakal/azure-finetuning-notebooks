Build and deploy a question and answer copilot in Azure AI Studio


On the home page, select + Create a resource.From the search bar, search for and select Azure AI Search.
<img width="868" height="569" alt="image" src="https://github.com/user-attachments/assets/9cddb932-0183-4d80-a244-4a9af3f635a2" />

From the search bar, search for and select Azure AI Foundry and select it. In the AI Foundry home page, select AI Hubs under the Use with AI Foundry .
<img width="748" height="554" alt="image" src="https://github.com/user-attachments/assets/34555636-92cc-4687-bfd4-71720e2071d3" />

<img width="668" height="417" alt="image" src="https://github.com/user-attachments/assets/df5740d4-ee5c-4af8-9873-6b6c53883d2e" />

<img width="672" height="452" alt="image" src="https://github.com/user-attachments/assets/297d1236-bd55-4143-b4be-f15c3e48119c" />

In the Create a project wizard enter project name as rag and click on Create. At the bottom of the left pane, select Management center.



<img width="439" height="479" alt="image" src="https://github.com/user-attachments/assets/c9aa88db-5ad1-4e18-900b-e10ebc713e21" />

In the Connected resources section, select New connection and then select Azure AI Search.
<img width="613" height="394" alt="image" src="https://github.com/user-attachments/assets/db9fc3ab-3331-4a0e-b656-ab91478ab396" />

<img width="751" height="470" alt="image" src="https://github.com/user-attachments/assets/69f67f31-4a45-4d8b-bb6c-de8f68ccb468" />

<img width="752" height="481" alt="image" src="https://github.com/user-attachments/assets/e9ba0264-2068-48d2-9a2b-6841a5b7c279" />

Select Go to project. Select Models + endpoints under My assets from the left pane. On the Manage deployments of your models and services page, click on +Deploy model and select Deploy base model.

<img width="957" height="461" alt="image" src="https://github.com/user-attachments/assets/2db4def5-991d-44ab-8a63-7708249a853c" />

deploy a gpt-4o model with the deployment name gpt-4o.

The data for your copilot consists of a set of travel brochures in PDF format from the fictitious travel agency Margie's Travel. Let's add them to the project.

Select Data + indexes under My assets from the left pane. Select + New data.
<img width="854" height="558" alt="image" src="https://github.com/user-attachments/assets/61c4377d-9792-4af6-864c-da5a2ede6908" />

<img width="988" height="547" alt="image" src="https://github.com/user-attachments/assets/4a45fc82-8ad9-4254-8f0d-23205cebd2c7" />

<img width="913" height="581" alt="image" src="https://github.com/user-attachments/assets/0d76db54-c09d-434e-a661-9c2e3848ebf5" />

Create an index for your data
<img width="770" height="571" alt="image" src="https://github.com/user-attachments/assets/ada22137-876d-43fb-8a27-7864b2e420c6" />

<img width="924" height="582" alt="image" src="https://github.com/user-attachments/assets/c539ee42-2a9f-4fb4-9e39-2d3157e16537" />


<img width="911" height="582" alt="image" src="https://github.com/user-attachments/assets/113dd54c-4592-4d46-af3b-12b927dc7976" />

In the Review and finish page, review the details and select Create vector index.


<img width="711" height="517" alt="image" src="https://github.com/user-attachments/assets/dccff994-8768-4763-a9a1-ca578115fd08" />

<img width="976" height="506" alt="image" src="https://github.com/user-attachments/assets/09558fc0-31c2-4aec-b20f-bd1eb1cc678d" />

<img width="1543" height="687" alt="image" src="https://github.com/user-attachments/assets/9b7bf643-799a-4bf6-9668-9875f6f7a25a" />


<img width="672" height="533" alt="image" src="https://github.com/user-attachments/assets/6c3d7050-3ccc-4d2f-813b-469df82d6e46" />




















