# 来源与修改声明

## 上游项目

本项目基于开源项目 [**xiaozhi-esp32**](https://github.com/78/xiaozhi-esp32) **v2.4.2** 二次开发。

- 上游版权：Copyright (c) 2025 Shenzhen Xinzhi Future Technology Co., Ltd. / Project Contributors
- 上游许可：MIT License

## 本项目的修改内容

针对微雪 **Waveshare ESP32-S3-Touch-LCD-3.49**（16 MB Flash 版本）适配与增强：

| 修改 | 说明 |
|---|---|
| 待机翻页时钟 | 独立覆盖层，静置 3 秒后显示。140 px 大号数字，农历 1900–2100 本地计算 |
| SD 卡本地音乐播放器 | 扫描 TF 卡根目录 mp3，支持中文歌名（改 FATFS API 编码为 UTF-8） |
| 自动续播 | 一首播完自动接下一首，末首循环回第一首 |
| 音乐界面深色主题 | 纯黑底 / 白字 / 浅灰按钮 / 红色播放键 |
| 音乐期间忽略唤醒词 | 防止喇叭声音被麦克风拾取导致自问自答；BOOT 键仍可唤起 |
| 字幕背景透明 | 聊天字幕取消奶白衬底 |
| 时钟字体替换 | Arial → Liberation Sans Bold（SIL OFL 1.1），详见 `docs/字体授权说明.md` |
| 移除网络电台 | 保留纯本地音乐播放 |

**音频链路保持原厂**：没有加入任何增益、动态压缩或限幅处理。

> 📌 开发过程中曾尝试过语音响度增强与防失真算法，最终经排查确认「声音发毛」的根因是**喇叭与外壳之间缓冲胶老化的机械共振**（硬件装配问题），因此相关软件处理已全部撤销。详见 README 的排查记录。

## 修改部分版权

Copyright (c) 2026 xiaozhi-3.49-custom contributors

本项目的修改部分同样以 **MIT License** 发布，与上游保持一致。完整许可文本见仓库根目录的 [`LICENSE`](LICENSE)。

## 第三方组件

| 组件 | 许可 |
|---|---|
| [xiaozhi-esp32](https://github.com/78/xiaozhi-esp32) | MIT |
| [ESP-IDF](https://github.com/espressif/esp-idf) | Apache-2.0 |
| [LVGL](https://github.com/lvgl/lvgl) | MIT |
| [ESP-SR](https://github.com/espressif/esp-sr)（唤醒词 / AFE） | MIT / Apache-2.0 |
| [Liberation Sans](https://github.com/liberationfonts/liberation-fonts)（时钟字体） | SIL Open Font License 1.1 |
