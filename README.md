# Text-to-Image

This project uses the Stable Diffusion Pipeline to generate images from text prompts. The Stable Diffusion Pipeline is a machine learning model that uses a diffusion process to generate images from text prompts. This is a simple GUI application for generating images based on user prompts.

[![Deploy to DO](https://www.deploytodo.com/do-btn-blue.svg)](https://cloud.digitalocean.com/apps/new?repo=https://github.com/aksprat/text-to-image/tree/main)


## Table of Contents

- [Requirements](#requirements)
- [Description](#description)
- [Setting Up Hugging face Account](#HuggingFace Account Setup)
- [Usage](#usage)
- [License](#license)

## Requirements

- You need a DigitalOcean account. If you do not already have one, first [sign up](https://cloud.digitalocean.com/registrations/new?utm_team=devrel&utm_source=github&utm_content=signup).

- HuggingFace [account](https://huggingface.co/)

- [Stable Diffusion Model](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0)

## Description

When you run the code, you will be prompted to enter a text prompt. Once you have entered a text prompt, the Stable Diffusion Pipeline will generate an image based on the text prompt. The generated image will be displayed using matplotlib.

This [sample app](https://oyster-app-rpxke.ondigitalocean.app/) demonstrates how to use React in a NextJS app to create a search and filter feature for a list of _some_ aquariums in the United States. The app uses the `useState` hook to filter the list of aquariums based on the user's input in the search bar.

The [sample app](https://oyster-app-rpxke.ondigitalocean.app/) combines [DigitalOcean's MongoDB Managed Database](https://www.digitalocean.com/products/managed-databases-mongodb?utm_team=devrel&utm_source=github&utm_content=managed-databases-mongodb) and Compass to store the list of aquariums and is mapped over and displayed using [Material UI components](https://mui.com/material-ui/).

[Autoscaling](https://www.digitalocean.com/blog/introducing-cpu-based-autoscaling-app-platform?utm_team=devrel&utm_source=github&utm_content=blog) is also enabled in the deployed app to ensure that the app can handle increased traffic. To learn more about autoscaling, see the [Autoscaling video from Bikram Gupta](https://www.youtube.com/watch?v=k8pCGYPeqOQ).

## HuggingFace Account Setup

To run this file you need a HuggingFace API Token.

1. Go to the Hugging Face [website](https://huggingface.co/)
2. Click on the "Sign In" button in the top-right corner of the page.
3. Sign in with your Hugging Face account or create a new account if you don't have one.
4. Once you are signed in, click on your profile picture in the top-right corner of the page and select "Account settings" from the dropdown menu.
5. On the account settings page, click on the "API token" tab.
6. Click on the "Generate new token" button to create a new authorization token.
7. Enter a name for your token in the "Token name" field (e.g. "Image Generator App").
8. Choose the permissions you want to grant to your token (e.g. "Read-only" or "Full access").
9. Click on the "Generate" button to create your token.
10. Copy the generated token and use it in your Python code where it says self.authorization_token = "".

### Deploy the App

Click the following button to deploy the app to App Platform. If you are not currently logged in with your DigitalOcean account, this button prompts you to to log in.

Once in the console you can choose other services such as Database, Droplets, Autoscaling, and more!

Note that, for the purposes of this tutorial, this button deploys the app directly from DigitalOcean's GitHub repository, which disables automatic redeployment since you cannot change our template. If you want automatic redeployment or you want to change the sample app's code to your own, we instead recommend you fork [our repository](https://github.com/do-community/us-aquarium-search/tree/main).

To fork our repository, click the **Fork** button in the top-right of [its page on GitHub](https://github.com/do-community/us-aquarium-search/tree/main), then follow the on-screen instructions. To learn more about forking repos, see the [GitHub documentation](https://docs.github.com/en/github/getting-started-with-github/fork-a-repo).

After forking the repo, you can view the same README in your own GitHub org; for example, in `https://github.com/<your-org>/us-aquarium-search`. To deploy the new repo, visit the [control panel](https://cloud.digitalocean.com/apps) and click the **Create App** button. This takes you to the app creation page. Under **Service Provider**, select **GitHub**. Then, under **Repository**, select your newly-forked repo. Ensure that your branch is set to **main** and **Autodeploy** is checked on. Finally, click **Next**.

After clicking the **Deploy to DigitalOcean** button or completing the instructions above to fork the repo, follow these steps:

1. Configure the app, such as by specifying HTTP routes, declaring environment variables, autoscaling setup, or adding a database. For the purposes of this tutorial, this step is optional.
2. Provide a name for your app and select the region to deploy your app to, then click **Next**. By default, App Platform selects the region closest to you. Unless your app needs to interface with external services, your chosen region does not affect the app's performance, since to all App Platform apps are routed through a global CDN.
3. On the following screen, leave all the fields as they are and click **Next**.
4. Confirm your plan settings and how many containers you want to launch and click **Launch Basic/Pro App**.

After, you should see a **"Building..."** progress indicator. You can click **View Logs** to see more details of the build. It can take a few minutes for the build to finish, but you can follow the progress in the **Deployments** tab.

Once the build completes successfully, click the **Live App** link in the header and you should see your running application in a new tab, displaying the home page.

### Local Installation (fork)

To install the project, follow these steps:

1. Fork the repository
2. Install the dependencies:

```bash
npm install
```

3. If you are planning on using MongoDB (setup code already in app), make sure to set up the `env` variables so your local development works. Once in the console you will have to set that same `env` variable for the app to build.
   There is a `.env.example` file set up for your MongoDB Connection String if you choose to use it:

```js
MONGODB_URI = '';
```

Run the development server:

```bash
npm run dev
```

## Usage

This sample app uses [NextJS](https://nextjs.org/) and can modified to include any data set that you would like to filter and search through.

### CSS

The CSS can also be modified to fit your design preferences. If you choose to use another CSS framework, you can remove the [Material UI components](https://mui.com/material-ui/) and replace them with the components from the framework you choose.

### Database

You are not limited to **ONLY** using MongoDB but if you do, make sure to set up your MongoDB database and connect it to your app. You can use [MongoDB Compass](https://www.mongodb.com/products/tools/compass) to add the data to your database. MongoDB will not be setup by default, you will have to set up your own database. MongoDB it is not considered a dev database in this case. The video below shows how to setup and add the Mongo instance to your app.

Make sure to add your trusted sources to your database. For more information about that, check out the [How to Secure MongoDB Managed Database Clusters](https://docs.digitalocean.com/products/databases/mongodb/how-to/secure/) docs.

Next to the top of the page where it says "test-db" it says **"Creating..."**. The db is being proivisioned and could take a few minutes. Once it is complete, your db will be ready.

https://github.com/do-community/us-aquarium-search/assets/6799474/a768ea6a-a951-48f6-a026-51733f323c66

If you choose to use another database platform, you can modify the code to connect to your database. To learn more about our Managed Databases, see the [Managed Databases documentation](https://www.digitalocean.com/products/managed-databases?utm_team=devrel&utm_source=github&utm_content=managed-databases).

### Autoscaling

The sample app has autoscaling enabled in the resources. If you choose to use autoscaling, you must have a dedicated instance for the feature to work. By choosing the $49/month dedicated instance, the autoscaling feature is unlocked. You don't have to choose the $49 service, there are cheaper options. This is just for the sample app.

You can set the minimum and maximum container size as well as the CPU Threshold % as you can see by the image below.

![autoscale-screenshot](https://github.com/do-community/us-aquarium-search/assets/6799474/9f7b9781-4451-4af1-a28e-d07528921e6a)

I tested the autoscaling feature by running a load test (200,000 requests) on the app using [hey](https://github.com/rakyll/hey). The app was able to handle the increased traffic and the containers scaled up to meet the demand.
![autoscale feature in app platform](https://github.com/do-community/us-aquarium-search/assets/6799474/ede9c2d5-ef27-40ea-99c0-63fa63cd4a9f)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

