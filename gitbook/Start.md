# 开始

## 进入游戏

请创建一个世界，在教程作者的环境下，ProbeJS应当会在 `.minecraft/kubejs/probe` 和 `.minecraft/.vscode` 文件夹下生成一些文件以供VS Code进行自动补全并且控制台会输出以下内容：![](https://s2.loli.net/2024/03/21/6jgMTxInfo3kpPK.png)

当你看到 `ProbeJS typing generation finished. [time]` 时，代表ProbeJS已经生成完毕。

如果你没有看见以上内容，请在聊天框输入 `/probejs test_availability` 来验证是否可以进行生成，若输出以下内容：![](https://s2.loli.net/2024/03/21/Gei4TMHpqavULoX.png) 那么你就可以运行 `/probejs dump` 来生成文件。

## 常用指令

### 注意：以下所有 `/kubejs` 均可简写成 `/kjs` 。

| 命令                                | 注释                                                         |
| :---------------------------------- | ------------------------------------------------------------ |
| `/kubejs errors <脚本类型>`         | 脚本类型可以传入 `client` `server` `startup` ，来查看对应脚本类型的错误。 |
| `/kubejs hand`                      | 查看当前主手物品的信息，点按彩色字体可复制内容。             |
| `/kubejs dump_registry <注册表>`    | 输出指定注册表下的所有内容。                                 |
| `/kubejs export <输出类型>`         | 输入类型可以传入 `pack_folders` `pack_zips` ，用来将游戏内的配方、tags、所有方块、实体类型、流体类型导出。 |
| `/kubejs hotbar`                    | 查看当前快捷栏的信息。                                       |
| `/kubejs inventory`                 | 查看当前背包的信息。                                         |
| `/kubejs list_tags <注册表> <标签>` | 将指定注册表中指定的标签的内容打印到聊天栏[1]                |
| `/kubejs offhand`                   | 查看当前副手物品的信息                                       |
| `/kubejs packmode <包模式>`         | 设置包模式，不传入 `<包模式>` 将查看当前模式。               |
| `/kubejs reload <类型>`             | `<类型>` 可以为 `config` (重载配置）、 `lang` （语言文件）、 `textures` （纹理）、 `client_scripts` （客户端脚本）、 `server_scripts` （服务端脚本）、 `startup_scripts` （启动阶段脚本）[2] |
|                                     |                                                              |

[1]如在作者当前环境下输入 `/kubejs list_tag minecraft:block forge:chests` ，会输出以下内容：![](https://s2.loli.net/2024/03/21/pC2SBE5OYfDdrum.png)

[2]如果想要重载所有资源，请按下 `F3+T` ；如果想要重载所有脚本、配方、标签和所有数据，请在聊天框输入 `/reload` 并运行； `/kubejs reload startup_scripts` 并不能重载所有启动阶段脚本的事件，有些事情需要您重新启动游戏（例如 `StartupEvents.registry` ）或世界（例如 `WorldgenEvents.add` ）。

## kubejs文件夹结构

接下来列出的的文件夹将位于 `.minecraft/kubejs/` 。

`assets/` ：该文件夹会像正常的资源包一样加载，你可以在这里的对应目录下放自定义的物品、方块、流体等的纹理、模型等，并且也可以通过按下 `F3+T` 来重载，与普通的资源包不同的是，它无法被正常方式禁用。

`client_scripts/` ：该文件夹应保存着每次客户端资源重新加载时加载的脚本。

`config/` ：该文件夹储存着 KubeJS 与其部分附属的配置。

`data/` ：该文件夹会像正常的数据包一样加载，并且也可以通过输入 `/reload` 来重载，与普通的数据包不同的是，它无法被正常方式禁用。

`exported/` ：该文件夹储存着游戏内通过指令导出的部分数据。

`probe/` ：该文件夹储存着 ProbeJS 导出的部分数据。

`server_scripts` ：该文件夹应保存着每次服务端数据重新加载时加载的脚本。

`startup_scripts` ：该文件夹应保存着每次启动时加载的脚本。
