# 字体来源与处理

本站字体全部为按需子集，文件名前缀 kam- 只是站内命名；CSS 里的家族名另取
（Kam Serif / Kam Sans / Kam Display），避免与系统已装的同名字体冲突。

## Kam Serif（正文）

- 上游：Noto Serif SC VF，https://github.com/notofonts/noto-cjk
- kam-serif-regular.woff2：400 字重，2343 字（CJK 2031）
- kam-serif-semibold.woff2：600 字重，485 字（标题、正文加粗、档案块、ASCII）

## Kam Sans（小节标题与界面）

- 上游：Noto Sans SC VF，同仓库
- kam-sans-regular.woff2：400 字重，226 字
- kam-sans-semibold.woff2：600 字重，226 字

## Kam Display（文章大标题）

- 上游：得意黑 Smiley Sans v2.0.1，https://github.com/atelier-anchor/smiley-sans
- kam-display.woff2：146 字（现有全部文章标题 + ASCII）
- 该字体本身只有一款倾斜字形，标题的斜势是字体设计，不是合成

## 许可

三套字体均为 SIL OFL 1.1，全文见同目录 LICENSE。

## 处理流程

fontTools varLib.instancer 固定字重，pyftsubset 按站点实际用字裁切，转 woff2。
字符集文件在 scripts/fonts/（正文、粗体、标题、界面四份），新增内容若出现子集外的字，
浏览器会回落到系统字体，不影响阅读。

## 复现

需要 Python 3 与 fonttools、brotli：

```bash
python -c "from fontTools.ttLib import TTFont; from fontTools.varLib.instancer import instantiateVariableFont as i; f=TTFont('NotoSerifSC-VF.ttf'); i(f,{'wght':400}).save('s400.ttf')"
python -m fontTools.subset s400.ttf --text-file=chars-body.txt --flavor=woff2 --output-file=kam-serif-regular.woff2
```

## 许可文件

同目录 LICENSE 为 OFL 1.1 全文，同时适用于 Noto Serif SC、Noto Sans SC 与得意黑。