# commands
```shell
# create a new project
npx react-native@latest init <project>

# install library that runs native code (--save/--save-dev flag is important to link them automatically)
npm install <library> --save

# run project in android
npm start # run metro server
npm run android # run emulator/phone (at another terminal)

# connect physical device
# adb (android debug bridge)
# list connected devices
adb devices

# production build
npx react-native build-android --mode=release
npm run android -- --mode="release"
```

# references
* [Running on device doc](https://reactnative.dev/docs/running-on-device)
* [Debugging basics doc](https://reactnative.dev/docs/debugging#accessing-the-dev-menu)
* [Production build doc](https://reactnative.dev/docs/signed-apk-android)
