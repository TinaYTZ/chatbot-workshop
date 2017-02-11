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
  - Get the App Secret in Settings tab on `developers.facebook.com`
  - Get `pageAccessToken` from Messenger -> Settings
  - For `validationToken`, you can put be whatever you want
  - For `serverURL`, you have to tunnel your localhost. If you have installed ngrok on your computer, type `ngrok http 3333` in the terminal. `3333` is the default port that you specify in your server.
  - You can ignore the last field for now.
  
2. Set up webhook
  - Go to Product -> Messenger -> Webhooks
  - Fill in your ngrok url with the `\webhook` route. Example: `https://d9d7d46e.ngrok.io/webhook`
  - Fill in your `validationToken` specified in step 1
  - Subscripe the webhook with a page
  
## Development

### Receiving a message from messenger
Open file `basic-receiver.js` and start exploring. This is a mini server I created with the code from `app.js`. Look down to `app.post` and follow the workshop. 

[Format of the data Facebook send us](https://developers.facebook.com/docs/messenger-platform/webhook-reference#format)

### Sending a message to messenger
Open file `basic-sender.js` and copy all the code over `basic-receiver.js`. The code is from FB and it gives us a really good black box to use. If you want to explore more about sending messages to the bot, check out [here](https://developers.facebook.com/docs/messenger-platform/send-api-reference).

### Adding AI (wit.ai)
Adding an AI is complicated because wit.ai and Messenger, although from the same company, their code are a bit different. So, you have to marge them together. For this section, please open `basic-ai.js`.

More documentation [here](https://wit.ai/docs)

## Deployment

### Setting up Heroku
- Install heroku and then login `heroku login`
- `cd` to your git and `heroku create`
- Go on to heroku website, get the url, and change it inside your config file, `default.json`
- Heroku will use `npm start`, so set to script in your `package.json` file accordingly
- Deploy to the server with `git push heroku master`

Note: If you want a newer version of Node on Heroku, edit your `package.json` file
```
"engines": {
  "node": "~4.1.2"
}
```

[Getting Started on Heroku with Node.js](https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up)

### Getting to the public
Your messenger bot is still in development. That means, other people other than yourself cannot talk to it. It will not response to anyone other than the admins. You can add more contributors to the App in Settings or you can get it approved for the public [here](https://developers.facebook.com/docs/messenger-platform/app-review).

## More tutorials + links

- [Official Facebook's Walk-through](https://developers.facebook.com/docs/messenger-platform/quickstart)
- [The Complete Guide](https://developers.facebook.com/docs/messenger-platform/implementation)
- [Facebook Dev Site](https://developers.facebook.com/docs/messenger-platform/)

## Contact

If you need help, find me on [Facebook](https://www.facebook.com/minhhoangtcu) or on Slack.
