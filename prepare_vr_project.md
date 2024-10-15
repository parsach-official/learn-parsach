# Prepare your VR Project

You can download our template project from [here](https://blobs.learn.parsach.com/ue54/Parsach_Template.zip).

If you want to use an existing project instead of using the template, follow the instructions below.

# Creating a project without using the template

## Add a Content Plugin

Inside your UE Project, go into the Plugins tab from `Edit -> Plugins`, click on Add and select `Content Only`; the plugin name should be `ParsachExp` 

![Open Plugins](https://learn.parsach.com/assets/images/UE5.4/prepare_vr_project/open_plugin.png)
![ParsachExp Plugin](https://learn.parsach.com/assets/images/UE5.4/prepare_vr_project/create_plugin.png)

## Add a Primary Asset Label to the plugin
Create a `Data Asset`-> `Primary Asset Label` on your plugin content folder by right-clicking on your asset list, Miscellaneous -> Data Asset -> Primary Asset Label

![Add data asset](https://learn.parsach.com/assets/images/UE5.4/add_data_asset.png)
![Add primary asset label](https://learn.parsach.com/assets/images/UE5.4/add_primary_asset_label.png)

Prefix the file with `DA_` such as `DA_PluginPak`, then open the file and update the settings to:

- have a chunk ID between 10 and 1000
- Disable `Apply Recursively`
- Cook rule - Always Cook
- Enable `Label Assets in My Directory`
- Enable `Is Runtime Label`
- Enable `Include Redirectors`

![DA_PluginPak](https://learn.parsach.com/assets/images/UE5.4/plugin_data_asset.png)

This will ensure your content is packaged into a pak file, separate from the main game pak.
You only need one `Primary Asset Label` in your base plugin content folder. 

## Update your Project Settings

Update packaging settings:

- Enable
    - Use Pak File
    - Generate Chunks
- Disable
    - IoStore
    - Zen Store
    - Share Material Shader Code

![Package settings](https://learn.parsach.com/assets/images/UE5.4/engine_project_settings.png)

### Update Game - Asset Manager settings
Go into Project Settings -> Game -> Asset Manager
Add the directory `/ParsachExp` inside Primary Asset Types to Scan -> Index[1] PrimaryAssetLabel -> Directories -> Add `/ParsachExp`

![Asset Manager](https://learn.parsach.com/assets/images/UE5.4/primary_asset_to_scan.png)

## Include Videos on your pak

To add movies to your content, first, you must create a folder, `Movies,` inside the plugin content.

Then go into project settings -> Packaging, search for `Additional Non-Asset Directories to Package` add `./../Plugins/ParsachExp/Content/Movies`

![Asset Manager](https://learn.parsach.com/assets/images/UE5.4/additional_non-asset.png)

Finally, add the file `DefaultPakFileRules.ini` into your Config folder (`/YourProjectName/Config`).
The value for OverridePaks must include `pakchunk` + chunk id from the data asset previously created. In our example id 10, therefore `pakchunk10`.

![DefaultPakFileRules.ini](https://learn.parsach.com/assets/images/UE5.4/defaultpakfilerules.png)

**Restart the editor** so this file is considered.

=== Content for the file DefaultPakFileRules.ini

    [MoviesToPak]
    OverridePaks="pakchunk10"
    bOnlyChunkedBuilds=true
    ; List of file masks to apply to
    +Files=".../*.mp4"
    +Files=".../*.avi"
    +Files=".../*.mov"
    
