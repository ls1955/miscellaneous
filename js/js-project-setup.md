# Scenario:

Setup a new JS project with npm, also wanna install Jest.

```bash
npm init
npm install --save-dev jest
touch .gitignore && echo "node_modules/*" >> .gitignore # Assume working with git

# if using import statements
  npm install --save-dev babel-jest @babel/core @babel/preset-env
  touch babel.config.js && printf "module.exports = {\n  presets: [['@babel/preset-env', {targets: {node: 'current'}}]],\n};" >> babel.config.js

git add .
git commit -m "Initial commit"
```
