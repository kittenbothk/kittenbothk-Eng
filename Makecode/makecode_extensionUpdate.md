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

你可能正在使用舊版本的插件而需要更新，更新插件的方法如下：
1. 切換至JavaScript模式
2. 打開資源管理器
3. 點擊插件版本
4. 插件就會自動更新到最新版本

![](./images/update.gif)

## 修改插件版本

你有時候可能會需要切換至之前版本的插件，更改插件版本的方法如下：

1. 打開專案設定
2. 點擊「以純文字模式編輯設定」
3. 在KOI的插件中，更改版本

        ( "koi" : "github:kittenbot/pxt-koi#v0.5.4" )->( "koi" : "github:kittenbot/pxt-koi#v0.2.4" )
    
4. 右擊然後儲存
5. 切換至Javascript模式
6. 檢查插件版本

![](./images/modify.gif)
