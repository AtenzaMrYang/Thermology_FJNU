# 《热学》部分课后习题解答

高等教育出版社《热学》（秦允豪版）部分课后习题的解答汇编，使用 LaTeX 排版。习题解答根据教学需要做了适当删改，并更正了收录习题中的部分勘误。

## 编程语言

LaTeX（使用 `ctexart` 文档类）

## 目录结构

```
Thermology_FJNU/
├── .gitignore                  # Git 忽略规则
├── README.md                   # 项目内容的简单说明
└── 热学作业/
    ├── 热学习题解答.tex         # 主文件（文档类、宏包、格式定义、入口）
    ├── 热学习题解答.pdf         # 编译生成的 PDF
    └── 章节/
        ├── 导论.tex
        ├── 分子动理论的平衡态理论.tex
        ├── 热力学第一定律.tex
        └── 热力学第二定律与熵.tex
```

## 编译方式

### 环境要求

- **编译器**：XeLaTeX（`ctexart` 文档类需要 XeLaTeX 或 LuaLaTeX 编译）
- **发行版**：TeX Live 2026
- **编译引擎版本**：
  - XeTeX 3.141592653-2.6-0.999998
  - LaTeXmk 4.87

> `\excludecomment{solution}` 指令已预留在主文件头部，取消注释即可隐藏所有解答、生成纯习题册。

## 联系方式

- **作者**：郑锦阳 (MrYang)
- **审阅**：郭文锑
- **GitHub**：[AtenzaMrYang/Thermology_FJNU](https://github.com/AtenzaMrYang/Thermology_FJNU)

## 致谢

本项目代码经 DeepSeek 审阅并修正了其中存在的问题。
