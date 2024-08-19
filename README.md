本仓库提供了 Decompyle++ 项目的编译版本，包含了 pycdc.exe 与 pycdas.exe 这两个可执行文件。

# Pycdc的简介(译自pycdc官方仓库地址)

## Decompyle++
***Python 字节码反汇编器/反编译器***

Decompyle++ 旨在将编译后的 Python 二进制码转换回有效的二进制码的和人类可读的Python源代码。

虽然其他项目已经实现了这些功能，而与之不同的是，Decompyle++ 是独一无二的，因为它追求于支持来自任何版本 Python 的二进制码。

Decompyle++ 包括二进制码反编译器（pycda）和 反编译器（pycdc）。

顾名思义，Decompyle++ 是用 C++ 编写的。 如果您想做出贡献，请在 github 上 Fork 我们，项目网址为 https://github.com/zrax/pycdc

### 用法
要运行 pycdas (PYC反汇编器)： `./pycdas [ PYC 文件的路径 ]`
二进制码的反汇编结果将会被打印到标准输出。

要运行 pycdc (PYC反编译器)： `./pycdc [ PYC 文件的路径 ]`
将反编译的 Python 源代码将会被打印到标准输出。 任何错误都会打印到标准程序。

编组代码对象： `marshal.dumps(compile(...))`.
这两种工具都支持 Python 编组的代码对象，作为 的输出。

要使用此功能，请在命令行上指定 `-c -v <version>` -必须指定版本，因为对象本身不包含版本元数据。
