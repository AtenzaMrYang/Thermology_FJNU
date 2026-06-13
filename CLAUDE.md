# CLAUDE.md — Thermology_FJNU

## 项目概述

高等教育出版社《热学》（秦允豪版）部分课后习题解答的 LaTeX 汇编。习题按章节组织，每题包含题目和解答，可编译为习题册（隐藏解答）或完整版（显示解答）。

## 编译命令

```bash
cd 热学作业
xelatex 热学习题解答.tex
```

或使用 latexmk：`latexmk -xelatex 热学习题解答.tex`

### 隐藏解答模式

取消主文件第 52 行 `% \excludecomment{solution}` 的注释，重新编译即可生成纯习题册（不含解答）。

## 项目结构

```
Thermology_FJNU/
├── README.md
├── CLAUDE.md
└── 热学作业/
    ├── 热学习题解答.tex          # 主文件：文档类、宏包、格式定义
    ├── 热学习题解答.pdf          # 编译输出
    └── 章节/
        ├── 导论.tex
        ├── 分子动理论的平衡态理论.tex
        ├── 热力学第一定律.tex
        └── 热力学第二定律与熵.tex
```

## 环境要求

- **编译器**: XeLaTeX（ctexart 文档类需要）
- **发行版**: TeX Live 2026
- **宏包依赖**: ctex, geometry, hyperref, amsmath, amssymb, amsthm, mathtools, tikz, siunitx, xcolor, comment, tcolorbox

## 代码规范

### 题目与解答

- 题目使用 `question` tcolorbox 环境，背景色 LightBlue，边框 cyan
- 解答使用 `solution` 环境，以 cyan 色粗体 "解答" 开头
- 每道题目独立编号，格式为 `{题目X.X.X}`（对应教材章.节.题号）

### 数学格式

- 微分算符使用 `\mathrm{d}`（如 `\,\mathrm{d}x`）
- 物理量使用斜体，单位使用 `\si{}` 命令（siunitx 包），前加 `\,` 空格
- 矢量/平均值使用 `\overline{}` 或 `\bar{}`
- 下标：摩尔量用 `\mathrm{m}`（如 `V_\mathrm{m}`），初始/终态用 `\mathrm{i}`/`\mathrm{f}`

### 章节文件

- 每个章节文件以 `\newpage\section{章节名}` 开头
- 通过主文件 `\input{章节/文件名.tex}` 引入

### 单位表示

使用 siunitx 包，格式：`数值 \,\si{单位}`

示例：
- `300 \,\si{K}`
- `0.101 \,\si{MPa}`
- `\si{J \cdot mol^{-1} \cdot K^{-1}}`
- `\si{kg/m^3}` → 建议改为 `\si{kg\,m^{-3}}`

### 绘图

使用 TikZ 在 `center` 环境中绘制 p-V 图或 T-S 图，线条颜色统一使用 `cyan`。

### 关键宏包与颜色

- `LightBlue`: RGB(226, 247, 254) — 题目框背景
- `SierraBlue`: RGB(192, 207, 222) — 已定义但当前未使用
- `cyan`: tcolorbox 边框 / 解答标签 / TikZ 图形线条

## 注意事项

- `question` 环境第一个参数可选（默认 `breakable`），第二个参数为标题/编号
- 若需要求导后令自变量为某值，使用 `\left.\frac{\mathrm{d}F}{\mathrm{d}x}\right|_{x=x_0}`
- `\excludecomment{solution}` 控制解答显示/隐藏