[![Netlify Status](https://api.netlify.com/api/v1/badges/d5fa9df7-6ad3-4518-b1fd-5df145df6b5c/deploy-status)](https://app.netlify.com/sites/dreamy-lalande-35da01/deploys)

## Getting started with SvelteJS v3

This is a simple web using [Svelte](https://svelte.dev) from [svelte-starter-template](https://github.com/Holben888/svelte-starter-template.git) and [svelte-template](https://github.com/sveltejs/template). To get going, make sure we have [NodeJS](https://nodejs.org/en/) and [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) installed.

...install all project dependencies...

```
npm install
```

...and build the application.

```
npm run dev
```

For the above commmand, file `rollup.config.js` imports for "live-reload" and "serve." These allow the website to rebuild itself automatically when you add new code.

To create an optimised version of the app:
```
npm run build
```
We can run the newly built app with `npm run start`. This uses sirv, which is included in the package.json's dependencies so that the app will work when you deploy to platforms like Heroku.

## Next steps

Visit the [documentation page](https://svelte.dev/docs) for SvelteJS! :smiley:

[<img src="https://www.netlify.com/img/deploy/button.svg">](https://app.netlify.com/start/deploy)
