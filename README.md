# Technologies we use:

## CMS systems
- [Storyblok](https://www.storyblok.com/)
- Also considering [Prismic](https://prismic.io/) and [NetlifyCMS](https://www.netlifycms.org/), as alternatives.

## Frameworks

- [NextJS (React)](https://nextjs.org/) + [TypeScript](https://www.typescriptlang.org/)

We use NextJS in combination with Vercel for easy github integration and deployments.
NextJS has too many benefits to count, but the key selling point is that it makes deploying and optimizing your website/app very easy. So we spend less time configuring things, and more time actually coding them.

## Styling
- [TailwindCSS](https://tailwindcss.com/)

### Styling component libraries
- [HeadlessUI](https://headlessui.dev/)
- [TailwindUI](https://tailwindui.com/)

We heavily rely and recommend these libraries. They are simple to use, look very good out-of-the-box, and are very customizable, if needed.

## Code linters
- [Prettier](https://prettier.io/) - for code linting.
- [Husky](https://www.npmjs.com/package/husky) - Easy-to-use git hooks. So we can execute the linting process when you commit soemthing.
- [Lint Staged](https://www.npmjs.com/package/lint-staged) - so we only lint the files that are staged for commits.

You should have all of these tools (and TypeScript) set up, and running in the project.
[Here's a nicely written guide, detailing how to do so](https://paulintrognon.fr/blog/typescript-prettier-eslint-next-js).

## Data Fetching
- [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) - the native browser implementation is good enough for most of the use cases. It's native to the browser, so there's nothing to install, and it's quite well documented in the provided link.

## GraphQL
- [URQL](https://formidable.com/open-source/urql/) - GraphQL client which is small and easy to use. [Short tutorial video](https://www.youtube.com/watch?v=Miock1yWkCQ) on how to set it up with next.
- [graphql-code-generator](https://www.graphql-code-generator.com/) - So you can generate typescript types from your graphql endpoint. Don't forget to set the `maybeValue: T` in your `codegen.yml`, [like here](https://github.com/dotansimha/graphql-code-generator/issues/3919#issuecomment-618595537). Otherwise you'll rip your hair out with the typing.
