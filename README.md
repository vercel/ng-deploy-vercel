<!-- ![](https://assets.zeit.co/image/upload/v1561740077/repositories/ng-deploy-now/ng-deploy-now.png)
[![NPM version](https://img.shields.io/npm/v/@zeit/ng-deploy.svg)](https://www.npmjs.com/package/@zeit/ng-deploy)
[![Join the community on Spectrum](https://withspectrum.github.io/badge/badge.svg)](https://spectrum.chat/zeit/now)
 -->
Deploy Angular applications to [Vercel](https://vercel.com/home)

## Quick start

1. Install the latest version of Angular cli

   ```sh
   yarn global add @angular/cli
   ```

1. Create a new Angular project

   ```sh
   ng new hello-world --defaults
   cd hello-world
   ```

1. Add `ng-deploy` to your project

   ```sh
   ng add @vercel/ng-deploy
   ```

1. You will be prompt to log in to [Vercel](https://vercel.com/home) account

1. Deploy your project to `Vercel`

   ```sh
   ng run hello-world:deploy
   ```

After deploying your application you will see output similar to the following:

```
Your application is deployed at https://hello-world-1234.vercel.app
```

## Usage

You can adjust your deployment with options.

The available options are:

- `--configuration` (`-c`) - A named build target, as specified in the "configurations" section of angular.json
- `--scope` (`-s`) - Scope [user or team](https://vercel.com/docs/cli#options/global-options/scope) under which the project will be deployed
- `--force` (`-f`) - Force a new deployment even if nothing has changed
- `--target` (`-t`) - Deploy to either 'staging' or 'production' aliases
- `--no-build` - Skip build process during deployment

Example:

```sh
ng deploy --scope vercel
```

## Development

If you want to try the latest package locally without installing it from npm, use the following instructions. This may be useful when you want to try the latest non published version of this library or you want to make a contribution.

### yarn link

Use the following instructions to make ng-deploy-vercel available locally via `yarn link`.

1. Clone the project

   ```sh
   git clone https://github.com/vercel/ng-deploy-vercel
   cd ng-deploy-vercel
   ```

1. Install the dependencies

   ```sh
   yarn install
   ```

1. Build the project:

   ```sh
   yarn run build
   ```

1. Create a local yarn link:

   ```sh
   yarn link
   ```

### Adding to an Angular project - ng add

Once you have completed the previous steps to yarn link the local copy of ng-deploy-now, follow these steps to use it in a local angular project.

1. Enter the project's directory

   ```sh
   cd your-angular-project
   ```

1. To add the local version of @zeit/ng-deploy, link @zeit/ng-deploy.

   ```sh
   yarn link @zeit/ng-deploy
   ```

1. You may be prompted you to sign in to Now.

1. Then, instead of running `ng add @zeit/ng-deploy`, add the local version.

   ```sh
   ng add @zeit/ng-deploy
   ```

1. Now you can deploy your angular app to Now.

   ```sh
   ng run your-angular-project:deploy
   ```

> You can remove the link later by running `yarn unlink`
