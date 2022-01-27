# Ticket Viewer

To run the project, the required node modules will need to be installed. To do this, use the following command:

        $ npm install

    This command will install the required dependencies as listed in the package.json

## Using the application

This project requires user account information to be entered into the `.env` file, prior to starting the server.

Within the project's root folder, open the `.env` file and enter the following:
    
1. Set `ZENDESK_API_USER` to your Zendesk account username 
2. Set `ZENDESK_API_PASS` to your Zendesk account password 
2. Set `ZENDESK_API_DOMAIN` to your Zendesk account domain

By default I have made the account and used the api.

Once these have been entered, save the file. 

To run the project, start the server by running the command
    
    $ npm start

The project will run on localhost:8080

# Testing

This project uses Jest for the testing framework. To run the tests, run the following command:

    $ npm test


# Implimentation

- The front end of the app is built using HTML and CSS. 
    - JQuery was used to provide the show/hide feature of the tickets details.
- The backend of the app was driven by NodeJS using the Express web framework. 
    - [Axios](https://github.com/axios/axios) is used as the http client
    - [Jest](https://jestjs.io/) is used as the testing framework
    - [Dotenv](https://www.npmjs.com/package/dotenv) is used to handle the authentication. I decided to utilize using environment variables as opposed to creating a login page. I understand that this is not what I would use if built for production. But for a coding challenge like this where my account information has to be shared, I believe using a configuration file such as .env and utilizing environment variables is sufficient.

## UI
The application's UI was kept simple and minimalistic.
- Home Page
    - Button to view tickets. Clicking this will initiate the API call to gather tickets 
- Tickets
    - Displays (upto) 25 tickets on the page. 
    - If there are more tickets, a `next` button is displayed at the bottom of the page. When clicked, a call is made to request the next batch of tickets.
    - Conversely, a `previous` button is displayed if it is possible to view the previous set of 25 tickets.
    - Clicking on the Ticket's Subject title will expand to show more details about that particular ticket. The ticket's status and description are displayed.
- Errors
    - If a route does not exist, then a page is rendered to inform the user.
    - If the API is down, then a page is rendered with the status and status text from the API
