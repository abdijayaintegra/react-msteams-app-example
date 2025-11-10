# Contacts Management Teams App

A sample **Microsoft Teams React application** built for internal **training and sharing sessions** in our development / IT department.  
This project demonstrates how to integrate a modern React frontend with the Microsoft Teams platform — focusing on how to build, configure, and deploy a **Contacts Management App** using Teams SDK, Fluent UI, and an existing backend service.

---

## Overview

This project serves as a **learning resource** for developers to understand how to:
- Develop and run a **React-based Microsoft Teams App**.
- Integrate frontend components using **Fluent UI** and **TeamsFx SDK**.
- Connect to a pre-built backend API (Contacts Service).
- Manage environment configuration with `.env` files.
- Optionally expose your local development environment using **ngrok** for Teams public preview.

---

## Prerequisites

Before running the project, make sure you have the following installed:

- **Node.js** (≥ 18.x)  
- **npm** or **bun** (package manager)  
- **Microsoft Teams Developer Account**
- **Visual Studio Code** or other IDE/Text Editor
- **Ngrok** (for testing your app from public Teams environment)
- **Git** for version control  
- **TeamsFx CLI** for advanced setup

---

## Getting Started with the Project

1. Fork this Repository
Fork or clone the repository into your local environment:
```bash
git clone https://github.com/<your-org>/react-msteams-app-example.git
cd react-msteams-app-example
```

2. Working with .env Information. Rename all .env files and remove the word example from filenames: <br>
- **.env.example.dev** → **.env.dev**
- **.env.example.dev.user** → **.env.dev.user**
- **.env.example.local** → **.env.local**
- **.env.example.local.user** → **.env.local.user**

    Complete all required environment variables in each .env file.
These values depend on your developer setup (consult your team lead if unsure). Double-check all values inside the .env files before starting the app.

3. Working with npm or bun CLI Commands Install dependencies:
```bash
npm install
# or
bun install
```
&emsp; &emsp; &nbsp;run it locally
```bash
npm run start
# or
bun run start
```
&emsp; &emsp; &nbsp;This will start the local development server and open the app in your browser. <br>
&emsp; &emsp; &nbsp;If you’re using the Teams Toolkit, you can also run directly inside Teams.

4. Bonus: Working with ngrok for Public Preview.
    
    If you want to test your app on a real Microsoft Teams environment (not just local):<br>
    > Install ngrok (if you haven’t yet):
    > https://ngrok.com/download
    
    Run ngrok to expose your local port (default 3000):
```bash
ngrok http 3000
```
> **Copy the generated public HTTPS URL and update it** in:
> Your .env file (BASE_URL_APP)
> Microsoft Teams App manifest (for validDomains or contentUrl)
> Reload the app in Microsoft Teams using the new public URL.

## Credits

