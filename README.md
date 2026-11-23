# Minecraft-PVP-AI-bot----WaveDog
我的世界高版本pvp的AI机器人 Minecraft pvp AI bot robot Wavedog
将机器人装到服务器
1. 准备服务器环境：Windows x64、Paper 1.21.11、Java 21 和 Node.js。
2. 例如解压到 E:\WaveDog，在PowerShell中运行：
   Set-Location -LiteralPath 'E:\WaveDog\work\pvp-dual-brain'
   npm.cmd ci --omit=dev
3. 复制插件。 关闭目标服，把解压后 plugins 里的 JAR 和配置目录一起复制到目标服的 plugins。解压出来的 work 留在 E:\WaveDog。
4. 修改启动命令。 在原来的-jar 前加上这两个参数，路径换成目标机上的实际路径：
   "-Dwavedog.workspace=E:\WaveDog" "-Dwavedog.node=E:\node\node.exe"
5. 自己准备竞技场。启动后，在服务端控制台运行 wdnative status 和 wdneural，确认四只机器人在线、模型显示 ready: true。然后在游戏里用 /<输入机器人的名字> duel <输入你的游戏名> 开局。


附带小体积AI机器人玩家对话：我的世界游戏内基于pvp机器人内置transformer系统的小语言transformer。
感受transformer,我设想应该这样，
向量对应动作战斗状态环境等各种之前近身剑斗transformer以及感受trans（二者感受的东西相同甚至感受trans更多）乃至玩家发的消息等各种游戏中需要感受的东西，
同时向量对应自己要输出的字或单词短语（语素），那样可以说出更多样化的语言。
const ids = tf.tensor2d(messages.map((message, i) => [...message, ...reply[i]]), undefined, 'int32')
const inputs = tf.concat([game, tf.gather(this.embedding, ids)], 1)
const state = this.block.apply(tf.add(inputs, this.position.slice([0, 0], [length, width])),
  this.mask.slice([0, 0], [length, length]))
return this.head.apply(state.slice([0, prefixLength, 0], [batch, reply[0].length, width]))
