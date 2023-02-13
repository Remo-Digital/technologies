# Project architecture
## Keep it simple.

Components go into the `components` folder, and pages go into the `pages` folder.

If a component is a base component that is commonly used, (like a button with custom styling), please place it in the `component` folder, and prefix it's name with `Base` (Like `BaseButton.tsx`, `BaseInput.tsx`, etc.)

If a component is page specific, please place it in the `component` folder, and prefix it with the name of a page (like `HomeButton.tsx`)

Please do not nest create/nest more folders in the `components` folder.

## Abstraction

**Abstract things reactively, instead of proactively.**

Abstraction adds another layer of complexity with your code, and makes the codebase harder to understand so we should be VERY careful when and how we do it. If you do not have a clear reason to abstract something **DO NOT DO IT**.

As a rule of thumb, do not abstract anything in your initial implementation of a feature. Only afterwards, if it makes sense, and you can justify it.

**Just moving things around in new components, and "it's a code smell" are not valid reasons for abstraction.**

## Comments

Do feel free to add comments to your pages/components, especially if they are larger. Comments are also very usfeul to break up large pieces of JSX code on a page/component.

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

## Form Handling
- [React Hook Form](https://react-hook-form.com/) - makes handling forms, form states and form validations so much easier. 

## Code linters
- [Prettier](https://prettier.io/) - for code linting.
- [Husky](https://www.npmjs.com/package/husky) - Easy-to-use git hooks. So we can execute the linting process when you commit soemthing.
- [Lint Staged](https://www.npmjs.com/package/lint-staged) - so we only lint the files that are staged for commits.

You should have all of these tools (and TypeScript) set up, and running in the project.
[Here's a nicely written guide, detailing how to do so](https://paulintrognon.fr/blog/typescript-prettier-eslint-next-js).

## Data Fetching
- [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) - the native browser implementation is good enough for most of the use cases. It's native to the browser, so there's nothing to install, and it's quite well documented in the provided link.
- ~[SWR](https://swr.vercel.app/) - if you need client side fetching, and use a REST API.~ Please prefer Tanstack Query instead.
- [Tanstack Query (ex React Query)](https://tanstack.com/query/latest/docs/react/overview) - if you need to handle data fetching on the client side. Tanstack Query also comes in with builtin cache handling, and many other goodies which make data fetching on client side way easier.

## GraphQL
- [URQL](https://formidable.com/open-source/urql/) - GraphQL client which is small and easy to use. [Short tutorial video](https://www.youtube.com/watch?v=Miock1yWkCQ) on how to set it up with next.
- [graphql-code-generator](https://www.graphql-code-generator.com/) - So you can generate typescript types from your graphql endpoint. Don't forget to set the `maybeValue: T` in your `codegen.yml`, [like here](https://github.com/dotansimha/graphql-code-generator/issues/3919#issuecomment-618595537). Otherwise you'll rip your hair out with the typing.
- ~Apollo Client~ - **Just use URQL instead.** It has all the featres, and more, and is smaller in size.

## Carousel/Slider

### Please try to avoid them.

Or at least, before implementing one, please take a look at the following presentation: [Should I Use A Carousel?](https://shouldiuseacarousel.com/)

If you the client is really really insistant on having a carousel, and must have it:
- [react-multi-carousel](https://react-multi-carousel.vercel.app/)
  
  **Possible bugs:**
  - If the carousel doesn't render for some reason, try wrapping it in a `div` and giving it a height and width of a 100%.

