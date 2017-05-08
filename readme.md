# WP Shuttle for Automatic Plugin Deployments

You need to specify the following environment variables which are used for deploying to the WordPress plugin SVN repository:

- `WP_ORG_SLUG`
- `WP_ORG_USERNAME`
- `WP_ORG_PASSWORD`

## Getting Started

1. Add `kaspars/wp-shuttle` as a developer dependency to your project:

	$ npm install kaspars/wp-shuttle --save-dev

2. Update the Travis CI build script to deploy your repository.

3. Use `.svnignore` to exclude files and folders from the deployment.
