# README

### Setup Instructions
This following steps are instructions to launch and view a simple Python Flask application that authenticates with Procore's API using the OAuth 2.0 Authorization Code Grant Type flow. The application is configured to access either Procore's production environment or Procore's developer sandbox environment.

THIS REPOSITORY IS FOR TRAINING PURPOSES ONLY.

1. Clone this repository
2. If you do not have Python 3, Download and Install Python 3 (Recommended version >=3.7) from `https://www.python.org/downloads/`. If you are unsure which version you have, type `python3 --version` or `python --version` into the terminal. 
3. If you do not have `pip` currently installed, run `python3 -m pip install -U pip`. If you do have pip installed, make sure  `pip` is referncing Python 3 by 
4. If you have `pipenv` installed skip this step,  otherwise run `pip install pipenv`. It is important that pipenv 
5. Navigate to the `python-oauth-sample` folder in the command line and run `pipenv install`.
6. Navigate to the `.env.example` file in the root directory of the project. Rename the file to `.env`.

Within this file, configure your application's Client ID, Client Secret, Redirect URI, OAuth URL, and Base URL in order to save these as the application's environment variables:

        * CLIENT_ID: 
        * CLIENT_SECRET: 
        * REDIRECT_URI: http://localhost:3000/users/home
        * OAUTH_URL: https://login.procore.com
        * BASE_URL: https://api.procore.com

    * Client ID and Client Secret values are provided when [creating an application](https://developers.procore.com/documentation/new-application) in the Procore Developer Portal. The redirect URI above should be added to your application, which can be done on your application's home page.
    * The BASE_URL and the OAUTH_URL will depend on which environment you're working accessing. If you're working in the production environment, the OAUTH_URL will be https://login.procore.com and the BASE_URL will be https://api.procore.com. For the sandbox environment, both the OAUTH_URL and the BASE_URL should be set to https://sandbox.procore.com.
    * After these values have been configured within the `.env` file, make sure to save your changes.

7. Remember to add the REDIRECT_URI to the to your application's configuration page. 
7. From the command line, `pipenv run python3 app.py` while you are in the `python-oauth-sample` folder. Open a web browser and navigate to "localhost:3000" using the address bar. 
8. The landing page will include a button that says, "Sign In to Procore". Click this button and enter your Procore email address/password.
9. After authenticating with Procore, you will be redirected back to the sample application. This page will include a table containing the first and last five characters of both your access token and your refresh token. In addition, there will be timestamps corresponding to when the access token was generated and when it expires (2 hours after generation).
10. To access the data returned by the [Show User Info](https://developers.procore.com/reference/me) endpoint, click on the "Show User Information" button on the home page. 
11. To refresh your access token, click on the "Refresh Access Token" button. Notice that the corresponding values will be updated in the table on the home page.
12. To revoke your access token, click on the "Revoke Access Token" button. This will remove your access token and return you to the sign in homepage. 
If you have any questions regarding this application's code or functionality, please reach out to apisupport@procore.com.
