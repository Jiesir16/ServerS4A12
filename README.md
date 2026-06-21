# 86JP Server Emulator

DNF 86JP 服务端模拟器。配合 `86JP` 客户端使用,客户端在dc群。

## 作者与协作

署名: 风骑士

目前项目仍处于研究和开源完善阶段，还存在非常多 BUG。欢迎有能力的朋友一起提交 Issue、PR，或加入 Discord 共同完善服务端、客户端适配、封包、数据库和 PVF 相关内容。

## 社区交流

Discord 社区: https://discord.gg/3wct6SZp

## 补丁源码

补丁源码位于 `Patch/` 目录。补丁成品已经生成好，并且已经放在客户端中；普通用户直接使用客户端即可，不需要重新编译补丁。

## 快速启动

普通用户下载仓库后，直接双击根目录的 `StartServer.exe`。它会启动 `Server/DfoServer/bin/Debug/DfoServer.exe`。

如果你改了源码，需要重新编译，再运行 `StartServer.exe`。

## 构建

需要 .NET SDK（提供 `dotnet` CLI）。NuGet 依赖自动下载，无需额外配置。

```bash
dotnet build Server/DfoServer.sln -c Debug
```

或双击 `build.bat`。

## 运行

1. 将客户端的 `Script.pvf` 放到 `Server/DfoServer/bin/Debug/Data/Pvf/` 目录
2. 运行 `Server/DfoServer/bin/Debug/DfoServer.exe`
3. 服务端监听 7001 (Channel) + 10011 (Game) 端口

## 数据库

SQLite 数据库 `inventory.db` 位于 `Server/DfoServer/bin/Debug/Data/`。
首次运行时自动创建表结构。附带的 DB 包含一个种子角色。

## 项目结构

```
Server/DfoServer/    服务端主程序 (.NET Framework 4.7.2)
Tool/PvfLib/         PVF 档案解析库
build.bat            一键构建脚本
```
