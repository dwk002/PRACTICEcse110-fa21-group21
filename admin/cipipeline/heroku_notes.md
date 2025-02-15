# Node.js deployment in Heroku!
### Written by - Do James Kim

**Tutorial Link**
[Heroku, Getting started with Node.js](https://devcenter.heroku.com/articles/getting-started-with-nodejs)

## Deploying
1. Create an app on Heroku, which prepares Heroku to receive your source code. 
> `$ heroku create`
2. Now deploy your code:
> `$ git push heroku main`
3. The application is now deployed. Ensure that at least one instance of the app is running:
> `$ heroku ps:scale web=1`
4. Now visit the app at the URL generated by its app name. As a handy shortcut, you can open the website as follows:
> `$ heroku open


## Define a Procfile

1. Heroku apps include a [Procfile](https://devcenter.heroku.com/articles/procfile)
that specifies the commands that are executed by the app on startup. 
You can use a Procfile to declare a variety of process types, including:
the Procfile in the example app you deployed looks like this:
> `web: npm start`
This declares a single process type, `web`, and the command needed to run it. The name `web` is important here. 
It declares that this process type will be attached to the HTTP routing stack of Heroku, and receive web traffic when deployed. 
This command will use the `start` script that is specified in the `package.json.`
- Tasks to run before a [new release is deployed](https://devcenter.heroku.com/articles/release-phase)


## Declaring Dependencies
1. Heroku recognizes an app as Node.js by the existence of a `package.json` file in the root directory. For your own apps, you can create one by running 
> `$ npm init --yes`

2. Run this command in your local directory to install the dependencies, preparing your system for running the app **locally:**
> `$ npm install`
>  >  Note: When an app is deployed, Heroku reads the `package.json` to install the appropriate node version and the `package-lock.json` to install the dependencies.

3. Now start your application locally using the heroku local command, which was installed as part of the Heroku CLI:
> `$ heroku local web`
>  > Note: Just like Heroku, heroku local examines the Procfile to determine what to run.
>  > Open http://localhost:5000 with your web browser. You should see your app running locally.
>  > To stop the app from running locally, in the CLI, press `Ctrl+C` to exit.

 






4. Create `index.js` file inside project directory.
> Current Status of root directory:
> 
> ![image](https://user-images.githubusercontent.com/60757227/142718793-da10db67-7883-464e-89ab-ceb8d99773aa.png)
