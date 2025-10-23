# Replicate the Development Environment:
## Background ->
1.  Tech used ->
    - NextJS React
    - TypeScript
    - Tailwind CSS
    - Firebase database

## Backend Steps ->
1. Clone repository from GitHub ->
    - copy HTTPS url
    - choose the desired location and then `git clone (url)` in the terminal
2. Install dependencies ->
    - `npm install` in terminal
3. Create Firesbase Database ->
    - name your database
        - ![alt text](images/name_db.png)
    - click continue until you reach the account section; use the default account
        - ![alt text](images/default_account.png)
    - click on build and then Firestore
        - ![alt text](images/firestore_db.png)
    - use the standard edition
    - set location to `nam5 (United States)`
    - start in production mode
    - add dummy data in this same format:
        - coach (collection):
            - ![alt text](images/coach.png)
        - school (collection):
            - ![alt text](images/school.png)
        - users (collection):
            - ![alt text](images/users.png)
    - create a `.env.local` file in your local repository with the following variables:
        - ![alt text](images/env.png)

## Frontend Steps:
1. Run project ->
    - `npm run dev` in terminal
    - click the localhost link and it will route you to the webpage in your browser
    - login with test credentials:
        - email - dev@demo.com
        - password - password


