# auto-koubei-collector-skill

[![Release](https://img.shields.io/github/v/release/sh3rlockC/auto-koubei-collector-skill)](https://github.com/sh3rlockC/auto-koubei-collector-skill/releases)
[![Downloads](https://img.shields.io/github/downloads/sh3rlockC/auto-koubei-collector-skill/total)](https://github.com/sh3rlockC/auto-koubei-collector-skill/releases)
[![License](https://img.shields.io/github/license/sh3rlockC/auto-koubei-collector-skill)](https://github.com/sh3rlockC/auto-koubei-collector-skill/blob/main/LICENSE)


一个可复用的 OpenClaw Skill，用于从汽车之家车型口碑页批量采集“最满意 / 最不满意”评价，并导出 Excel。

脚本支持终端进度条、`progress.json` 轮询，以及直接推送到飞书 incoming webhook。
导出结果旁也会自动生成同名 `.validation.json`，用于记录校验结果、异常与分页情况。

## 当前能力

- 支持汽车之家车型口碑分页抓取
- 支持 `最满意` / `最不满意` 双维度
- 支持自动探测总页数
- 导出 Excel
- 生成 validation 校验报告
- 支持进度文件和飞书 webhook

## 目录结构

```text
skill/
├── SKILL.md
├── scripts/
│   └── export_autohome_koubei.py
└── references/
```

## 使用示例

```bash
python3 skill/scripts/export_autohome_koubei.py \
  --series-id 8140 \
  --start-page 1 \
  --auto-detect-pages \
  --output ./ZJ启源A06最满意or最不满意_全量.xlsx \
  --workdir /Users/xyc/.openclaw/workspace
```

如果要看进度，可再加：

- `--progress`
- `--progress-file /tmp/job.progress.json`
- `--progress-webhook https://...`
- `--feishu-webhook https://...`
- `--feishu-secret <secret>`

对话框/前端侧最简单的做法是每 1-2 秒读取 `progress.json`，然后展示 `percent`、`stage`、`message`。

## Release 内容

每个 Release 默认包含：

- `.skill` 包
- GitHub 自动生成的源码压缩包

## License

MIT
