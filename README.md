# hargow-courses

Versioned Cantonese curriculum for Hargow

粤语情境课程真源，正文、粤拼、解释、词汇语法、角色和来源授权分开记录。

首个原创试点是「走进茶楼，先打个招呼」：六轮粤语对话、作者标注词段与粤拼、词汇/语法、三种练习和日常应用。课源使用 Chef 2.0 契约，结构与课包检查通过；revision 3 已包含原创角色头像、Qwen Flash 3.1 实际粤语语音和固定强制对齐模型测得的时间轴。录音与素材离线检查通过；尚未登记生产或激活发布，没有声明人工试听。

字音参考 [香港语言学学会粤拼字表](https://github.com/lshk-org/jyutping-table)，情境文字与解释为原创。字表核对不等同于整段口语与实际配音质量验收。录音使用实际粤语，不使用法语或普通话配音冒充。

离线检查（在 Chef 的固定版本目录执行）：

```powershell
$env:CHEF_PRODUCT = 'hargow'
cargo run --locked -p chef-engine --bin chef-server -- check ../hargow-courses/lessons/starter-teahouse-arrive.lesson.json
cargo run --locked -p chef-engine --bin chef-server -- check-release ../hargow-courses/releases/hargow-teahouse-pilot.json --sources ../hargow-courses/releases/hargow-teahouse-pilot
```

拆分设计和验收范围见 [架构说明](docs/architecture.md)。秘密、生产账号、私有声音档案与恢复密钥不得提交。
