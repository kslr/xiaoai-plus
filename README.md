# 🤖 xiaoai-plus

[![CI](https://github.com/kslr/xiaoai-plus/actions/workflows/ci.yml/badge.svg)](https://github.com/kslr/xiaoai-plus/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/kslr/xiaoai-plus?include_prereleases)](https://github.com/kslr/xiaoai-plus/releases)
[![Downloads](https://img.shields.io/github/downloads/kslr/xiaoai-plus/total)](https://github.com/kslr/xiaoai-plus/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#%E8%AE%B8%E5%8F%AF-license)
[![Stars](https://img.shields.io/github/stars/kslr/xiaoai-plus?style=social)](https://github.com/kslr/xiaoai-plus)

> **让小爱音箱进化！** 在音箱上获得与「豆包」端到端一致的实时语音对话体验（本机运行、独立唤醒、远场优化）。

---

## 📱 支持设备

| 型号 | 设备代号 |
| :--- | :--- |
| **Xiaomi 智能音箱 Pro** | `OH2P` |

## ✨ 核心特性

- ⚡ **实时对话体验**：与移动端豆包一致，支持实时互动、音色定义、连续对话与随时打断。
- 🎙️ **双助手共存**：小爱同学与豆包同学可同时运行，拥有独立的唤醒词。
- 🏠 **纯本地运行**：程序完全在音箱本机执行，无需搭建外部中转服务器。
- 🗣️ **自定义唤醒**：支持根据需求自定义关键词进行语音唤醒。
- 🛠️ **远场优化**：集成 AEC（回声消除）、NS（降噪）、AGC（增益），大幅提升远场唤醒与对话的准确率。

## 📖 使用指南

### 1️⃣ 基础环境准备
**解锁 SSH 权限：**  
首先需要为你的小爱音箱刷机以获取控制权限，请参考：[解锁教程](https://github.com/kslr/open-xiaoai/blob/main/docs/flash.md)

### 2️⃣ 获取模型能力
**开通大模型：**  
访问火山引擎官网，开通「豆包端到端实时语音大模型」能力：  
👉 [火山引擎产品页](https://www.volcengine.com/product/realtime-voice-model)

### 3️⃣ 部署程序到音箱

1. **下载程序**：前往 [Releases](https://github.com/kslr/xiaoai-plus/releases) 页面，下载与你设备架构匹配的压缩包。
2. **上传文件**：将文件上传到音箱的 `/data/xiaoai-plus` 目录：
   ```shell
   # 示例：使用 SCP 上传
   scp <local_file> root@<device_ip>:/data/xiaoai-plus
   ```
3. **配置文件**：
   ```shell
   cd /data/xiaoai-plus
   cp config.ini.example config.ini
   # 编辑 config.ini 填入你的火山引擎 API 参数
   vi config.ini
   ```

### 4️⃣ 启动运行

通过 SSH 登录音箱后，执行以下命令：
```shell
cd /data/xiaoai-plus
chmod +x xiaoai_plus_speaker
./xiaoai_plus_speaker -c config.ini
```

---

## 🛠️ 高级定制

- **自定义关键词**：
  1. 编辑 `assets/keywords.txt` 文件。
  2. 重新打包或直接同步到设备上测试唤醒效果。

## ⚖️ 免责声明

- 本项目仅供学习与研究使用，请确保在合法合规的前提下操作。
- 本项目与小米（Xiaomi）、火山引擎（Volcengine）/ 字节跳动（ByteDance）无任何官方从属关系，相关品牌与商标归其各自权利人所有。

## 🤝 致谢

本项目基于 [open-xiaoai](https://github.com/idootop/open-xiaoai) 修改与扩展，感谢原作者及社区的贡献。
