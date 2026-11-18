# Ori DE 简体中文补丁 / Ori DE Simplified Chinese Patch

[中文](#中文) | [English](#english)

## 中文

给《奥日与黑暗森林：终极版》（*Ori and the Blind Forest: Definitive Edition*）用的独立简体中文补丁，是一个很小的 BepInEx 5 插件（`OriZhPatch.dll`）：

- 解锁游戏自带的简体中文：选项 > 语言里出现「简体中文」，并记住你的选择；
- 装入内嵌的霞鹜文楷字形图集，补齐游戏字体里缺的字；
- 给游戏中文里空着的条目补上翻译，修正部分术语；角色名字保留英文（Ori、Sein、Naru……）。

没有联机或合作代码，没有额外菜单，也不改任何玩法。

### 安装

1. 到 [Releases](../../releases) 下载 `OriZhPatch-v….zip`。
2. 退出游戏，把压缩包里的东西**全部**解压到游戏目录，和 `oriDE.exe` 放在一起。
3. 启动游戏，选项 > 语言 > **简体中文**。

卸载：删除 `BepInEx\plugins\OriZhPatch.dll` 和 `BepInEx\config\oricoop.zhpatch.cfg`。如果 BepInEx 只是为这个补丁装的，还可以删掉 `BepInEx\`、`winhttp.dll`、`doorstop_config.ini`、`.doorstop_version`。

### 兼容性

- 只适用于 **Definitive Edition**（`oriDE.exe`），针对正版、没装其他模组的游戏。
- **普通版（非终极版）没有测试过**，不保证能用。
- **不要和 OriCoop 合作模组一起装**：OriCoop 已经包含了这个补丁。两者同时存在时，BepInEx 会停用这个独立补丁，并在日志里说明。
- 压缩包里没有任何游戏文件或存档，你需要自己有一份正版游戏。

### 自己编译

需要：Windows，.NET Framework 4 自带的 `csc.exe`，一份装好 BepInEx 5 的 Definitive Edition（编译时引用游戏和 BepInEx 的 DLL，这些 DLL 不在仓库里）。

```powershell
# 只编译 OriZhPatch.dll（输出到 src\bin）
powershell -File src\build-zhpatch.ps1 -NoInstall -Game "<游戏目录>"
# 编译并打包 zip（输出到 dist\）
powershell -File src\make-zhpatch-kit.ps1 -Game "<游戏目录>"
```

`src/assets/zh-text/` 下的 `zh_extra.txt`、`zh_terms.txt` 含有游戏原文，所以**不在仓库里**（见 [GAME-ASSETS-NOTICE.md](public/GAME-ASSETS-NOTICE.md)）。没有它们也能编译和运行，只是少了补译和术语修正；Releases 里的 zip 是完整版。

### 来源和许可

- 代码来自 [OriCoop](https://github.com/Venompool888/oricoop) 的中文支持部分（用 `ZHPATCH` 编译开关去掉联机相关代码），使用 [MIT 许可证](LICENSE)。
- 字体：霞鹜文楷（LXGW WenKai Light），作者 LXGW 和 Klee Project Authors，SIL Open Font License 1.1，见 [LXGW-WenKai-OFL.txt](src/assets/zhpatch-kit/LXGW-WenKai-OFL.txt)。
- 打包进 zip 的 BepInEx、HarmonyX 等第三方组件的许可见 [THIRD-PARTY-LICENSES.txt](src/assets/kit/THIRD-PARTY-LICENSES.txt)。
- 游戏内容的权利归 Moon Studios、Microsoft / Xbox Game Studios 等权利人所有。这是非官方、非商业的玩家补丁，与他们没有关联，也没有得到他们的认可。

## English

A standalone Simplified Chinese patch for *Ori and the Blind Forest: Definitive Edition*: one small BepInEx 5 plugin (`OriZhPatch.dll`) that

- unlocks the game's built-in Simplified Chinese, adds 简体中文 to Options > Language and remembers your choice;
- installs an embedded LXGW WenKai glyph atlas with the characters the game's font lacks;
- fills in Chinese text the game leaves blank and corrects some terms, keeping character names in English (Ori, Sein, Naru, ...).

No co-op code, no extra menus, no gameplay changes.

### Install

1. Download `OriZhPatch-v….zip` from [Releases](../../releases).
2. Close the game and unzip **everything** into the game folder, next to `oriDE.exe`.
3. Start the game and choose Options > Language > **简体中文**.

Uninstall: delete `BepInEx\plugins\OriZhPatch.dll` and `BepInEx\config\oricoop.zhpatch.cfg`. If BepInEx was installed only for this patch, you can also delete `BepInEx\`, `winhttp.dll`, `doorstop_config.ini` and `.doorstop_version`.

### Compatibility

- **Definitive Edition only** (`oriDE.exe`), for an unmodded retail copy of the game.
- **The standard (non-Definitive) edition is untested**; compatibility is not guaranteed.
- **Do not install it alongside the OriCoop co-op mod**, which already contains this patch. If both are present, BepInEx disables this standalone patch and logs why.
- The zip contains no game files or saves. You need your own legitimate copy of the game.

### Build

You need Windows, the `csc.exe` that ships with .NET Framework 4, and a Definitive Edition install with BepInEx 5. The build references the game's and BepInEx's DLLs, which are not in this repository.

```powershell
# OriZhPatch.dll only (to src\bin)
powershell -File src\build-zhpatch.ps1 -NoInstall -Game "<game folder>"
# build and package the zip (to dist\)
powershell -File src\make-zhpatch-kit.ps1 -Game "<game folder>"
```

`zh_extra.txt` and `zh_terms.txt` under `src/assets/zh-text/` contain game text, so they are **not in this repository** (see [GAME-ASSETS-NOTICE.md](public/GAME-ASSETS-NOTICE.md)). The patch builds and runs without them, minus those fallback translations and term fixes. The zip in Releases is the full build.

### Origin and licences

- The code is the Chinese-language part of [OriCoop](https://github.com/Venompool888/oricoop), compiled with the `ZHPATCH` define to leave out everything co-op. It is under the [MIT licence](LICENSE).
- Font: LXGW WenKai Light by LXGW and the Klee Project Authors, SIL Open Font License 1.1; see [LXGW-WenKai-OFL.txt](src/assets/zhpatch-kit/LXGW-WenKai-OFL.txt).
- Licences for BepInEx, HarmonyX and the other components bundled in the zip: [THIRD-PARTY-LICENSES.txt](src/assets/kit/THIRD-PARTY-LICENSES.txt).
- Rights in the game content belong to their owners, including Moon Studios and Microsoft / Xbox Game Studios. This is an unofficial, non-commercial fan patch, not affiliated with or endorsed by them.
