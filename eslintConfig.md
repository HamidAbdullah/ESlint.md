#  ESlint:
ESlint is tool that help **develpors** identify and fix common errors in their **javaScript** code.it checks the code for common mistake such as errors , spelling mistake and **formatting issues**.then it give suggestion how to fix those mistake to make the code word better. ESLint is used to improve the **quality and reliability** of JavaScript code.

## [Installation and setup of ESLint](https://github.com/vasilestefirta/react-native-eslint-prettier-example):
1. React Native (0.63.4) version include an ESlint configuration by default. However, we will **remove that configuration** becuase we plan to **create our own configurations**. 

        `npm uninstall @react-native-community/eslint-config`

2. React Native 0.63.4 (latest version) doesn't have the most up-to-date version of eslint. To get the latest version, we'll uninstall it and then reinstall it.
         
          `npm uninstall eslint`

3. now install the latest eslint package version.
        
            `npm install eslint --save-dev`

4.  To set **up a configuration** file for eslint, we'll run a command in cli
      
         `npx eslint --init`
     that asks us some questions through the command line interface. We'll need to select the appropriate answers for each question, indicated by checkmarks (✔) and arrow symbols (❯).

# question 1:

    ? How would you like to use ESLint? …
        To check syntax only
        To check syntax and find problems
        ❯ To check syntax, find problems, and enforce code style

# question 2:

    ? What type of modules does your project use? …
        ❯ JavaScript modules (import/export)
        CommonJS (require/exports)
        None of these

# question 3:
? Which framework does your project use? …
❯ React
  Vue.js
  None of these

# question 4

    // (select "No", because we won't add TypeScript support for this project):
    ? Does your project use TypeScript? › No / Yes

# question 5:

        ? Where does your code run? …
        Browser
        ✔ Node

# question 6:
        ? How would you like to define a style for your project? …
        ❯ Use a popular style guide
        Answer questions about your style
        Inspect your JavaScript file(s)

# question 7 (we'll rely on Airbnb's JavaScript style guide here):
        ? Which style guide do you want to follow? …
        ❯ Airbnb: https://github.com/airbnb/javascript
        Standard: https://github.com/standard/standard
        Google: https://github.com/google/eslint-config-google

# question 8:
        ? What format do you want your config file to be in? …
        JavaScript
        YAML
        ❯ JSON

****

    the final prompt here is where eslint will ask you if you want to install all the necessary dependencies. Select "Yes" and hit enter: Yes
Checking peerDependencies of eslint-config-airbnb@latest
The config that you have selected requires the following dependencies:

    eslint-plugin-react@^7.21.5 eslint-config-airbnb@latest eslint@^5.16.0 || ^6.8.0 || ^7.2.0 eslint-plugin-import@^2.22.1 eslint-plugin-jsx-a11y@^6.4.1 eslint-plugin-react-hooks@^4 || ^3 || ^2.3.0 || ^1.7.0

    ? Would you like to install them now with npm? › No / Yes

**After completing the setup process for eslint, a file called ".eslintrc.json" will be created in the root directory of the project. This file will contain the initial configuration for eslint, which we can modify later as needed.**
                   
        eslintrc.json
    _________________________________________
       {
    "env": {
        "es2021": true,
        "node": true,
    },
    "extends": [
        "plugin:react/recommended",
        "airbnb"
    ],
    "parserOptions": {
        "ecmaFeatures": {
            "jsx": true
        },
        "ecmaVersion": 12,
        "sourceType": "module"
    },
    "plugins": [
        "react"
    ],
    "rules": {
    }
}


This is a **configuration file for ESLint** that specifies the linting rules for a project that uses React Native and TypeScript.Here's what each part does:

**`env`:**
               
        Specifies the environments where the code will be running,including ES2021 (the latest version of ECMAScript), Node.js,and React Native.

`extends`
        
        Extends the linting rules from other ESLint configurations. In this case, we are using a combination of recommended rules,rules for React development, rules for TypeScript development,and rules for the Airbnb style guide.

`overrides`
        
        Allows us to specify different configurations for different files in the project


`parser`

          Specifies the parser to use for analyzing the code. Here, we  are using the @typescript-eslint/parser parser.

`parserOptions`

        Specifies the options for the parser, including support for JSX syntax, ECMAScript version 12, and the TypeScript tsconfig.json configuration file.

