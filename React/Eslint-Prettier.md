# Eslint & Prettier

1. Install eslint in project and then initialize eslint

   - `npm i -D eslint `
   - `npx eslint --init`

2. In react verssion > 17.0.0 importing react in file is optional so add this rule in eslintrc file

   ```json
   "rules": {
    "react/react-in-jsx-scope": "off",
    "prettier/prettier": [
      "error",
      {
        "endOfLine": "auto",
        "singleQuote": true,
        "parser": "flow"
      }
    ]
   }
   ```

3. Add eslint plugin for prettier so that both don't collide with each other

   ```js
   npm install eslint-config-prettier eslint-plugin-prettier prettier --save-dev
   ```

4. Now add the code below in extends object in eslintrc file for prettier working.

   ```
   "plugin:prettier/recommended"
   ```

5. Now create .prettierrc file and paste this default code below

    ```json
      // this configuration is preferrable in most cases.   
   {
     "semi": false,
     "tabWidth": 2,
     "printWidth": 100,
     "singleQuote": true,
     "jsxSingleQuote": false,
     "trailingComma": "none",
     "jsxBracketSameLine": true
   }
   ```
> - If you are workign with tailwindCSS and prettier
> - then do this to add tailwind css sorting
> ```npm
> npm install -D prettier-plugin-tailwindcss
> ```
> - And then add this into your prettierrc file
> ```json
>  "plugins": ["prettier-plugin-tailwindcss"]
> ```

---

6. Now add the below code in package.json file for some tweeks

   ```json
   "lint": "eslint .",
   "lint:fix": "eslint --fix",
   "format": "prettier --write './**/*.{js,jsx,ts,tsx,css,md,json}' --config ./.prettierrc"
   ```
