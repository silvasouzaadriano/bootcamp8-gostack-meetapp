<h1 align="center">
    MEETAPP challenger
</h1>


## A challenger for [RocketSeat GoStack Bootcamp](https://rocketseat.com.br/bootcamp) Certificate


## Concepts

- The application created is an event agregator for developers called Meetapp (acronymous for Meetup + App). It means that users will be able to create it owns meetups and also participate in meetups which were not created by the same user logged.
- The backend application its an API which will allow: create, update and authenticate users (using encryption for password); create, update and list meetups; create, update and list subscription in meetups; notify meetup onwers, via e-mail, about new subscriptions; upload meetup banner and user avatar
- By the the frontend and mobile applications will be possible the user sign up and manage it profile.
- By the front end and mobile applications will be possible the user sign up and manage it profile.
- Complementing the fuctionalities regarding to sign up / sign in, the front end and mobile applications has distinct utilizations:

  1) The frontend was developed only to allow users to create and manage meetups.
  2) The mobile application was built only to allow users to subscribe to meetups which they are not ornanizing.

## Main Technologies used

### BACK-END
-   [Node.js](https://nodejs.org/en/)
-   [Express](https://expressjs.com/)
-   [nodemon](https://nodemon.io/)
-   [Sucrase](https://github.com/alangpierce/sucrase)
-   [Docker](https://www.docker.com/docker-community)
-   [Sequelize](http://docs.sequelizejs.com/)
-   [PostgreSQL](https://www.postgresql.org/)
-   [node-postgres](https://www.npmjs.com/package/pg)
-   [Redis](https://redis.io/)
-   [MongoDB](https://www.mongodb.com/)
-   [Mongoose](https://mongoosejs.com/)
-   [JWT](https://jwt.io/)
-   [Multer](https://github.com/expressjs/multer)
-   [Bcrypt](https://www.npmjs.com/package/bcrypt)
-   [Youch](https://www.npmjs.com/package/youch)
-   [Yup](https://www.npmjs.com/package/yup)
-   [Bee Queue](https://www.npmjs.com/package/bcrypt)
-   [Nodemailer](https://nodemailer.com/about/)
-   [date-fns](https://date-fns.org/)
-   [Sentry](https://sentry.io/)
-   [DotEnv](https://www.npmjs.com/package/dotenv)
-   [VS Code](https://code.visualstudio.com/) with [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) 

### FRONT-END
-   [ReactJS](https://reactjs.org/)
-   [Create React App Configuration Override](https://github.com/sharegate/craco)
-   [Redux](https://redux.js.org/)
-   [Redux-Saga](https://redux-saga.js.org/)
-   [React Router v4](https://github.com/ReactTraining/react-router)
-   [styled-components](https://www.styled-components.com/)
-   [Axios](https://github.com/axios/axios)
-   [History](https://www.npmjs.com/package/history)
-   [Immer](https://github.com/immerjs/immer)
-   [Polished](https://polished.js.org/)
-   [React-Toastify](https://fkhadra.github.io/react-toastify/)
-   [React-Icons](http://react-icons.github.io/react-icons/)
-   [react-perfect-scrollbar](https://github.com/OpusCapita/react-perfect-scrollbar)
-   [Unform](https://github.com/Rocketseat/unform)
-   [Yup](https://www.npmjs.com/package/yup)
-   [date-fns](https://date-fns.org/)
-   [Reactotron](https://infinite.red/reactotron)
-   [VS Code](https://code.visualstudio.com/) with [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

### MOBILE
-   [ReactJS](https://reactjs.org/)
-   [React Native](https://facebook.github.io/react-native/)
-   [Xcode](https://developer.apple.com/xcode/)
-   [styled-components](https://www.styled-components.com/)
-   [Axios](https://github.com/axios/axios)
-   [Polished](https://polished.js.org/)
-   [React-native-flash-message](https://github.com/lucasferreira/react-native-flash-message#readme)
-   [React-Icons](http://react-icons.github.io/react-icons/)
-   [react-perfect-scrollbar](https://github.com/OpusCapita/react-perfect-scrollbar)
-   [Unform](https://github.com/Rocketseat/unform)
-   [Yup](https://www.npmjs.com/package/yup)
-   [date-fns](https://date-fns.org/)
-   [Reactotron](https://infinite.red/reactotron)
-   [VS Code](https://code.visualstudio.com/) with [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)




## How To Use

To clone and run this application, you'll need [Docker](https://docs.docker.com/),  [Git](https://git-scm.com), [Node.js v10.16.1](https://nodejs.org/en/) or higher + [Yarn v1.19.1](https://yarnpkg.com/lang/en/) or higher installed on your computer. 

NOTE: The mobile application only was tested using Android Studio emulator. However, as the react native compile for both Android and IOS its expected it running in both application.

### Install Backend
```bash
# Clone this repository
$ git clone https://github.com/silvasouzaadriano/bootcamp8-gostack-meetapp

# Go into the repository
$ cd bootcamp8-gostack-meetapp/backend

# Install dependencies
$ yarn install

# Created Postgree Docker container
$ docker run --name meetapp_database -e POSTGRES_PASSWORD=docker -e POSTGRES_DB=meetapp -p 5432:5432 -d postgres

# Created Mongo Docker container
$ docker run --name meetapp_mongo -p 27017:27017 -d -t mongo

# Created Redis Docker container
$ docker run --name meetapp_redis -p 6379:6379 -d -t redis:alpine

# .env
$ Replace the .env.EXAMPLE to .env

# Mail
In the .env must be changed the user and password regarding on section mail according to created on https://mailtrap.io. Note that this approach was used to simulate the email sending regarding to notifications. The suggestion is to Log in the Mailtrap and create an Inbox called Meetapp then access the inbox created for get the credencials which must be used on on .env, section Mail.

# Run Migrates
$ yarn sequelize db:migrate

# Run the API
$ yarn dev

# Run the QUEUE for send emails
$ yarn queue
```

### Install Frontend
```bash

# Go into the front path
$ cd bootcamp8-gostack-meetapp/frontend

# Install dependencies
$ yarn install

# Run the Front
$ yarn start
```

### Install Mobile
```bash

# Go into the front path
$ cd bootcamp8-gostack-meetapp/mobile

# Install dependencies
$ yarn install

# Link the native-dependencies
$ yarn react-native link react-native-vector-icons
$ yarn react-native link @react-native-community/async-storage
$ yarn react-native run-android (if you are running the application in the Android Studio) OR
$ yarn react-native-run-ios (if you are running the application by MacOS) 


# Run the mobile
- For Android
  $ adb reverse tcp:3333 tcp:3333
  $ yarn react-native run-android
  $ yarn react-native start

- For IOS
  $ yarn react-native start
```

---

Made with ♥ by Adriano Souza :wave: [Get in touch!](https://www.linkedin.com/in/adriano-souza-9b1a1b11)


