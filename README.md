[![Uses Mofo Standards](https://MozillaFoundation.github.io/mofo-standards/badge.svg)](https://github.com/MozillaFoundation/mofo-standards)

# Mozilla Foundation – Engineering Standards

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

## License

Make sure every repo contains an [MPL 2.0](https://www.mozilla.org/en-US/MPL/) `LICENSE` file. This `LICENSE` file can be added by selecting "Mozilla Public License 2.0" when you create a new repo on GitHub.

For every npm-managed project, `"license" : "MPL-2.0"` should be included in the `package.json` file.

## Publishing to npm

When publishing a shared library to npm, be sure to include `mozillafoundation` as a collaborator. This ensures that ops has access to administrate the module if necessary.

## GitHub Flow

Active projects and future projects will use GitHub flow for branching. This means that new features should be written in feature branches in the same repo, branched from `master`. When ready, open a pull request against `master` to have the new feature (or fix) brought into the base branch. Branches should only merge into master when fully completed, so other people's work is never blocked.

For more details, see: [https://guides.github.com/introduction/flow/](https://guides.github.com/introduction/flow/)

**NOTE**: The decision to standardize GitHub flow on Mozilla Foundation projects was made In August 2016. Therefore, you can expect to find some projects that have yet to be updated to use GitHub flow. You will be able to identify these projects by checking what the base branch of the repository it. If it is `develop` you should use [Git Flow](http://nvie.com/posts/a-successful-git-branching-model), otherwise, use GitHub flow.

## Code Review

Prior to landing a pull request in one of our repositories we require at least one developer to peer review your code.

When you make a PR, assign to another developer to conduct the review. Alternatively, if the code is not ready for review yet, prefix the title with "WIP" (Work in Progress).

Once ready for review, the reviewer will then use Github's built in review process to comment and approve/deny the request. They should then unassign themself from the issue and assign the submitter.

## Designer Review

If there are visual changes in your commit, a designer should review it as well.
On GitHub our repos should have the following labels (click [here](https://github.com/MozillaFoundation/mofo-standards/labels) for the canonical list of labels with their coloring):

- `PR - Designer Review Requested`
- `PR - Needs Design Changes`
- `PR - Designer Approved`

If design changes are required, attach the appropriate label and assign the PR to a designer as well. Since you've opened the PR from the main repo (not a fork), Heroku should auto-deploy a review instance of the app to make this easy. (If you don't have permission to push to the main repo, open the review from a fork and ask for a review instance to be spun up in your PR).

The assigned designer should review the changes and add comments/change the label as appropriate, then unassign themself from the issue.

## Merging Code

If your PR is approved by everyone necessary, then you can go ahead and merge it! If your PR has multiple commits please squash them to a single descriptive commit that explains what your patch does (and *why* if applicable). If your PR is related to a GitHub issue, it's good practice to also include that number in the commit message (eg: `Resolves #342`) so the original issue gets automatically closed.

## Deployment

We use webhooks to trigger automatic deployments to staging environments from the master branch. Production deployments will be performed manually by project members given the right permissions to do so. See the project specific documentation for details on an application's deployment pipeline.

## Internal Libraries

- [Mofo Bootstrap](https://github.com/mozilla/mofo-bootstrap)
- [Mofo UI](https://github.com/mozilla/mofo-ui)

## Add the "uses mofo-standards" badge to projects

In order to show that a codebase or project conforms to the standards talked about in this guide, add the following code to the top of the README.md file:

```
[![Uses Mofo Standards](https://MozillaFoundation.github.io/mofo-standards/badge.svg)](https://github.com/MozillaFoundation/mofo-standards)
```
