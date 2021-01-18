# proj41-accelerate-io-perf-in-gvisor
在2018年开源的gVisor是为容器提供高效、多层防御的应用内核。作为一个容器运行时，它提供了云原生安全（防止容器逃逸）、弹性资源。由于gVisor的IO相关系统调用需要很长的路径，性能较差。本项目希望通过使用io_uring的思维来加速gVisor应用程序的IO性能。

当前项目实现源码：

* https://github.com/google/gvisor

### 所属赛道

2021全国大学生操作系统比赛的“OS功能设计”赛道

### 参赛要求
- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生（2021年春季学期或之后本科毕业的大一~大四的学生）
- 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖
- 请遵循“2021全国大学生操作系统比赛”的章程和技术方案要求

### 项目导师

谈鉴锋
- github https://github.com/tanjianfeng
- email henry.tjf@antgroup.com

### 难度

中等

### 特征

- 用 Golang 语言实现
- 使用高级语言在用户态实现跨系统的应用内核

### 文档

- [gVisor doc](https://gvisor.dev/)
- [io_uring](https://kernel.dk/io_uring.pdf)

### License

- [Apache-2.0](https://opensource.org/licenses/Apache-2.0)

## 预期目标

### 注意：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标

### 第一题：在Sentry内核里为应用程序支持io_uring

- 让gVisor容器中的应用程序可以通过io_uring的APIs，完成批量IO操作（主要是read, write操作）

目标：通过read/write功能测试.

### 第二题：io_uring性能调优

- 编写IO基准测试程序；
- 调优Sentry内部io_uring后端实现

目标：利用IO基准测试程序，出具IO性能优化报告。

### 第三题：通过io_uring加速Sentry内核向host kernel调用（主要是read, write操作）

作为io_uring的后端，除了部分可以通过Sentry page cache的IO操作，剩余的IO操作仍然需要丢给host kernel。

- 让这部分可以通过io_uring的方式从sentry调用到host kernel上。

目标：利用IO基准测试程序，出具IO性能优化报告。