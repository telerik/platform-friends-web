---
title: "Telerik Friends Sample App for Web/HTML"
slug: sample-backend-services-friends-web
position: 1
publish: true
page_title: Telerik Friends Sample App for Web/HTML | Telerik Platform
description: 
tags: Sample App, Web, Web app, HTML, Application, JavaScript, BaaS, mBaaS, Social, Analytics, Social Login, AD FS
---


# Telerik Friends Sample App for Web/HTML

<a href="https://github.com/telerik/platform-friends-web" target="_blank"><img style="padding-left:20px" src="http://docs.telerik.com/platform/appbuilder/sample-apps/images/get-github.png" alt="Get from GitHub" title="Get from GitHub"></a>

* [Overview](#overview)
* [Requirements](#requirements)
* [Configuration](#configuration)
* [Running the Sample](#running-the-sample)

This repository contains the Telerik Friends app for Web/HTML. It is a sample mobile app demonstrating how to integrate a large gamut of Telerik Platform services into a mobile Web application.

The Telerik Friends sample app showcases these features and SDKs:

- Cloud data access (Telerik Backend Services)
- Working with files (Telerik Backend Services)
- User registration and authentication (Telerik Backend Services)
- Authentication with social login providers (Facebook, Google, etc.) (Telerik Backend Services)
- Authentication with AD FS (Telerik Backend Services)
- Using custom user account fields (Telerik Backend Services)
- Basic app analytics (Telerik Analytics)
- Tracking feature usage (Telerik Analytics)

To implement all the features listed above, the sample app utilizes the following Telerik products and SDKs:

- Telerik Backend Services - this is where all data, files, and user accounts are stored in the cloud
- Telerik Backend Services JavaScript SDK - to connect the app to Telerik Backend Services
- Telerik Analytics - used to store and monitor analytics data in the cloud
- Telerik Analytics JavaScript SDK - to connect the app with Telerik Analytics

???- Telerik Mobile Testing - used to implement tests for the mobile app

## Requirements

Before you begin, you need to ensure that you have the following:

- **An active Telerik Platform account**
Ensure that you can log in to a Telerik Platform account. This can be a free trial account. Depending on your license you may not be able to use all app features. For more information on what is included in the different editions, check out the pricing page. All features included in the sample app work during the free trial period.

- **JavaScript/Html Editor**
You can use any JavaScript/HTML editor to edit the code (Notepad++, Sublime Text, etc.)

## Configuration

The Friends sample app comes fully functional, but to see it in action you must link it to your own Telerik Platform account.

What you need to set:

### API Key for Telerik Backend Services

This is a unique string that links the sample mobile app to a project in Telerik Backend Services where all the data is read from/saved. When creating the project, you must base it on the Friends sample Backend Services project that has all the necessary data prepopulated.

You must use this project's API key. To set it in the app:

1. Open the `/scripts/app/settings.js` file.
2. Replace `$EVERLIVE_API_KEY$` with the API Key of your Friends Backend Services project.

> If you happen to break the structure of the automatically generated Friends sample project, you can delete it and a fresh instance will be created again for you automatically. Alternatively, you could create a new project and choose to start from a Friends template, instead of starting from a blank project.

### (Optional) Project Key for Telerik Analytics

This is a unique string that links the sample mobile app to a Telerik Analytics project in your account. If you do not set this the sample will still work, but no analytics data will be collected.
	
1. Open the `/scripts/app/settings.js` file.
2. Replace `$EQATEC_PROJECT_KEY$` with the Project Key of your Friends Analytics project.

### (Optional) Facebook App ID
To demonstrate social login, we've pre-initialized the sample to use a purpose-built Facebook app by Telerik. However, you still need to enable Facebook integration in the Telerik Platform portal:

1. Go to your app.
2. Click the Backend Services project that you are using.
3. Navigate to **Users > Authentication**.
4. Ensure that the Facebook box is checked.

> Note that if you intend to use the code for a production app you need to set up your own Facebook application and adjust the Facebook app ID as follows:
	
1. Open the `/scripts/app/settings.js` file.
2. Find the `appId: '1408629486049918'` line.
3. Replace the number with your Facebook app ID.

### (Optional) Google Client ID

To demonstrate social login, we've pre-initialized the sample to use a Google Client ID owned by Telerik. However, you still need to enable Google integration in the Telerik Platform portal:

1. Go to your app.
2. Click the Backend Services project that you are using.
3. Navigate to **Users > Authentication**.
4. Ensure that the Google box is checked.

> Note that if you intend to use the code for a production app you need to set up your own Google Client ID and adjust the code as follows:

1. Open the `/scripts/app/settings.js` file.
2. Find the `clientId: '406987471724-q1sorfhhcbulk6r5r317l482u9f62ti8.apps.googleusercontent.com'` line.
3. Replace the number with your Google Client ID.
	
### (Optional) Microsoft Account

To demonstrate social login, we've pre-initialized the sample to use a  Microsoft Account Client ID owned by Telerik. However, you still need to enable Microsoft Account integration in the Telerik Platform portal:

1. Go to your app.
2. Click the Backend Services project that you are using.
3. Navigate to **Users > Authentication**.
4. Ensure that the Windows Live box is checked.

> Note that if you intend to use the code for a production app you need to set up your own Microsoft Account Client ID and adjust the code as follows:

1. Open the `/scripts/app/settings.js` file.
2. Find the `clientId: '000000004C10D1AF'` line.
3. Replace the number with your Microsoft Account Client ID.

> When testing, you can't use `localhost` as a redirect domain. Instead, create an alias such as `mydev.machine.local` and map it to 127.0.0.1 in your system's HOSTS file.

### (Optional) Active Directory Federation Services (AD FS)

The sample app allows users to [register using AD FS](http://docs.telerik.com/platform/backend-services/javascript/users/adfs-login/introduction). To try this integration, configure the following:

1. Replace the default setting in `/scripts/app/settings.js`:

	```
	adfsRealm: '$ADFS_REALM$'
	adfsEndpoint: '$ADFS_ENDPOINT$'
	```
2. Log in to the Telerik Platform portal.
3. Go to your app.
4. Click the Backend Services project that you are using.
5. Navigate to **Users > Authentication**.
6. Ensure that the Active Directory box is checked.
7. Fill in **ADFS metadata URL** with your AD FS server's metadata URL.

> Note that AD FS authentication can only be accomplished over HTTPS.

### HTTPS Connections

By default the Friends Sample is configured to use HTTP. If you want to switch to HTTPS, update the `appSettings.everlive.scheme` setting in  `/scripts/app/settings.js` to `https`.

## Running the Sample

Once the app is configured, you can host it on any Web server and run it in a Web browser.

> Ensure that the Web browser that you are using has Internet connectivity when running the sample.

## Screenshots

![](screenshots/ios-login-screen.png)
![](screenshots/ios-activities-stream.png)
![](screenshots/ios-activitiy-details.png)
