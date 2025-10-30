# Deploying with Firebase Hosting:

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
