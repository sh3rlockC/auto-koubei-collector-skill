# auto-koubei-collector-skill

[![Release](https://img.shields.io/github/v/release/sh3rlockC/auto-koubei-collector-skill.)](https://github.com/sh3rlockC/auto-koubei-collector-skill./releases)
[![Downloads](https://img.shields.io/github/downloads/sh3rlockC/auto-koubei-collector-skill./total)](https://github.com/sh3rlockC/auto-koubei-collector-skill./releases)
[![License](https://img.shields.io/github/license/sh3rlockC/auto-koubei-collector-skill.)](https://github.com/sh3rlockC/auto-koubei-collector-skill./blob/main/LICENSE)


一个可复用的 OpenClaw Skill，用于从汽车之家车型口碑页批量采集“最满意 / 最不满意”评价，并导出 Excel。

## 功能

- 支持汽车之家车型口碑分页抓取
- 支持 `最满意` / `最不满意` 双维度
- 支持自动探测总页数
- 导出 Excel
- 生成 validation 校验报告

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

## Release 内容

- `.skill` 包
- GitHub 自动生成源码包

## License

MIT