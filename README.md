# Integration with Hubspot

## Description
Automation of tasks on Hubspot such as creating forms, reading submissions of forms can be with Linx and API requests. This sample demonstrate automation of tasks related with forms on Hubspot and pushing submissions  to google sheets
Features:
* Create forms.
* Reading of submissions in Hubspot.
* Retrieving and writing out submissions to google sheets.
* Find duplicate and filter submissions to get distinct submissions based on email addresses
## Installation

https://developers.hubspot.com/docs/api/working-with-oauth
https://developer.okta.com/blog/2018/04/10/oauth-authorization-code-grant-type
https://knowledge.hubspot.com/forms/find-your-form-guid

Create a new connected app on Salesforce:
1. Create a new test account on�Hubspot.com or (Create a test account)[https://legacydocs.hubspot.com/docs/faq/how-do-i-create-a-test-account]
2. Enable the OAuth 2.0 settings. 
(How to) [https://developers.hubspot.com/docs/api/oauth-quickstart-guide]
o Configure the Callback URL to be:�http://localhost:8080/oauth/token
o In the scope section, choose the following: **contacts social tickets forms**
3. Save your connected app.
4. Copy your�client_id.
5. Copy your consumerSecret.
Configure the Solution's $.Settings:
1. Install Linx Designer. Download it�here.
2. Open the sample HubspotIntegration(.lsoz) in your Linx Designer.
3. Edit the $.Settings values:
o HubspotClientID: Your connected app�s�client_id
o HubspotConsumerSecret: Your connected app�s�Consumer Secret
4. Save the Solution.
Generate access tokens:
1. Start the debugger on the RESTHost service in the Linx Designer.
2. Make a request in your browser to�http://localhost:8080/oauth/authorize
3. You will be redirected to the Hubspot 2.0 access consent screen.
4. Authorize the connected application.
5. View success message.
 

## Usage


## Contributing

For questions please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)

