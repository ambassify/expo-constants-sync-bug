# expo-constants-sync-bug

Reproduce:

1. I created a new expo app using npx create-expo-app
2. Made some small changes to use custom native builds (https://docs.expo.dev/guides/adopting-prebuild/)
3. Added `expo.extra.foo = 'bar'` in my `app.json` file
4. In the example app, displayed that value by referencing `Constants.expoConfig.extra.foo`
7. Run `npx expo run:android`
5. It works, "bar" is deplayed.
6. Change `expo.extra.foo` to `'baz'`
7. Run `npx expo run:android`
8. It doesn't work, "bar" is still displayed
9. Run `npx expo prebuild`
10. Run `npx expo run:android`
11. It still doesn't work, "bar" is still displayed
12. Run `npx expo prebuild --clean`
13. Run `npx expo run:android`
11. The value has been update to "baz"
