# Integration with Hubspot

## Description
Automation of tasks on Hubspot such as creating forms, reading submissions of forms can be done with Linx and API requests. This sample demonstrate automation of tasks related with forms and submissions on Hubspot and pushing submissions to google sheets.  Reading of forms might be useful for an integration with an external system that has its own form-building interface. Submissions can be easily read for deduplicate, update or create contacts or integration with other third-part apps like Salesforce.

The sample also contains some generically designed functions that connect and make requests to the Salesforce API. You can copy and use these functions in your own Linx Solution to integrate with other 3rd-party systems that can be accessible via API.

#### Features:
* Create forms.
* Retrieve all forms details.
* Reading of submissions in Hubspot.
* Retrieving and writing out submissions to google sheets.
* Find duplicate and filter submissions to get distinct submissions based on email addresses
## Installation

#### Create a new connected app on Hubspot:
1. [Create a new test account](https://legacydocs.hubspot.com/docs/faq/how-do-i-create-a-test-account) on Hubspot.com
2. [Enable the OAuth 2.0 settings](https://developers.hubspot.com/docs/api/oauth-quickstart-guide)
   * Configure the Callback URL to be: http://localhost:8080/oauth/token
   * In the scope section, choose the following: **contacts social tickets forms**
3. Save your connected app.
4. Copy your client_id.
5. Copy your consumerSecret.

#### Google API Setup:

1. Register as a developer on [Developer console](https://console.developers.google.com/)
2. Register your Application/Project and Enable API scope. [How to?](https://linx.software/docs/guides/googleapis/)
3. Download Authorization Credentials
4. Connect your Linx application

#### Configure the Solution's $.Settings:
1. Open the sample HubspotIntegration(.lsoz) in your Linx Designer.
2. Edit the $.Settings values:
   * HubspotClientID: Your connected app’s **client_id**
   * HubspotConsumerSecret: Your connected app’s **Consumer Secret**
   * GoogleAuthCredentials : Copy paste the **Authorization Credentials** downloaded above.
3. Save the Solution.

#### Generate access tokens:
1. Start the debugger on the RESTHost service in the Linx Designer.
2. Make a request in your browser to http://localhost:8080/oauth/authorize
3. You will be redirected to the Hubspot 2.0 access consent screen.
4. Authorize the connected application.
5. View success message.

#### Create a google sheet and share with service account created
1. Locate the client_email in the **Authorization Credentials** JSON file downloaded above and copy the email.
2. Create a googlesheet in your gmail drive and share it with the email with editor's rights.

## Usage
#### Export submissions to googlesheet
Retrieves all submissions from Hubspot for a particular form and write them to googlesheet.   

To write out all the submission on your instance of Hubspot for a form to a sheet in googlesheet:

1. Generate the the access token.
2. Create and share your googlesheet with the registered service account.
3. Run the UpdateGoogleSheetsForFormGUID function.
    * Pass the form GUID as parameter.
    * Pass the GoogleSheetId as parameter.
---
#### Find duplicate emails in submissions
Very often, users submit duplicate forms and you need to clean them before any further use.  This function writes the duplicates emails in a file in the directory: C:\Linx\Hubspot\DuplicateEmails.txt

1. Generate the the access token.
2. Run the GetDuplicateSubmissionsFilterEmail function.
   * Pass the form GUID as parameter.

`If a file already exists with the same name then the data will get overwritten.`

#### Filter distinct submissions by email addresses
You need distinct submissions to be able to integrate with other 3rd party apps. This generic function returns a list of distinct submssions that can be easily used.
This function writes the duplicates emails in a file in the directory: C:\Linx\Hubspot\Submissions.txt

1. Generate the the access token.
2. Run the GetDuplicateSubmissionsFilterEmail function.
   * Pass the form GUID as parameter.

`If a file already exists with the same name then it will append the data in the file.`

## Contributing

For questions please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)

