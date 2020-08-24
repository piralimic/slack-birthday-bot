# Slack Birthday Bot

The purpose of this bot is to send a message to your team's Slack when is someones birthday.


## Setup & Deploy

### Heroku

1. Clone this repo to a desire location at your own computer
2. Get your [Incoming Webhook URL](https://api.slack.com/incoming-webhooks) from Slack
3. Save the url at `configurations.json` file and fill in the rest of the configurations as you like
4. Set your birthdays list using the format `FirstName LastName YY MM DD` at the `birthdays.txt` file
5. Create a blank app at Heroku
6. Push your code to Heroku
7. The bot was developed with the **2.2.6** version of ruby, any other versions may require changes.
7. Run `heroku addons:create scheduler:standard` to add the Scheduler add-on to your deploy
8. Run `heroku addons:open scheduler` to configure the scheduler
9. Click **Add a new job** and type `rake congratulate` as the command
10. Set frequency to **Daily** and choose the **Time** you want to be notified

### Custom Server

1. Clone this repo to a desire location at your own server
2. Get your [Incoming Webhook URL](https://api.slack.com/incoming-webhooks) from Slack
3. Save the url at `configurations.json` file and fill in the rest of the configurations as you like
4. Set your birthdays list using the format `FirstName LastName YY MM DD` at the `birthdays.txt` file
5. Run `crontab -e` to edit your crontab
6. Add this line to the crontab and save it: `0 9 * * * cd /clone/location && /usr/local/bin/rake congratulate` (replace `/clone/location` by the location where you cloned the repo)


## Contributors 

This project was originally created by [Tiago Botelho](https://github.com/tiagonbotelho), while he was an intern at [jeKnowledge](http://jeknowledge.pt/).

It was later revised by [Diogo Nunes](http://www.diogonunes.com/) from [EqualExperts](https://www.equalexperts.com/) and [João Bernardo](http://jbernardo.me) from [jeKnowledge](http://jeknowledge.pt/).

## License

This project is licensed under the terms of the MIT license.
