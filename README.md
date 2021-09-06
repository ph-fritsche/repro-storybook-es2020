**Reproduction of storybook defaults being incompatible with ES2020 dependencies**

# What do I see here?

1. A dependency in ES2020 syntax: [*/dependency-foo*](https://github.com/ph-fritsche/repro-storybook-es2020/tree/master/dependency-foo)

2. A component using this dependency: [*/src/App.tsx*](https://github.com/ph-fritsche/repro-storybook-es2020/blob/master/src/App.tsx)

3. A minimal CRA setup

3. The storybook config created per `npx sb init`

# What to do?

1. Open the repro in the [devcontainer](https://github.com/ph-fritsche/repro-storybook-es2020/blob/master/.devcontainer.json) or on your local machine.

2. Install dependencies per `yarn install`.

3.  1. Start the `react-scripts` development server: `yarn start`  
        *=> Works*

    2. Start storybook: `yarn storybook`  
        *=> Fails due to `ModuleParseError: Module parse failed: Unexpected token`.*
    
        ```
        | export default function foo(s) {
        >     return s?.optional ?? 'foo'
        | }
        | 
        ```