The backend API used in this training is adapted from the open community project by Eko Kurniawan Khannedy — [GitHub: Eko Kurniawan Khannedy - Technical Architect at BliBli.com](https://github.com/khannedy).

All rights and credit for the backend logic belong to him and the contributors of that repository.

## License

This project is for educational and internal use only within the developer team.
If reused publicly, please include proper credit for both frontend and backend authors.

## Support 
If you face issues during setup or integration:

- Check .env configurations first.

- Verify that your Teams Developer environment is correctly configured.

- Ask questions in the internal Teams “#dev-sharing-session” channel.
 

## Overview of the React with Fluent UI template

This app showcases how to craft a visually appealing web page that can be embedded in Microsoft Teams, Outlook and the Microsoft 365 app with React and Fluent UI. The app also enhances the end-user experiences with built-in single sign-on and data from Microsoft Graph.

This app has adopted [On-Behalf-Of flow](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow) to implement SSO, and uses Azure Function as middle-tier service, and make authenticated requests to call Graph from Azure Function.

### Get started with the React with Fluent UI template

> **Prerequisites**
>
> To run the command bot template in your local dev machine, you will need:
>
> - [Node.js](https://nodejs.org/), supported versions: 16, 18
> - A [Microsoft 365 account for development](https://docs.microsoft.com/microsoftteams/platform/toolkit/accounts)
> - [Set up your dev environment for extending Teams apps across Microsoft 365](https://aka.ms/teamsfx-m365-apps-prerequisites)
> Please note that after you enrolled your developer tenant in Office 365 Target Release, it may take couple days for the enrollment to take effect.
> - [Teams Toolkit Visual Studio Code Extension](https://aka.ms/teams-toolkit) version 5.0.0 and higher or [Teams Toolkit CLI](https://aka.ms/teamsfx-cli)

1. First, select the Teams Toolkit icon on the left in the VS Code toolbar.
2. In the Account section, sign in with your [Microsoft 365 account](https://docs.microsoft.com/microsoftteams/platform/toolkit/accounts) if you haven't already.
3. Press F5 to start debugging which launches your app in Teams using a web browser. Select `Debug (Edge)` or `Debug (Chrome)`.
4. When Teams launches in the browser, select the Add button in the dialog to install your app to Teams.

**Congratulations**! You are running an application that can now show a beautiful web page in Teams, Outlook and the Microsoft 365 app.

![Personal tab demo](https://user-images.githubusercontent.com/11220663/167839153-0aef6adc-450e-4b8c-a28f-7d27005d1093.png)

### What's included in the template

| Folder       | Contents                                            |
| - | - |
| `.vscode`    | VSCode files for debugging                          |
| `appPackage` | Templates for the Teams application manifest        |
| `env`        | Environment files                                   |
| `infra`      | Templates for provisioning Azure resources          |
| `src`        | The source code for the Teams application |

The following are Teams Toolkit specific project files. You can [visit a complete guide on Github](https://github.com/OfficeDev/TeamsFx/wiki/Teams-Toolkit-Visual-Studio-Code-v5-Guide#overview) to understand how Teams Toolkit works.

| File                                 | Contents                                           |
| - | - |
|`teamsapp.yml`|This is the main Teams Toolkit project file. The project file defines two primary things:  Properties and configuration Stage definitions.|
|`teamsapp.local.yml`|This overrides `teamsapp.yml` with actions that enable local execution and debugging.|
|`aad.manifest.json`|This file defines the configuration of Microsoft Entra app. This template will only provision [single tenant](https://learn.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps#who-can-sign-in-to-your-app) Microsoft Entra app.|

### Extend the React with Fluent UI template

Following documentation will help you to extend the React with Fluent UI template.

- [Add or manage the environment](https://learn.microsoft.com/microsoftteams/platform/toolkit/teamsfx-multi-env)
- [Create multi-capability app](https://learn.microsoft.com/microsoftteams/platform/toolkit/add-capability)
- [Use an existing Microsoft Entra application](https://learn.microsoft.com/microsoftteams/platform/toolkit/use-existing-aad-app)
- [Customize the Teams app manifest](https://learn.microsoft.com/microsoftteams/platform/toolkit/teamsfx-preview-and-customize-app-manifest)
- Host your app in Azure by [provision cloud resources](https://learn.microsoft.com/microsoftteams/platform/toolkit/provision) and [deploy the code to cloud](https://learn.microsoft.com/microsoftteams/platform/toolkit/deploy)
- [Collaborate on app development](https://learn.microsoft.com/microsoftteams/platform/toolkit/teamsfx-collaboration)
- [Set up the CI/CD pipeline](https://learn.microsoft.com/microsoftteams/platform/toolkit/use-cicd-template)
- [Publish the app to your organization or the Microsoft Teams app store](https://learn.microsoft.com/microsoftteams/platform/toolkit/publish)
- [Enable the app for multi-tenant](https://github.com/OfficeDev/TeamsFx/wiki/Multi-tenancy-Support-for-Azure-AD-app)
- [Preview the app on mobile clients](https://github.com/OfficeDev/TeamsFx/wiki/Run-and-debug-your-Teams-application-on-iOS-or-Android-client)
