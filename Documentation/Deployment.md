# ~~~ Hosting ~~~
Fore more in-depth information, visit the following documentation - https://firebase.google.com/docs/hosting/test-preview-deploy?authuser=0#view-changes

<br>

## Deploying with Firebase Hosting Locally:

### step 1:
- Install Firebase CLI - `npm install -g firebase-tools`

### step 2:
- Enable Web Frameworks - `firebase experiments:enable webframeworks`

### step 3:
- Login to Firebase - `firebase login`

### step 4:
- Go to the root of the project and run - `firebase init hosting`

### step 5:
- Follow the provided prompts and select the existing Firebase
- Answer "yes" to using a web framework
- Choose "Next.js"
- The Firebase CLI will configure firebase.json

### step 6:
- Build Next.js application - `npm run build`

### step 7:
- The build will be generated so you are safe to deploy - `firebase deploy`

<br>

## Testing Locally:

### step 1:
- At the root of the project run - `firebase emulators:start`

### step 2:
- Open the web app at the local URL provided

<br>

## Create a Preview Link:

### step 1:
- To create a link that you can send to others so they can preview the web app, run the following from your local project directory - `firebase hosting:channel:deploy CHANNEL_ID`
- CHANNEL_ID = a string with no spaces (you can get creative here: i.e. basketball-dashboard-test-1)

### step 2:
- The CLI will provide a preview URL you can click on

<br>

## Deploying with Firebase Hosting from Local Project Directory to Live Channel:

### step 1: 
- Run the following command in the root of the local project directory - `firebase deploy --only hosting`
- It's possible to view your hosted site from 2 URLS: SITE_ID.web.app and SITE.ID.firebaseapp.com
- SITE_ID is usually defaulted to the same as the PROJECT_ID

<br>

## Stop a Deployment:

### step 1:
- Run the following in the local project directory after a deployment has begun - `firebase hosting:disable`