`plugins`

        Specifies the additional ESLint plugins we are using, including plugins for React, React Native, and TypeScript.

 `settings`

        Specifies additional settings for ESLint, including the version of React to use.

`rules`

         Specifies the specific linting rules to apply to the code. Here, we have specified rules for requiring semicolons, allowing JSX syntax in TypeScript files, and requiring dot notation for accessing object properties

   # 5. React Hooks:

 [React Hooks](https://legacy.reactjs.org/docs/hooks-intro.html) are a popular way to write React Native code, and there are some recommended rules for using them correctly. To use these rules in your project, you need to update your .eslintrc.json file by adding a line to the "extends" section. This will tell ESLint to use the recommended rules for React Hooks.

        {
            //...
            "extends": [
                "plugin:react/recommended",
                "airbnb",
                "airbnb/hooks"
            ],
            //...
        }

 6. npm install --save-dev eslint-plugin-react-native - add support for[ React Native specific ESLint rules](https://www.npmjs.com/package/eslint-plugin-react-native#list-of-supported-rules). After installing this package, update the plugins section of your .eslintrc.json file like so:


            {
                //...
                "plugins": [
                    "react",
                    "react-native"
                ],
                //...
            }

7. Create a **.eslintignore** file in the root on your project to tell ESLint to ignore specific files and directories, and then add the following contents:

        node_modules/
    **In our case, we simply want to ignore the node_modules folder from being linted.**


8. Last step here, is to configure your code editor to lint the code for you.

        To add ESLint in VS Code, follow these steps:
        Open VS Code and navigate to the Extensions tab on the left-hand side.
        Search for "ESLint" in the search bar and install the ESLint extension.
        Navigate to the Settings tab in VS Code by pressing "Ctrl + ," on Windows or "Cmd + ," on Mac.
        In the search bar, type "ESLint" and click "Edit in settings.json".
        Add the following configuration to the settings.json file:

***
            "eslint.enable": true,
            "editor.codeActionsOnSave": {
            "source.fixAll.eslint": true
            },

            6. Save the settings.json file.

******
****
# install and setup Prettier: 

1. To improve the formatting of your code, you can use a tool called Prettier. Prettier is a package that you can install as a dev dependency in your project using npm.

  To install Prettier, open your terminal and navigate to your project directory. Then run the following command:

          npm install --save-dev --save-exact prettier 

2. To make sure our code is high-quality and well-formatted, we can use Prettier and ESLint. Sometimes these tools may conflict, so we need to turn off unnecessary or conflicting ESLint rules. We do this by installing eslint-config-prettier and updating the extends section in our .eslintrc.json file. This allows us to use both tools together in our project without any problems.

           npm install --save-dev eslint-config-prettier

***

                    {
                //...
                "extends": [
                    "plugin:react/recommended",
                    "airbnb",
                    "airbnb/hooks",
                    "prettier",
                    "prettier/react"
                ],
                //...
            }

3. Create a .prettierrc.json configuration file in the root of your project with the following options:

            {
            "arrowParens": "always",
            "bracketSpacing": true,
            "jsxBracketSameLine": false,
            "jsxSingleQuote": false,
            "quoteProps": "as-needed",
            "singleQuote": true,
            "semi": true,
            "printWidth": 100,
            "useTabs": false,
            "tabWidth": 2,
            "trailingComma": "es5"
        }

Prettier is a tool that helps format code. There are many configuration options available, such as specifying the maximum line length or whether to use tabs or spaces for indentation.

To see all of the available options and their explanations, you can refer to the [Prettier documentation.](https://prettier.io/docs/en/options.html)

    If you're working with React Native, it may already come with a .prettierrc configuration file. If this is the case for you, you don't need to create a new .prettierrc.json file. You can simply use the existing configuration file, which is also written in JSON format.


4. Last step here, is to configure your code editor to format your code using Prettier. If you're a VS Code user, simply install the[ Prettier VS Code](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) extension. After the extension has been installed, add the following settings to your VS Code JSON config:

        {
            "editor.defaultFormatter": "esbenp.prettier-vscode",
            "editor.formatOnSave": true
        }

### Final Step: 

    if you're writing React Native components in .js files, you'll need to update the react/jsx-filename-extension ESLint rule to allow JSX in .js files.

**To do this, you can add the following rule to the rules section of your .eslintrc.json file:**

    "rules": {
    "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }]
    }

**his allows JSX to be used in .js files. You can also enable, disable or modify other ESLint rules within the rules section of your .eslintrc.json file.**
