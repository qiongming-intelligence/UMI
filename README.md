接口人: @高圆寺

# UMI

## 1.环境划分

- 采集环境：`Python 3.9`，用于相机、tracker、夹爪等数据采集。
- 训练/推理环境：`Python 3.10`，用于模型训练与推理，建议与采集环境分开创建。

## 2.采集环境（Python 3.9）

### 2.1创建环境

```shell
conda create -n umi-collect python=3.9 -y
conda activate umi-collect
```

### 2.2 安装基础依赖

```shell
sudo apt update
sudo apt install build-essential zlib1g-dev libx11-dev libusb-1.0-0-dev freeglut3-dev liblapacke-dev libopenblas-dev libatlas-base-dev cmake
sudo apt install libgtk-3-dev
```

### 2.3 安装 `libsurvive`

```shell
cd third_party_lib/libsurvive-master
sudo cp ./useful_files/81-vive.rules /etc/udev/rules.d/
# 连接无线接收器
sudo udevadm control --reload-rules && sudo udevadm trigger # 执行完这步后，如电脑上插有无线接收器请将其拔插一遍。
make
```

### 2.4 安装 Python 依赖

```shell
pip install wxPython==4.2.1 --no-build-isolation
pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
```

## 3. 训练/推理环境（Python 3.10）

### 3.1 创建独立环境

```shell
conda create -n umi-train python=3.10 -y
conda activate umi-train
```

### 3.2 安装训练/推理依赖

- 训练/推理依赖建议参考 `third_party_lib/universal_manipulation_interface-main/conda_environment.yaml` 单独安装。
- 训练命令与数据格式说明见 `scripts/training/TRAIN_UMI_DIFFUSION_POLICY.md`。

## 4. 贡献指南

### 4.1 代码质量

- 遵循仓库中现有的代码风格和约定
- 编写有意义的 commit 信息
- 为复杂逻辑添加注释
- 提交前彻底测试您的更改

### 4.2 文档

- 修改时更新相关文档
- 为新功能包含使用示例

### 4.3 问题报告

报告 Bug 或请求功能时：

1. 搜索现有 issue 以避免重复
2. 使用清晰、描述性的标题
3. 提供详细信息：
   - 环境详情（操作系统、软件版本）
   - 复现步骤（针对 Bug）
   - 预期行为 vs 实际行为
   - 相关日志或截图

### 4.4 获取支持与联系我们

如果您在二次开发或环境配置中遇到难以解决的阻碍，可以通过发 Issue 联系我们，或者直接发送邮件至开源技术支持邮箱：cxy1454272125@126.com，期待您的加入！

## 5. 社区行为准则

### 5.1 我们的标准

有助于创建积极环境的行为示例包括：

- 使用欢迎和包容性的语言
- 尊重不同的观点和经验
- 优雅地接受建设性批评
- 关注什么对社区最有利
- 对其他社区成员表示同理心

不可接受的行为示例包括：

- 使用性化语言或图像，以及任何形式的性关注或挑逗
- 恶意攻击、侮辱或贬低评论，以及人身或政治攻击
- 公开或私下骚扰
- 未经他人明确许可，发布他人的私人信息，如实体地址或电子邮件地址
- 在专业环境中可能被认为不适当的其他行为

### 5.2 违规处理流程与免责责任

- 如果您遭遇了令您不适的行为，或者目睹了他人违反本行为准则，请立刻发送邮件至 yucongcong654@gmail.com 向项目核心维护团队进行举报。所有的举报都将被严格保密处理。
- 项目核心维护团队有权利且有责任对涉嫌违规的内容进行干预，包括但不限于直接删除或隐藏带有攻击性的评论、修改 Commit message、回退破坏性代码或关闭相关的 Issues。
- 对于屡次违规者或情节严重者，维护团队保留直接禁言或永久封禁该账号参与本项目一切活动（包括提 PR、评论 Issue 和加入交流群）的权利。

## 6.社区与交流

- GitHub Issues：用于提交Bug、功能需求和问题咨询。
- 微信群：欢迎添加微信号“13681751192”（小助手）， 加入交流群
- 扫描二维码加入群聊



- 邮箱：cxy1454272125@126.com（用于正式合作和问题咨询）

# 使用指南
Ref: https://dcnk1u1qkxw1.feishu.cn/docx/RhxTd7U2soCXnPxJjS4cX4tFnjd
