<h1 align="center">
    MEETAPP challenger
</h1>


## A challenger for [RocketSeat GoStack Bootcamp](https://rocketseat.com.br/bootcamp) Certificate


## Concepts

- The application created is a event agregator for developers called Meetapp (acronymous for Meetup + App). It means that users will be able to create it owns meetups and also participate in meetups which were not created by the same user logged.
- The backend application its an API which will allow: create, update and authenticate users (using encryption for password); create, update and list meetups; create, update and list subscription in meetups; notify meetup onwers, via e-mail, about new subscriptions; upload meetup banner and user avatar
- By the the frontend and mobile applications will be possible the user sign up and manage it profile.
- By the front end and mobile applications will be possible the user sign up and manage it profile.
- Complementing the fuctionalities regarding to sign up / sign in, the front end and mobile applications has distinct utilizations:

  1) The frontend was developed only to allow users to create and manage meetups.
  2) The mobile application was built only to allow users to subscribe to meetups which they are not ornanizing.


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


