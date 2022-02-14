# ComposeImagePicker
> a composable function which provides user selection image Uri.
you can use this function to easily retrieve user's gallery images and get the selected Uri as call back.



## Getting start
to use this function you need to take some steps:

1) First of all, you shoud add following line in you *AndroidManifests.xml*:
    ```
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    ```
2) Then, you need to add the following dependencies in you *build.gradle (Module)*
    ``` 
    implementation "com.google.accompanist:accompanist-permissions:Latest_version"
    implementation "io.coil-kt:coil-compose:Latest_version"
    ```
now you are ready to use *ImagePicker* in you composable function just like this:
```
ImagePicker(
    modifier = Modifier
        .background(
            MaterialTheme.colors.background,
            shape = RoundedCornerShape(topEnd = 20.dp, topStart = 20.dp)
        )
        .clip(RoundedCornerShape(topStart = 20.dp, topEnd = 20.dp))
        .shadow(5.dp, RoundedCornerShape(topEnd = 20.dp, topStart = 20.dp)),
    height = 550.dp,
    openSelection = openSelection,
    context = applicationContext,
    onCloseListener = {openSelection = false}
) { selectedImageUri ->
    openSelection = false
    Log.i("Log", "selected image uri is: $selectedImageUri")
}
```
    

## Just a Points
It is better to provide the list of image Uris as a parameter for the function. so you can move the logic of finding Uris in you *view model* and pass it as a parameter to the *ImagePicker* composable.

## here you can see some screenshot of the result:

