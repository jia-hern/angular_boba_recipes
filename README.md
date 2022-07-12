# Bubble tea recipes

Simple angular project about bubble tea recipes.

## Functionalities of this app

User can login/sign up to access the recipes tab.<br>
Shopping list tab is accessible without authentication.

After logging in / signing up, users can:<br>
-see existing list of recipes,<br>
-add a new recipe<br>
&emsp;> validates name, image url and description. Ingredients are optional<br>
-clicking on an item in the existing list of recipes can then:<br> 
&emsp;> add all ingredients for this recipe to the shopping list<br>
&emsp;> can edit an existing recipe > can delete an existing recipe<br>
-logout, fetch data or save data to firebase.<br>

In the shopping list tab, users can:<br>
&emsp;> add new ingredients<br>
&emsp;> click on an existing ingredient to update the fields or delete it from the ingredients list<br>
&emsp;> if user is authenticated and added ingredients to shopping list, they would appear in the ingredients list<br>

## Running the project locally.

1. download and unzip project.<br>
   open the project in a code editor e.g. Visual Studio Code.<br>
   Requires npm and node.js on your development setup.<br>

2. Requires firebase console as a backend<br>
   Sign up at: `https://console.firebase.google.com/`<br>
   create a new account, then create a new project.<br>
   Create a new realtime database.<br>
   edit rules to be:<br>
   {<br>
   &emsp;"rules": {<br>
   &emsp;&emsp;".read": "auth != null",<br>
   &emsp;&emsp;".write": "auth != null",<br>
   &emsp;}<br>
   }

copy the firebase link<br>
-> would be used in /environments/environment.prod.ts and /environments/environment.ts
replace the value for firebaseAPIUrl (the 'your_firebase_api_url')<br>
Go to authentication, choose email/ password for sign in method.<br>
then go to project settings, copy the web api key.<br>
-> would be used in /environments/environment.prod.ts and /environments/environment.ts
replace the value for firebaseAPIKey (the 'your_firebase_api_key')

3. In the terminal, type in:
   
&emsp;npm install --legacy-peer-deps<br>
&emsp;npm run build:ssr<br>
&emsp;npm run serve:ssr<br>
&emsp;go to the localhost link that is shown in the terminal
