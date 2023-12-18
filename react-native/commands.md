```shell
# create a new project
npx react-native@latest init <project>

# create a new project (only for Android)
npx react-native@latest init <project> --skip-install
npm install
npx react-native run-android

# install library that runs native code (--save/--save-dev flag is important)
npm install <library> --save

# run project in android
npm start # run metro server
npm run android # run emulator/phone (at another terminal)
```
