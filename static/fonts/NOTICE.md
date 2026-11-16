# 字体来源与处理

本站正文使用 Noto Serif SC（思源宋体）的按需子集，文件名前缀 kam-serif 只是站内命名，
字体本身未改名，字体家族在 CSS 里叫 "Kam Serif" 以免与系统已装的同名字体冲突。

- 上游：https://github.com/notofonts/noto-cjk （Noto Serif SC VF，SIL OFL 1.1）
- 处理：fontTools varLib.instancer 固定字重，pyftsubset 按站点实际用字裁切，转 woff2
- kam-serif-regular.woff2：400 字重，2343 字（其中 CJK 2031）
- kam-serif-semibold.woff2：600 字重，434 字（其中 CJK 352，用于标题与正文加粗）
- 许可：见同目录 LICENSE（SIL OFL 1.1）

## 复现

需要 Python 3 与 fonttools、brotli：

```bash
python -c "from fontTools.ttLib import TTFont; from fontTools.varLib.instancer import instantiateVariableFont as i; f=TTFont('NotoSerifSC-VF.ttf'); i(f,{'wght':400}).save('s400.ttf')"
python -m fontTools.subset s400.ttf --text-file=scripts/fonts/chars-body.txt --flavor=woff2 --output-file=kam-serif-regular.woff2
```

字符集来自构建后的 public/ 页面正文与 frontmatter 标题；新增内容若出现子集外的字，
浏览器会回落到系统宋体，不影响阅读。