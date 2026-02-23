# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

诗歌创作项目，用于创作和校验古典诗词（律诗/绝句/排律、词、曲、对联）。

## Environment

```bash
# Python 运行
~/.uv/python3/bin/python <script>

# 安装依赖
cd ~/.uv/python3 && uv pip install <package>
```

## 参数说明

**韵书 (--yun-shu):**
- `1` = 平水韵
- `2` = 中华新韵
- `3` = 中华通韵

**词谱 (--ci-pu):**
- `1` = 钦定词谱
- `2` = 龙榆生词谱

## 搜韵 API

`https://api.sou-yun.cn/open`
- `/poem` - 诗词搜索
- `/RhymeCategory` - 韵目查询
- `/rhymeDictionary` - 韵典查询
- `/coupletwords` - 对仗词建议

## 校验符号

- `〇` 平仄正确
- `●` 平仄不合
- `◎` 字不在韵书
- `�` 无法识别

## 创作流程

1. 确定体裁（诗/词/曲/对联）、格式、韵书、主题
2. 用 `reference_builder.py` 提取主题意象词汇
3. 按格律模板起草
4. 用 `poetry_checker.py` 校验并迭代修正
5. 多音字或平仄不合时查询搜韵 API 获取替换建议

## 注意事项

- `scripts/yun/` 是 Couyun 校验库的打包副本，非必要勿修改
- 曲格校验需提供 `--pattern` 或 `--qu-pai`（曲牌定义在 `references/qu_patterns.md`）
- 意象提取只取词汇，避免直接复制原诗句

## 文本文件
- 所有的最终成稿以Markdown格式的文本存入当前目录。
