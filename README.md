# xiaoai-plus

在小爱音箱上获得与豆包近乎一致的端侧实时语音对话体验


## 支持设备

| 型号 | 设备代号 |
| --- | --- |
| Xiaomi 智能音箱 Pro | OH2P |

## 特性

- **实时对话体验**：与移动端豆包一致，支持实时互动、音色定义、连续对话与随时打断。
- **双助手共存**：小爱同学与豆包同学可同时运行，拥有独立的唤醒词。
- **纯本地运行**：程序完全在音箱本机执行，无需搭建外部中转服务器。
- **自定义唤醒**：支持根据需求自定义关键词进行语音唤醒。
- **远场优化**：集成 AEC（回声消除）、NS（降噪）、AGC（增益），大幅提升远场唤醒与对话的准确率。

## 快速开始

> [!IMPORTANT]
> 本教程仅适用于 **Xiaomi 智能音箱 Pro（OH2P）**，**其他型号**的小爱音箱请勿直接使用！🚨

1. 刷机更新小爱音箱补丁固件，开启并 SSH 连接到小爱音箱 👉 [教程](https://github.com/idootop/open-xiaoai/blob/main/docs/flash.md)
2. 开通「豆包端到端实时语音大模型」👉 [火山引擎](https://www.volcengine.com/product/realtime-voice-model)
3. 执行安装脚本（会自动下载并安装最新 release 到 `/data/xiaoai-plus`）
   ```sh
   curl -sSfL https://raw.githubusercontent.com/kslr/xiaoai-plus/main/install.sh | sh
   ```
4. 更新 config.ini 里的模型配置
5. **(可选)** 设置自定义关键词
   ```shell
   cat <<EOF > /data/xiaoai-plus/assets/keywords.txt
   t iān m āo j īng l íng @天猫精灵
   x iǎo d ù x iǎo d ù @小度小度
   n ǐ h ǎo x iǎo zh ì @你好小智
   d òu b āo d òu b āo @豆包豆包
   d òu b āo t óng x ué @豆包同学
   d òu b āo t ong x ue @豆包同学
   d ou b ao t ong x ue @豆包同学
   EOF
   ```
6. 启动程序
   ```shell
   /data/xiaoai-plus/xiaoai_plus_speaker -c /data/xiaoai-plus/config.ini
   ```
4. 设置开机自启动（下载 `boot.sh` 到 `/data/init.sh`）
   ```sh
   curl -L -o /data/init.sh https://raw.githubusercontent.com/kslr/xiaoai-plus/main/boot.sh
   chmod +x /data/init.sh

   # 重启小爱音箱
   reboot
   ```

## 免责声明

- 本项目仅供学习与研究，请确保在合法合规前提下使用。
- 项目与小米、火山引擎/字节跳动无从属关系，品牌与商标归属其各自权利人。

## License

MIT

## 致谢

本项目大量参考 https://github.com/idootop/open-xiaoai 研究和开发。
