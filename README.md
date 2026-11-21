# Minecraft-PVP-AI-bot----WaveDog
我的世界高版本pvp的AI机器人
将机器人装到服务器
1. 准备服务器环境：Windows x64、Paper 1.21.11、Java 21 和 Node.js。
2. 例如解压到 E:\WaveDog，在PowerShell中运行：
   Set-Location -LiteralPath 'E:\WaveDog\work\pvp-dual-brain'
   npm.cmd ci --omit=dev
3. 复制插件。 关闭目标服，把解压后 plugins 里的 JAR 和配置目录一起复制到目标服的 plugins。解压出来的 work 留在 E:\WaveDog。
4. 修改启动命令。 在原来的-jar 前加上这两个参数，路径换成目标机上的实际路径：
   "-Dwavedog.workspace=E:\WaveDog" "-Dwavedog.node=E:\node\node.exe"
5. 自己准备竞技场。启动后，在服务端控制台运行 wdnative status 和 wdneural，确认两只机器人在线、模型显示 ready: true。然后在游戏里用 /<输入机器人的名字> duel <输入你的游戏名> 开局。
