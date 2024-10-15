# Troubleshooting

## Only 1 pak file was created
- Make sure to enable `Use Pak File` and `Generate Chunks`
- Add a Data Asset\Primary Asset Label to your work folder 

## Your pak file is 1kb
- Check the location of your level 
- Confirm if the primary asset label exists on your plugin content

## `Optional` chunk paks are created
- Search for 8k textures and set maximum size to 4096

## Some textures or content is not loaded
- Confirm SM6 is enabled inside Project Settings/Platforms/Windows
- Right-click on your plugin base folder, `Fix Up Redirectors`
- Use `Tools/Audit/Asset Audit` to confirm if your missing content exists within the chunk
