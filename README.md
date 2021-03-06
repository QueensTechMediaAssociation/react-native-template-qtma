# QTMA React Native BoilerPlate :volcano:

## Preliminary Setup

- Please download and use [VSCode](https://code.visualstudio.com/) as your IDE
  - Download the following extensions:
    - [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack)
    - [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
    - [React Native Tools](https://marketplace.visualstudio.com/items?itemName=msjsdiag.vscode-react-native)
    - [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) code formatter
- Download [Git](https://git-scm.com/)
- Download [NPM](https://www.npmjs.com/get-npm)
- Download [yarn](https://classic.yarnpkg.com/en/docs/install/#windows-stable)

## Environment Setup :evergreen_tree:
- Run `yarn global add react-native-cli` to get the react native cli installed globally on your machine
- :warning: In the React Native Environment Setup make sure you do the following
  - Switch to the React Native CLI Quickstart (Not EXPO), make sure you select the Development OS and target OS pertaining to your machine
  - Follow the tutorial until the "Creating a new application" section
  > _Note:_ follow the tutorial for both Target OS's as you'll want to setup your project for both Android and IOS
- Follow the [React Native Environment Setup](https://reactnative.dev/docs/environment-setup) until the "Creating a new application" section

## Get Started With The Template
- Open a VSCode, open an integreated terminal Terminal>New Terminal and clone the template repository to a known folder for example /quentinrf/QTMA_Template/
  ```sh
  mkdir QTMA_Template
  cd QTMA_Template
  git clone https://github.com/QueensTechMediaAssociation/react-native-template-qtma
  ```
- In your Terminal/CMD
  - Navigate to your project's GitHub repository
  - Create a new React Native project using the repository you cloned earlier as a template
  - :warning: make sure to replace my path with your machines unique path!
  ```sh
  cd <Your_Personal_Github_Repository>
  react-native init <your_react_native_project_name> --template file:///Users/quentinrf/QTMA_Template/react-native-template-qtma
  ```

## Run Your Mobile Application and watch it fail
- Open your React Native Project in VSCode
- Open <your_project_name>/app.json
  - Change the "name" and "displayName" values to match the project name you just gave your React Native Project
- Depending on which target OS you've configured your project for you'll need to run a different command
- ios to be done in XCode
  - Open <your_project_name>/ios/<your_project_name>.xcworkspace
  - Click on your project in the left pane, then click the first Target under TARGETS, navigate to Signing & Capabilities (next to General) and add an apple development team and a unique bundle identifier
  - In your projects top level directory there will be a package.lock and a yarn.lock file, delete the package.lock as we'll be using yarn
  - For some weird reason the react-native-vector-icons package causes a build failure when configured from the template
  - Run
  ```sh
  yarn add react-native-vector-icons
  ```
  - cd into <your_project_name>/ios and run
  ```sh
  pod install
  ```
  - Now run your application with the following command and you should see an error "No Firebase App '[DEFAULT]' has been created - call firebase.initializeApp()"
  ```sh
  react-native run-ios
  ```
  - If you got a different error that looks like "XCode 10: Multiple Commands Produce ..." you'll need to navigate to <your_project_name>.xcworkspace
  - Open Build Phases which is next to "Signing & Capabilities" and open "Copy Bundle Resources" delete everything that isn't "Images.xcassets", "LaunchScreen.xib" and "GoogleService-info.plist" and try re-running the application
- Android
  - The following should fail
  ```sh
  react-native run-android
  ```

## Configure Your Application With A Firebase Project :fire:

- Go to [Firebase](https://firebase.google.com/)
- Click Get Started > Create New Project, follow the steps to create your project and make sure Google Analytics is enabled.
- Now it's time to add this project to your mobile app
  - In the Firebase project overview click on add app, select the same targetOS as used in "Environment Setup"
  - Follow the [React Native Firebase Getting Started Guide](https://rnfirebase.io/) for your target OS to configure your project with Firebase. Everyone should have autolinking available to them so stop when you see "Manual Linking", you don't need to complete the miscellaneous section


## Help

For any questions about the boiler plate and getting it setup on your local machine please reach out to quentinrf@gmail.com
