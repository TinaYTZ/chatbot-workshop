# HackMerced Chatbot Workshop
This is a sample project used for HackMerced Workshop. 

## What you need

- [NodeJS](https://nodejs.org/en/)
- [Ngrok](https://ngrok.com/)
- A Facebook account
- Hype

## How it work

![System Architecture](http://i.imgur.com/BeSLBtw.png)

In deployment, our server will be on [Heroku](https://www.heroku.com/). However, since we will spend most of our time in development, we will use `ngrok` to tunnel our localhost instead.

## Setting up

1. Config our Node server
  - Get the App ID and App Secret in Settings tab on `developers.facebook.com`
  - For `validationToken`, you can put be whatever you want
  - For `serverURL`, you have to tunnel your localhost. If you have installed ngrok on your computer, type `ngrok http 5000` in the terminal. `5000` is the default port that you specify in your server.
  
2. Set up webhook
  - Go to Product -> Messenger -> Webhooks
  - Fill in your ngrok url with the `\webhook` route. Example: `https://d9d7d46e.ngrok.io/webhook`
  - Fill in your `validationToken` specified in step 1
  - Subscripe the webhook with a page

## More tutorials + links

- [Official Facebook's Walk-through](https://developers.facebook.com/docs/messenger-platform/quickstart)
- [The Complete Guide](https://developers.facebook.com/docs/messenger-platform/implementation): it goes deeper into the features available.
- [Facebook Dev Site](https://developers.facebook.com/docs/messenger-platform/)
