# Mozilla Foundation – Engineering Guidebook

An overview of the best practices for the Mozilla Foundation engineering team.

## The Stack

**Note**: The following are guidelines for *new* projects and aren't guaranteed to be in place for legacy codebases.

### Front-end

#### React

[React](https://facebook.github.io/react/) is our preferred library for building UI on both web sites and applications.

#### npm

We use [npm](https://www.npmjs.com/) as both a package manager and a [task runner](http://blog.keithcirkel.co.uk/how-to-use-npm-as-a-build-tool/).

#### Webpack

**TODO**

#### Bootstrap & Sass

We use a custom Bootstrap theme known as [mofo-bootstrap](https://github.com/mozilla/mofo-bootstrap) as a CSS framework and utilize the Sass CSS preprocessor with the SCSS syntax.

### Back-end

**TODO**

## Coding Standards

We enforce our coding standards with automated tooling ("linters"), that are usually tied to Travis. Failure to pass the linter (usually by running `npm test`) will result in a broken build. Your code should not be merged until all tests are passing.

Refer to [Mofo Style](https://github.com/MozillaFoundation/mofo-style) for more info.

## GitHub Flow

Active projects and future projects will use GitHub flow for branching. This means that new features should be written in feature branches based on `master`. When ready, open a pull request against `master` to have the new feature (or fix) brought into the base branch. Branches should only merge into master when fully completed, so other people's work is never blocked.

For more details, see: [https://guides.github.com/introduction/flow/](https://guides.github.com/introduction/flow/)

**NOTE**: The decision to standardize GitHub flow on Mozilla Foundation projects was made In August 2016. Therefore, you can expect to find some projects that have yet to be updated to use GitHub flow. You will be able to identify these projects by checking what the base branch of the repository it. If it is `develop` you should use [Git Flow](http://nvie.com/posts/a-successful-git-branching-model), otherwise, use GitHub flow.

## Code Review

Prior to landing a pull request in one of our repositories we require at least one developer to peer review your code.

On GitHub our repos should have the following labels (click [here](https://github.com/MozillaFoundation/mofo-standards/labels) for the canonical list of labels with their coloring):

- `PR – Needs Review`
- `PR – Needs Work`
- `PR – Good To Merge`

When you make a PR, add the label `PR – Needs Review` and assign to another developer to conduct the review. Once a reviewer has completed their evaluation they will replace the label with either `PR – Needs Work` if changes are necessary, or `PR – Good To Merge` if the code is safe to be merged. The ticket should then be assigned back to the author.

If you get a `PR – Needs Work` response, then you can make the requested changes and repeat the same process as outlined above.

If your PR is "good to merge", then you can go ahead and merge it! If your PR has multiple commits please squash them to a single descriptive commit that explains what your patch does (and *why* if applicable). If your PR is related to a GitHub issue, it's good practice to also include that number in the commit message (eg: `Resolves #342`).

## Deployment

We use webhooks to trigger automatic deployments to staging environments from the master branch. Production deployments will be performed manually by project members given the right permissions to do so. See the project specific documentation for details on an application's deployment pipeline.

## Internal Libraries

- [Mofo Bootstrap](https://github.com/mozilla/mofo-bootstrap)
- [Mofo UI](https://github.com/mozilla/mofo-ui)
