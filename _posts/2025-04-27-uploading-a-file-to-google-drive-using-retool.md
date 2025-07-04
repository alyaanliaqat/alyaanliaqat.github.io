---
title: "Upload and Add Data to Google Drive Files Using Retool"
date: "2025-04-26 00:00:00"
categories: [API integration, Google Drive, Retool, Workflows, Transfer Data, Automation]
tags: [API integration, Google Drive, Retool, Workflow, Data Upload, Transfer Data, Automation]
---

## Introduction

In this blog, we will learn how to **create and upload a file to Google Drive** directly using **Retool Workflows**. You will be able to dynamically add your data (like JSON, CSV, etc.) into files and save them in a specific folder inside your Drive.

🔗 *Note: If you haven’t set up your Google Drive resource yet, please visit my previous blog here: [Google Drive API Integration with Retool Resources](https://alyaanliaqat.github.io/posts/google-drive-api-integration-in-retool-resource/)*

---

## Step 1: Create a New Workflow in Retool

1. In your Retool workspace, click **Workflows** → **New Workflow**.  
   ![Create a New Workflow]( /assets/images/blog_images/uploadingfileinretool/p1.png)
2. From the **Blocks** panel, drag a **Resource Query** block into the canvas.  
   ![Add Resource Query Block]( /assets/images/blog_images/uploadingfileinretool/p2.png)
3. Search for and select the **Google Drive** resource you created earlier.  
   ![Select Google Drive Resource]( /assets/images/blog_images/uploadingfileinretool/p3.png)
4. Connect the output of your data source block (e.g., a table or previous query) to this Resource Query block.
5. Set the **Request Type** to `POST`.
6. In the **Endpoint** field, add: `?uploadType=multipart`

![Set Endpoint](/assets/images/blog_images/uploadingfileinretool/p4.png)

---

## Step 2: Configure Headers and Body Type

1. Click **More configurations** on the Resource Query block.
2. Under **Headers**, add:

Authorization: `Bearer OAUTH2_TOKEN` 
Content-Type: `multipart/related; boundary=foo_bar_baz`

3. Set **Body type** to **Raw**.  
![Choose Raw Body](/assets/images/blog_images/uploadingfileinretool/p5.png)

---

## Step 3: Write the Raw Request Body

Insert the following raw multipart payload:
```
--foo_bar_baz Content-Type: 
application/json; charset=UTF-8

{ 
   "name": "yourfile.json", 
   "mimeType": "application/json", 
   "parents": ["PARENT_ID_FOR_GOOGLE_DRIVE_FOLDER"] 
} 
--foo_bar_baz 
Content-Type: application/json 
YOUR_FILE_DATA 
--foo_bar_baz--
```


- **name**: Filename as it will appear in Drive (e.g., `yourfile.json`).
- **mimeType**: File type (e.g., `"application/json"` or `"text/csv"`).
- **parents**: Array containing the folder ID where the file should be created.

---

## Step 4: Locate Your Parent Folder ID

To find the **Parent Folder ID**:

1. Open the desired folder in Google Drive.
2. Look at the URL — the long string after `/folders/` is the folder ID.  
   ![Locate Folder ID](/assets/images/blog_images/uploadingfileinretool/p6.png)

Example: `138esQimMAav_Y35X1B3cuf1Y1_G4zjWe`

---

## Step 5: Final Raw Body Example

Here’s a complete raw body example using the real folder ID and dynamic data:

{% raw %}
```
--foo_bar_baz
Content-Type: application/json; charset=UTF-8

{
  "name": "retooldatafile.json",
  "mimeType": "application/json",
  "parents": ["138esQimMAav_Y35X1B3cuf1Y1_G4zjWe"]
}
--foo_bar_baz
Content-Type: application/json

{{ JSON.stringify(query2.data, null, 2) }}

--foo_bar_baz--
```
{% endraw %}



> Here, `query2.data` refers to the data output from your previous query or data block.

---

## Step 6: Run the Query and Verify

1. Click **Run** on your Resource Query block.
2. In the response, you’ll see the newly created **file ID**, confirming success.
   ![Final Raw Body](/assets/images/blog_images/uploadingfileinretool/p7.png)
3. Open your Google Drive folder — you should see `retooldatafile.json` there!  
   ![File ID in Response](/assets/images/blog_images/uploadingfileinretool/p8.png)

🎉 You’ve successfully uploaded a JSON file to Google Drive using Retool Workflows!
   ![File in Drive](/assets/images/blog_images/uploadingfileinretool/p9.png)

---

## Notes on Other File Types

- To upload **CSV** files, change:
  `"mimeType": "text/csv"`

Ensure your RAW body content matches the file format (comma-delimited for CSV, etc.).

## Conclusion
By combining Retool Workflows with the Google Drive API, you can effortlessly automate file creation and data uploads to Drive folders. This approach requires no backend server — everything runs smoothly within Retool, unlocking powerful automation capabilities for your apps and processes.

Stay tuned for more tutorials, and happy automating! 🚀

---

## 📬 Contact

**Alyaan Liaqat**  
📧 [alyaanch3@gmail.com]  
🌐 [GitHub Portfolio](https://alyaanliaqat.github.io/)

---