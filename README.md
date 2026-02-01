# Hytale SkinLoader by [FunkyoEnma](https://funkyo.carrd.co/)
*(This is a functional alpha version, if you find any bug please report it here*

This is a mod that allows you to:

- Export to a .zip your custom character from the asset editor including
the main file and all the assets related to it with a simple command.
- Import a custom character from a url, downloading and setting it
- Set a model with a command and a specific permission

# Set a custom skin
The main command to set a custom skin (character model) is

    /skinloader set custom [modelname | url] <player> <modelname>

The arguments in [] are mandatory and the arguments in <> are optionals, where:

- **--player**: Is the player to put the skin, if not provided it puts to the command server
  (This argument is mandatory via console)
- **--modelname**: By default the models are saved to a formatted name with the user uuid, you can
change that with this parameter to save it with a custom name

### Required permissions
- `skinloader.set`
- `skinloader.set.custom`
- `skinloader.set.custom.toself` (To put the skin to self)
- `skinloader.set.custom.toplayer` (To use the --player argument)

## Set a skin from server
To set a skin that already is in server you must use the command: 

    `/skinloader set custom [modelname] <player>

### Required permissions
- `skinloader.set`
- `skinloader.set.custom`
- `skinloader.set.custom.toself` (To put the skin to self)
- `skinloader.set.custom.toplayer` (To use the --player argument)
- `skinloader.set.custom.model` (Specific permission to use modelname type)

## Download and Set a skin from url
To download the skin from url and set it you must use this command

    `/skinloader set custom [url] <player> <modelname>

If the parameter model name is not given, the model is going to be saved under the
formatted name with the destination player uuid (the uuid of --player or self if parameter --player not given)

### Required permissions
- `skinloader.set`
- `skinloader.set.custom`
- `skinloader.set.custom.toself` (To put the skin to self)
- `skinloader.set.custom.toplayer` (To use the --player argument)
- `skinloader.set.custom.url` (Specific permission to use url type)

This command will generate temporal files at `/tmp/SkinLoader/`.

**Advice:** for security reasons at this moment the skin import is only abaible for skins (character models) exported
with this mod.

*This function has been tested only with discord url, if some url wit .zip file don't work please tell me to check it*

# Export a skin

    /SkinLoader export custom <AssetPack> <path> <ModelName> --hasCharacterDirectory

- **AssetPack**: The name of the AssetPack (Could be the name in asset editor with ":" or the name in fileSystem with ".")
- **path**: Path to the main file (Default usually is `Models/Human` ***In asset editor showed as ModelAsset/Human***)
- **ModelName**: This is the name of the asset in asset editor or filename in the filesystem (without the .json)
- **Optional flag hasCharacterDirectory**: **This is only if the model have its own subfolder inside `Common/Characters`, for example in `Commion/Characters/Lumi/lumi.bbmodel`**

### Required permissions
- `skinloader.export`
- `skinloader.export.custom`

To export a skin please have this thinks in mind:

The common files must be inside the `Common/Characters` folder, and them can be in a subfolder, ie: 
`Common/Characters/lumi.bbmodel`, `Commion/Characters/Lumi/lumi.bbmodel` even with a subdirectory organization, ie:
`Common/Characters/Lumi/Atacchments/hat.bbmodel`, `Common/Characters/Lumi/Textures/hat.png`, `Common/Characters/hat.png`, etc.
 
The skin (Character model) will be exported to `/export/FunkyDev.SkinLoader/modelname.zip`

### Known bugs
- In Local world (Without dedicated server) the AssetPack must be on `Roaming\Hytale\UserData\Saves\<wold>\mods\`, this will be solved in the 0.0.2 version

## Important advisement
This mod is already in testings, and it can have bugs, if you found one please report it in the
[official github repository](https://github.com/FunkyoEnma/SkinLoader) to solve it.

## License
Any modification of the code is forbidden without authorization, if you want to contribute, please contact me.

This mod can be used in commercial use, distributed with modpacks and private use whitout Attribution needed.
