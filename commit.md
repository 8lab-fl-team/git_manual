# git commit 规范

## 1. 需要按照规定格式编写commit的Message

### 1.1. Message的首行按照 `<type>(<scope>): <subject>`的格式

出于对自动化扩展性的考虑，`:`之后的空格不可省略。

### 1.2. Message的首行总长度应控制在50字以内

### 1.3. `subject`至少包含变更动作及变更的对象，清晰描述变更

- ✅ fix(Scheduler): 修复状态检查过于频繁的问题
- ❌ fix(Scheduler): 修复一个BUG
- ❌ fix(Scheduler): 状态检查过于频繁

### 1.4. 当`subject`难以准确描述变更时，使用Message的正文部分补充描述

## 2. 单次commit修改的文件数量不能超过30个

## 3. 一个commit只对应一个目的，不能将两个无关目的混合提交

- ❌ feat(Scheduler): 添加了服务注册接口，顺便修复了状态检查过于频繁的问题

## 4. 任何commit都必须保证能够运行，且通过相应测试
