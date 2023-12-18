This fix is for Android 10. Try it if all else failed.

In AndroidManifest.xml, add:

```xml
<manifest xmlns:android="...">
    <application
        android:requestLegacyExternalStorage="true"
        ...
    >
    ...
    </application>
    ...
</manifest>
```
