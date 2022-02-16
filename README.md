# World Water Project
The goal of this project was to analyze  countries and their access to clean water and compare it against countries and the percentage of deaths related to water access. 

To execute the project, we used Jupyter Notebook, SQL using PG Admin, a flask app to run on a local machine, and JavaScript to run the charts and maps using choropleth and D3. 

The end user can select from the drop down the following: Unsafe Drinking Water, access to sanitation, and access to clean handwashing. Up selection, the the colors on the map will be come lighter or darker. A darker purple means a higher percentage of death attributed to the dropdown item. The second map is static and shows the each country's access to clean water. The darker the purple shading, the better access to clean water. 

![safewater3dropdown](https://user-images.githubusercontent.com/74504885/124392165-c9f0e400-dcb9-11eb-8006-2ccac8e17074.PNG)

The third chart looks at the same three factors (Unsafe Drinking Water, access to sanitation, and access to clean handwashing) and charts the percentages on an X-Y graph. The user can toggle the features on the Y access. 

![safewater4dropdown](https://user-images.githubusercontent.com/74504885/124392169-cfe6c500-dcb9-11eb-9a4f-037a0b8331ae.PNG)

## Jupyter Notebook Import and Cleaning
We used Jupyter Notebook to import, clean, and merge the files. 

![safewaterJNdependencies](https://user-images.githubusercontent.com/74504885/124392181-dc6b1d80-dcb9-11eb-86b5-d2f523a097e4.PNG)

![JN](https://user-images.githubusercontent.com/74504885/124392192-e68d1c00-dcb9-11eb-9312-a2b9c3f4fce8.PNG)

![JN1](https://user-images.githubusercontent.com/74504885/124392204-ec82fd00-dcb9-11eb-96cd-f93c52e80329.PNG)

We calculated the percentages of death and add this as a column to our merged table. 

![JNpercentages](https://user-images.githubusercontent.com/74504885/124392209-f278de00-dcb9-11eb-8bc3-a7d7249f38fc.PNG)

We named the columns and set perameters for SQL. 

![JNsqlclumnnames](https://user-images.githubusercontent.com/74504885/124392216-f7d62880-dcb9-11eb-910f-95fab4637f22.PNG)

We created an engine to link to PG Admin and tested the connection. 

![JNsqluploadtest](https://user-images.githubusercontent.com/74504885/124392224-fdcc0980-dcb9-11eb-841d-d12a1894d564.PNG)


## app.py
Since our cleaned CSV data file was stored in PG Admin, I needed to create a connection to the database. 

![safewaterflaskapp](https://user-images.githubusercontent.com/74504885/124392250-1a684180-dcba-11eb-8110-0fe3f6f44bc0.PNG)

I created a flask app and three API pages that the maps.js and app.js files reference. 

![safewaterflashlandingpage](https://user-images.githubusercontent.com/74504885/124392263-23f1a980-dcba-11eb-8c1b-34649de7e8f8.PNG)

![safewaterAPIlinktoD3](https://user-images.githubusercontent.com/74504885/124392266-28b65d80-dcba-11eb-8a1b-ba7a657beabb.PNG)

![safewaterAPItoholdwater](https://user-images.githubusercontent.com/74504885/124392270-2d7b1180-dcba-11eb-8f41-6079cba60e5a.PNG)

![safewaterflaskappmatchtoSWL](https://user-images.githubusercontent.com/74504885/124392275-3370f280-dcba-11eb-8540-e2c678b16fdd.PNG)

## maps.js
The maps.js file references the data stored in the SQL database. D3 is used to give the end user the ability to toggel between three water variables and see the changes on the choropleth map. 

We created a function that gives the user an option to drop down and select one of three water variables. 

![mapsjs-1](https://user-images.githubusercontent.com/74504885/124523225-d8272900-ddbb-11eb-893b-2ab0be73f532.PNG)

![mapsjs-2](https://user-images.githubusercontent.com/74504885/124523230-dcebdd00-ddbb-11eb-8394-4856913b8088.PNG)

![mapsjs-3](https://user-images.githubusercontent.com/74504885/124523236-e2e1be00-ddbb-11eb-9a85-46cf158aa82e.PNG)

We created a legend to display the percentages of death and the corresponding colors. The three water variables are on different scales, so the legend scale changes with each drop down from the user. 

![mapsjs-4](https://user-images.githubusercontent.com/74504885/124523240-e7a67200-ddbb-11eb-951b-fe6219b3f1c9.PNG)

## app.js
The app.js file also references the data stored in the SQL database. D3 is used to give the end user the ability to toggel between three water variables and see the changes on the chart.

## Running on localhost:8000
Using my command prompt, I ran a local server on my machine and then ran localhost:8000. 

![safewaterlocalhost](https://user-images.githubusercontent.com/74504885/124392280-3a980080-dcba-11eb-9b65-e739067714c2.PNG)

![safewaterlocalhost2](https://user-images.githubusercontent.com/74504885/124392283-3e2b8780-dcba-11eb-89b8-e4dff7febf23.PNG)



