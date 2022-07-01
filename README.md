# Integrating the SDK

## Introduction
- DIGITALREEF's SDK is delivered as a zipped folder containing React Native library. The main contents of the zip file are: react-native-iu-library 

- yarn add/npm install {project-folder}/react-native-iu-library –save 

- Please note if deployment target on podspec file 

- Verify platform version on podfile 

- cd ios – pod install 

## Integration Overview 
![Screen Shot 2022-07-01 at 11 22 34](https://user-images.githubusercontent.com/95364508/176912920-f58716aa-b356-4d3e-88e6-5939a0a3a884.png)

### Step 1: Extract the react-native-iu-library.zip 

Extract the react-native-iu-library file shared by DR team to an easily accessible folder to integrate with your project. 

 

### Step 2: Open Terminal (Mac/Linux) or command prompt (Windows) 

Open the Command prompt (windows) / Terminal (Linux/Mac) and change directory to your project. 

 

### Step 3: Add the React Native DR library 

In command prompt / terminal type the following command. 

 

    npm install / yarn add <extracted folder>\react-native-iu-library –save 

 

Path would be the "{Extracted folder}" where ReactNative-amlibrary.zip was extracted in Step 1 

On successful completion of the add command you would be able to see a message similar to the following 

+ `react-native-iu-library@1.0.0 added 1 package from 1 contributor and audited 1 package in 3.704s found 0 vulnerabilities` 

Next step, you need to run the following command 

    npx react-native link react-native-iu-library 

On successful completion of the add command you would be able to see a message similar to the following 

      -  info Linking "react-native-iu-library" iOS dependency 
        
       - info iOS module "react-native-iu-library" has been successfully linked 
        
        - info Linking "react-native-iu-library" Android dependency 
        
        - info Android module "react-native-iu-library" has been successfully linked 

 

### Step 4: Pod Install 

On your prompt / terminal navigate to ios folder of your project and type the following command. 

    pod install 

 

### Step 5: Add App Groups 

Select the target of your project on XCode and go to: "Signing & Capabilites" >  "+ Capabillity" and add App Groups 
![Screen Shot 2022-07-01 at 11 25 32](https://user-images.githubusercontent.com/95364508/176913453-7dc62f73-4651-4a28-bf34-0521a6cbba0e.png)
After  that, select  the  groups

![Screen Shot 2022-07-01 at 11 27 36](https://user-images.githubusercontent.com/95364508/176913815-3a91b0f4-d5ae-4d6d-ad58-536a4d445cf9.png)

### Step 6: Import DR SDK

Go to index.js file of  your  React  Native  project  and  import  our SDK calling:

    import  DigitalReefSDK  from 'react-native-iu-library'

### Step 7: Initialize  the SDK

Call  this  method  below  and  put  the  same  appgroup as string, following  the  step 5.

DigitalReefSDK.shared('', '')
