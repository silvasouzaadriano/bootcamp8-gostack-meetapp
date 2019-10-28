<h1 align="center">
    MEETAPP challenge
</h1>

<h4 align="center">
  A challenge for [RocketSeat GoStack Bootcamp](https://rocketseat.com.br/bootcamp) Certificate
</h4>

## How To Use

To clone and run this application, you'll need [Git](https://git-scm.com), [Node.js v10.16][nodejs] or higher + [Yarn v1.19][yarn] or higher installed on your computer. 

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
$ yarn react-native start
```

---

Made with ♥ by Adriano Souza :wave: [Get in touch!](https://www.linkedin.com/in/adriano-souza-9b1a1b11)


