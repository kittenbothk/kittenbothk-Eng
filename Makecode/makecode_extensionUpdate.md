# Makecode Extension Updates

Kittenbot may release updates for MakeCode extensions periodically to improve functionality and remove bugs. This page will show you how to update or rollback your MakeCode extension versions.

![](../functional_module/PWmodules/images/mcbanner.png)

#### KOI extension is used for demonstration

#### Import the KOI extension.

#### https://github.com/KittenBot/pxt-koi

[Loading Extensions](./powerBrickMC)

## Checking Extension Version

The steps to check the version of the extension:

1. Switch to text code mode
2. Open Explorer
3. The version is shown

![](./images/check.gif)

## Updating the Extension

If the extension version is outdated, it can be updated using the following method:

1. Switch to text code mode.
2. Open Explorer.
3. Click the version number.
4. The extension will be updated automatically.

![](./images/update.gif)

## Specifying an Extension Version:

You may need to specify an older version of an extension, this is done with the following method.

1. Open Project Settings.
2. Select "Edit Setting as Text".
3. Change the version number to the one desired.

        ( "koi" : "github:kittenbot/pxt-koi#v0.5.4" )->( "koi" : "github:kittenbot/pxt-koi#v0.2.4" )
    
4. Right click and save.
5. Switch to text code mode.
6. The extension version should now be changed.

![](./images/modify.gif)
