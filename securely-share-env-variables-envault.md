# Securely share .env variables with Envault

Almost every October CMS app is enriched with third party services.

Payment gateways such as Stripe, real-time communication platforms like Pusher, and authentication providers like GitHub are just a few of the many tools that developers use for their apps. These pose a challenge, though, as teams everywhere face a common problem during development - keeping everyone up to date with the latest API keys to use.

People often turn to Slack in this situation. Just send your .env file around, and you're sorted, right? Well, not really. While being insecure, this gets very confusing for teams working on multiple apps, all with credentials that are updated regularly, alongside new developers who need to gather their .env from scratch. Surely there's an easier way?!

## Introducing Envault

[Envault](https://envault.dev/?utm_source=october_news&utm_medium=article&utm_campaign=envault_launch) is a self-hosted app that holds your team's .env credentials for every project. It lets you update your variables, and immediately push the changes out to your whole team, ready to be downloaded with a single command.

<iframe src="https://player.vimeo.com/video/414894566" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

Using Envault variables in your project is easy. Our NPX CLI means that you don't need to install anything locally. Simply copy the setup command from your Envault dashboard, run it in your project directory, and you're ready to go. After you've set up the first time, downloading future .env updates is as easy as running `npx envault`. Envault doesn't just help with your October CMS projects. Any project that uses a .env file can use Envault to sync its credentials in the same way.

Envault has many powerful features, including...
- A complete history of all your credentials, which you can use to easily roll back to a previous version
- Automatic notifications through Slack, letting your team know when an .env update is ready to download
- A flexible permissions system to easily control developer access to different credentials
- An audit log that records any changes made to your Envault

## Convinced?
[Envault](https://envault.dev/?utm_source=october_news&utm_medium=article&utm_campaign=envault_launch) is just $49 to download and use forever, with the license covering your whole team and all your projects. You'll get support from the Envault team whenever you need it, and new feature updates for a year. Envault is built on Laravel 7, so it's dead simple to install on your own server. We've even published [step-by-step setup guides](https://docs.envault.dev/collection/12-setting-up-envault) on our documentation website.

Make sure to [follow us on Twitter](https://twitter.com/envaultapp) for all our latest updates. If you have any questions, feedback or just want to show us some love, drop an email to hello [at] envault [dot] dev. We'd love to hear from you!
