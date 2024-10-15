# Content

## Add your content to ParsachExp Plugin
All your content should be contained inside this plugin, it should not reference assets outside of the plugin. 

The exception to this is any **untouched** asset from Starter Content and VR Template, these can be referenced inside the plugin.

You can start by adding a VR level to your `ParsachExp` plugin, one possibility is to copy the `VRTemplate/Maps/VRTemplateMap` into `/ParsachExp/Maps`.
Just remember to rebuild lighting, since it has several static lights.

You can rename the level, so you don't mistake it with the base VRTemplate map.

![Default Map](https://learn.parsach.com/assets/images/UE5.4/add_content/add_level.png)

This will serve as the main level for your experience when it runs inside Parsach.


## Videos
To package video files and include them on chunk files you need to do several steps as described on Prepare VR Project.

Additionally, after any movie is added to the Plugin Movies folder (`YourProjectName/Plugins/ParsachEXP/Content/Videos`), drag and drop them into Editor, and it will create a `File Media Source` with full path.

You **must convert it** to a **relative path** such as `./../../YourProjectName/Plugins/ParsachExp/Content/Movies/samplevideo.mp4`

Make sure the initial part is `./../../` and append your `.uproject` name, for our samples it is `Parsach_Template` resulting in `./../../YourProjectName/Plugins/ParsachExp/Content/Movies/samplevideo.mp4`

![File Media Source](https://learn.parsach.com/assets/images/UE5.4/add_content/movie_file_media_source.png)

!!! tip

    There is a caveat, for it to work both as a pak video and inside unreal editor, make sure your project folder and name fully match, example:


    - project name is `abc`
    - located at C:\aaa\bbb\ccc\abc\abc.uproject
    - last folder and project name match
    - relative path should be `./../../abc/Plugins/ParsachExp/Content/Movies/samplevideo.mp4`
