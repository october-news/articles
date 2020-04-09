Many apps connect to third party services to enrich their features. These almost always require authentication via a key of some form.
As October CMS developers, these keys inevitably end up getting dumped in our site’s .env file.

While not so bad when you’re working solo on a site, this practice makes teamwork a nightmare. .env files get tossed around on Slack as a way of sharing credentials. Developers get confused as to why their environment is breaking, only to discover that *someone...* changed the keys and didn’t tell anyone! They then need to find out who has the most recently updated key, and what it is, before they can work.

![Man looking at objects](https://s.ocdnx.com/october-news.com/public/5e8/f8b/999/5e8f8b99919fe333593552.png)

## Introducing Envault

[Envault](https://envault.dev/) is a platform to manage and sync your teams’ local .env variables. We currently have packages available for both [October CMS](https://github.com/envault/oc-plugin) and [Laravel](https://github.com/envault/laravel) apps, with more in the pipeline. Let’s take a look at how easy it is to get started.

### Inviting a team member

Envault is centred around sharing, so teams are at the heart of the app. When you sign up, a “Personal” team is created for you. Let’s invite someone else to it.

![Inviting a user to your team.](https://s.ocdnx.com/october-news.com/public/5e8/f8c/2d0/5e8f8c2d0bd42850781657.gif)

*Inviting a user to your team.*

Simple! They’ll now receive an email with a link through which they can join your team.

### Adding your first app

Having team members is all good, but you have nothing to collaborate on at the moment. Enter: apps. Start by adding an app to your team. Let’s call it “Restaurants Near Me”: your latest October site to take the internet by storm.

![Adding an app to your team.](https://s.ocdnx.com/october-news.com/public/5e8/f8c/566/5e8f8c5662866350846610.gif)

*Adding an app to your team.*

Cool! That’s all set up.

### Storing your credentials online

It’s what we’re all here for, right? Let’s create two variables to connect to Stripe with.

![Adding credentials to your app.](https://s.ocdnx.com/october-news.com/public/5e8/f8c/771/5e8f8c7719309341338970.gif)

*Adding credentials to your app.*

Neat! We now have a virtual .env file. Let’s connect it to our October site.

### Setting up Envault locally

We’ve installed the `envault/oc-plugin` package to our project. Let’s connect it to our Envault app by running the setup command.

![Setting up your Envault app locally.](https://s.ocdnx.com/october-news.com/public/5e8/f8c/944/5e8f8c944ef4d229922216.gif)

*Setting up your Envault app locally.*

Watch how it syncs the variables automatically. It’s a thing of beauty.

### Updating credentials

Let’s update one of our online credentials.

![Updating a credential and syncing it.](https://s.ocdnx.com/october-news.com/public/5e8/f8c/b0e/5e8f8cb0e6dde782160683.gif)

*Updating a credential and syncing it.*

Whenever a variable is updated online, your team can simply run `php artisan envault:update` and their .env is updated. It’s as simple as that!

Envault version controls all variables, so rolling back to a previous version through the dashboard is easy!

![Rolling back to a previous version of the credential.](https://s.ocdnx.com/october-news.com/public/5e8/f8c/ca9/5e8f8cca9a8ad054396952.gif)

*Rolling back to a previous version of the credential.*

## So how does this actually work?

When you `envault:setup` an October site, an .envault.yml file is created in your project root. This file stores the app’s ID, and a personal authentication token that `envault:update` uses to retrieve subsequent updates. Each team member’s authentication token is unique to them and works as long as they remain a member of the app’s team.

## What features have we planned for version 1?

We’ve just released [Envault Beta](https://app.envault.dev/), which is completely free to use. We’re planning on launching subscriptions alongside version 1, but will always have a basic free plan for you to use on your projects. Here’s a few new features we’re working on right now -
* Importing and exporting your variables in .env format.
* Slack / email notifications for your team for when an .env update is available.
* An audit log to track who changed what, when.
* A directory of open source integrations of Envault with various frameworks.
* Logging in to your Envault account through the CLI, so you can `envault:setup` your environment without having to leave your IDE.
* Locally excluding variables from sync jobs.

## A final note

Please spread the word about Envault to your friends and colleagues on [social media](https://twitter.com/EnvaultApp)! We’d really appreciate it.

If you have any questions, feedback or just want to show us some love, drop us an email on hello [at] envault.dev. We’d love to hear from you!
