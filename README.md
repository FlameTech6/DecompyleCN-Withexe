目前仓库内编译版并非最新汉化版
# 本仓库已弃用，请移步新仓库 https://github.com/FTech6/pycdc-CN-with-build/

---

本仓库提供了 Decompyle++ (pycdc) 项目的汉化编译版本，包含了 pycdc.exe 与 pycdas.exe 这两个可执行文件，目前仅包含了 Windows x64 平台的构建

汉化工作者及编译人员：@FlameTech6

---

# 以下内容译自 pycdc 项目官方仓库，有少量删减与修改

---

# Decompyle++ 简介
**Python 字节码的反汇编器/反编译器**  

Decompyle++ 是一个将Python字节码(.pyc)文件转换回可读Python源代码的工具，支持从Python 2.4到最新版本的所有字节码格式

## 功能组件
- `pycdas`: Python字节码反汇编器
- `pycdc`: Python字节码反编译器

## 依赖要求
- CMake 3.12+
- C++17兼容编译器
- Python 3.x (仅测试需要)

---

# 使用方法
**运行 pycdas**，PYC 反汇编器：
`./pycdas [PATH TO PYC FILE]`
字节码反汇编结果将打印到 stdout

**运行 pycdc**，PYC 编译器：
`./pycdc [PATH TO PYC FILE]`
反编译后的 Python 源代码会打印到 stdout
任何错误都会打印到 stderr

**标记代码对象**：
这两种工具都支持 Python marshalled 代码对象，输出自`marshal.dumps(compile(...))`.

要使用此功能，请指定`-c -v <version>`必须指定版本，因为对象本身不包含版本元数据

---

# 命令行参数说明
## pycdc
| 选项 | 参数 | 适用工具 | 说明 | 必需条件 | 示例 |
|------|------|----------|------|----------|------|
| `-h`<br>`--help` | 无 | pycdas/pycdc | 显示帮助信息 | 可选 | `./pycdc -h` |
| `-v` | `<x.y>` | pycdas/pycdc | 指定Python版本 | 使用`-c`时必需 | `./pycdc -v 3.8` |
| `-c` | 无 | pycdas/pycdc | 处理序列化代码对象 | 需配合`-v`使用 | `./pycdc -c -v 2.7` |
| `-o` | `<文件路径>` | pycdas/pycdc | 指定输出文件 | 可选 | `./pycdc -o output.py` |

---

# 作者、许可证、署名
##核心开发者
* Michael Hansen 
* Darryl Pogue

##其他贡献者：
* charlietang98
* Kunal Parmar
* Olivier Iffrig
* Zlodiy

它根据 GNU 通用公共许可证第 3 版的条款发布；
详情请查看 LICENSE 文件
