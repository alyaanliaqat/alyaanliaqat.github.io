---
title: "Google Drive API Integration with Retool Resources"
date: "2025-04-26 00:00:00"
categories: [Retool, Google Drive API, API Integration, Workflows]
tags: [Retool, Google Drive API, Resource, OAuth, Automation]
---

# Google Drive API Integration with Retool Resources

## Introduction

In this blog post, we will walk through how to **create a Google Drive API integration inside Retool Resources**.  
By the end of this guide, you will have a resource that allows you to **create folders** and **upload files** directly into your Google Drive using Retool apps or workflows.  
This integration will help you automate tasks and seamlessly build workflows powered by Google Drive and Retool.

---

## Step 1: Set up OAuth Credentials in Google Cloud Console

First, we need to set up OAuth 2.0 credentials to allow Retool to interact with your Google Drive securely.

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. From the **Navigation menu**, go to **APIs & Services** → **Credentials**.  
   
   ![Google Cloud Console Credentials Page](/assets/images/blog_images/googledriveintegrationwithretool/p1.png)

3. On the **Credentials** page, click **+ Create Credentials** and select **OAuth client ID**.

   ![Create Credentials - OAuth Client ID](/assets/images/blog_images/googledriveintegrationwithretool/p2.png)

4. Select **Web Application** as the application type.

5. Add your custom application name.  

   ![Select Web Application and Add Name](/assets/images/blog_images/googledriveintegrationwithretool/p3.png)

6. Under the configuration, set the following:
   - **Authorized JavaScript origins**:  
     ```
     https://{your-retool-domain}.retool.com
     ```
   - **Authorized redirect URIs**:  
     ```
     https://oauth.retool.com/oauth/oauthcallback
     ```

7. After filling the details, click **Create**.

   ![OAuth Client Credentials Created](/assets/images/blog_images/googledriveintegrationwithretool/p4.png)

Congratulations! 🎉 You have successfully created your OAuth credentials for Retool.

---

## Step 2: Finalize OAuth Setup in Google Cloud Console

Now that you have created your OAuth credentials, you need to finish setting up access.

1. **Note down** your **Client ID** and **Client Secret** — you will need them while configuring Retool.

2. Click on the **OAuth Consent Screen** tab under Credentials.

   ![OAuth Consent Screen](/assets/images/blog_images/googledriveintegrationwithretool/p5.png)

3. Under the **Test Users** section, click the **Add Users** button.

4. Add the email address you use in Retool.  
   *(You can add multiple test users if needed.)*

   ![Add Test User in OAuth Consent Screen](/assets/images/blog_images/googledriveintegrationwithretool/p6.png)

5. Now, go to the search bar at the top of Google Cloud Console, and search for **Google Drive API**.

6. Select the **Google Drive API** provided by Google Enterprise API.

   ![Google Drive API Search](/assets/images/blog_images/googledriveintegrationwithretool/p7.png)

7. Make sure the **Google Drive API** is **enabled** and configured for **full access**.

   ![Google Drive API Enabled](/assets/images/blog_images/googledriveintegrationwithretool/p9.png)

✅ Congratulations!  
You have now completed all setup on the Google Cloud side.  
Let's move to Retool now!

---

## Step 3: Configure Google Drive API Resource in Retool

Now, let’s set up Retool to connect with your Google Drive.

1. In Retool, go to **Resources** and click **Create New**.

2. Choose **Resource Type** → **REST API**.

   ![Create REST API Resource](/assets/images/blog_images/googledriveintegrationwithretool/p8.png)

3. Fill the following fields:

   - **Name**: Enter a custom name for your resource.
   - **Base URL**:  
     ```
     https://www.googleapis.com/upload/drive/v3/files
     ```

4. Scroll down to the **Headers** section and add:

   | Key | Value |
   |:---|:---|
   | Authorization | Bearer OAUTH2_TOKEN |

   ![Add Authorization Header](/assets/images/blog_images/googledriveintegrationwithretool/p10.png)

5. Scroll further down and under **Authentication**, select **OAuth 2.0**.

6. Fill the fields as follows:

   | Field | Value |
   |:---|:---|
   | Authorization URL | `https://accounts.google.com/o/oauth2/v2/auth?access_type=offline&prompt=consent` |
   | Access Token URL | `https://oauth2.googleapis.com/token` |
   | Client ID | `"YOUR_OAUTH_CLIENT_ID"` |
   | Client Secret | `"YOUR_OAUTH_CLIENT_SECRET"` |
   | Scopes | `https://www.googleapis.com/auth/drive` |

   *(You can customize the scope depending on your needs; the above scope gives full Google Drive access.)*

7. Make sure to check the box **"Share OAuth2 credentials between users"**.

8. Click **Connect with OAuth**.

   ![Connect with OAuth](/assets/images/blog_images/googledriveintegrationwithretool/p11.png)

9. A popup will appear. Click **Authenticate**, select the **test user account** you added earlier, and click **Continue**.

   ![Authenticate OAuth Connection](/assets/images/blog_images/googledriveintegrationwithretool/p12.png)

10. Once authentication succeeds, click **Save**.

✅ You have now successfully connected your **Google Drive** as a resource inside Retool!

---

## 🎉 Conclusion

Now you have a fully functioning Retool resource integrated with Google Drive!  
You can use this resource to **create folders**, **upload files**, and **automate workflows** that interact directly with Google Drive — all from within Retool.

This setup unlocks huge potential for automation, file management, and dynamic app building with Retool and Google APIs.

In my next blog I will discuss how to create a file in google drive and upload content in it.
---

