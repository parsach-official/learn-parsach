# Publish your content
If you follow the previous instructions or have our template, you can package your content into a single `.pak file`.

## Package
Package game and check your chunk pak file, use this file to publish your content.

Go into the Platforms menu, select Windows, and a folder:

![Package](https://learn.parsach.com/assets/images/UE5.4/package.png)

After the package is done, go into the `<output_folder>\Windows\<your_project>\Content\Paks`
You should have 2 files, for example with chunk id being 10 on the primary asset label: 
- pakchunk0 -> main game pak
- pakchunk10 -> your pak to publish

![Pak file](https://learn.parsach.com/assets/images/UE5.4/pak_output.png)

## Test your paks

You can download our test application from [here](https://blobs.learn.parsach.com/ue53/Parsach_PlayTester.zip) and copy your pak into the folder `UserContent`
It should open the first pak found, the first map found on this folder, in VR mode.

![Play Tester](https://learn.parsach.com/assets/images/UE5.4/playtester_user_content.png)

## Publish

Publish your content in:
https://studio.parsach.com/create/upload

