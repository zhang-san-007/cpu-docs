## 安装verilator v5.008

Verilator 是一款开源的支持 Verilog 和 SystemVerilog 仿真工具。它能够将给定的电路设计翻译成 C++ 或者 SystemC 的库等中间文件，最后使用 C/C++ 编写激励测试，去调用前面生成的中间文件，由 C/C++ 编译器编译执行，来完成仿真。此外，它也具有静态代码分析的功能。


执行如下命令，安装verilator:
```shell title="shell"
# 1.安装依赖项
sudo apt-get install git help2man perl python3 make autoconf g++ flex bison ccache
sudo apt-get install libgoogle-perftools-dev numactl perl-doc
sudo apt-get install libfl2  # Ubuntu only (ignore if gives error)
sudo apt-get install libfl-dev  # Ubuntu only (ignore if gives error)
sudo apt-get install zlibc zlib1g zlib1g-dev  # Ubuntu only (ignore if gives error)

#2. 克隆项目
git clone git@gitee.com:jiuqulangan_prj/verilator-v5.008.git


#3. 执行安装过程
unsetenv VERILATOR_ROOT  #For csh; ignore error if on bash
unset VERILATOR_ROOT     #For bash
cd verilator-v5.008
autoconf         # Create ./configure script
./configure      # Configure and create Makefile
make -j `nproc`  # Build Verilator itself (if error, try just 'make')，这个命令耗时较久，请请耐心等待
sudo make install
```

## 安装gtkwave.md
GTKWave 是用来查看波形的一款图形化软件，我们将使用它查看 Verilator 生成的电路波形图，完成对硬件逻辑的调试。 安装的方法非常简单，只需要使用一行命令：
```shell
$ sudo apt install gtkwave
```
