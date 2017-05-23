# WP Shuttle for Automatic Plugin Deployments

## Getting Started

1. Add `kasparsd/wp-shuttle` as a developer dependency to your project:

		$ npm install --save-dev kasparsd/wp-shuttle

2. Update the Travis CI build script to deploy your repository.

3. Use `.svnignore` to exclude files and folders from the deployment.

You need to specify the following environment variables which are used for deploying to the WordPress plugin SVN repository:

- `WP_ORG_SLUG`
- `WP_ORG_USERNAME`
- `WP_ORG_PASSWORD`
