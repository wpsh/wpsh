<img src="https://kaspars.net/wp-content/uploads/2017/06/wp-shuttle.png" height="100" alt="WP Shuttle Logo" />

# WP Shuttle for Automatic Plugin Deployments

## Getting Started

1. Add `wpsh/wpsh` as a developer dependency to your project:

		$ npm install --save-dev wpsh/wpsh

	Run `npm init` if your project is missing the `package.json` file.

2. Add `wpsh` to the `scripts` section of the `package.json` file:

		"scripts": {
		  "wpsh": "wpsh"
		}

3. Use `npm run wpsh` to run the WP Shuttle script.

To run it as `wpsh` instead of `npm  run wpsh` you should add path to the local npm `bin` folder to the `$PATH` environment variable by appending the following to `~/.bashrc` or `~/.zshrc`:

	export PATH="./node_modules/.bin:$PATH"

and restart the shell to trigger the change.


## Automatic Deployments with Travis CI

1. Update the Travis CI config `.travis.yml` to deploy your plugin when committing to `master` and tagging a release:

		deploy:
		  - provider: script
		    script: npm run wpsh $TRAVIS_TAG
		    on:
		      tags: true
		  - provider: script
		    script: npm run wpsh trunk
		    on:
		      branch: master

2. Specify the following environment variables in the [Travis CI repository settings](https://docs.travis-ci.com/user/environment-variables/#Defining-Variables-in-Repository-Settings) for deploying to the WordPress plugin SVN repository:

	- `WP_ORG_SLUG`
	- `WP_ORG_USERNAME`
	- `WP_ORG_PASSWORD`

3. Use `.svnignore` to exclude files and folders from the deployment.
