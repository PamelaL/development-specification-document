>为规范开发，保持代码提交记录以及 git 分支结构清晰，方便后续维护，现规范 git 的相关操作。

# 一、项目各个环境与对应分支管理规范

| 环境 | 分支 | 说明 |
|----- | ----- | ----- |
| 开发分支 | feature/*** 或者 hotfixes/*** | 功能开发分支，先建立Issue再根据功能 (feature/***)或者bug修复类型（hotfixes/***） 命名，“***” 的名称为：序号+‘-’+Issue名。例如“feature/8-schedule-order-payment-h5”|
| UAT环境 | uat | 该分支的操作较为频繁，请本地操作，别用Merge Requests形式。更新本地的Issue分支和uat分支到最新版本，将本地Issue分支合并到本地uat分支，审查代码，有冲突先解决冲突，再push到远程的uat |
| 预生产环境 | release | 将通过功能测试的Issue分支以Merge Requests形式合并到release，做线上数据测试 |
| 生产环境 | master | 将通过测试的release分支以Merge Requests形式合并到master |

# 二、commit提交规范

> 在一个团队协作的项目中，开发人员需要经常提交一些代码去修复bug或者实现新的feature。而项目中的文件和实现什么功能、解决什么问题都会渐渐淡忘，最后需要浪费时间去阅读代码。但是好的日志规范commit messages编写有帮助到我们，它也反映了一个开发人员是否是良好的协作者。

确认需求后在对应项目中创建issue并描述开发内容，在issue下的分支中进行代码提交（方便功能追踪）；

提交基础规范，使用当前应用广泛的 [Angular Git Commit Guidelines](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines) 如下：

1、代码提交时注释内容不能为空，否则不允许提交；

2、注释的内容应当清晰、简洁，包含两部分内容：

   - 第一是本次实现的用户故事/任务/缺陷修复的编号；
   - 第二是文字性的描述，简要讲解实现的功能或修复的解决方案。

    例如：
    # fix 1007758：收银台增加后端管理配置
    # 收银台列表页topbar右侧入口配置数据异常处理


### 具体格式：

```
<type>: <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```
- type: 本次 commit 的类型，诸如 bugfix docs style 等

- scope: 本次 commit 波及的范围

- subject: 简明扼要的阐述下本次 commit 的主旨，在原文中特意强调了几点 1. 使用祈使句 2. 首字母不要大写 3. 结尾无需添加标点

- body: 同样使用祈使句，在主体内容中我们需要把本次 commit 详细的描述一下，比如此次变更的动机，如需换行，则使用 |

- footer: 描述下与之关联的 issue 或 break change，详见案例

### Type的类别说明：

- feat: 添加新特性

- fix: 修复bug

- docs: 仅仅修改了文档

- style: 仅仅修改了空格、格式缩进、都好等等，不改变代码逻辑

- refactor: 代码重构，没有加新功能或者修复bug

- perf: 增加代码进行性能测试

- test: 增加测试用例

- chore: 改变构建流程、或者增加依赖库、工具等

- revert: 回滚到上一个版本

### commit messages格式要求:

```
# 标题行：50个字符以内，描述主要变更内容
#
# 主体内容：更详细的说明文本，建议72个字符以内。 需要描述的信息包括:
#
# * 为什么这个变更是必须的? 它可能是用来修复一个bug，增加一个feature，提升性能、可靠性、稳定性等等
# * 他如何解决这个问题? 具体描述解决问题的步骤
# * 是否存在副作用、风险? 
#
# 如果需要的化可以添加一个链接到issue地址或者其它文档
```
