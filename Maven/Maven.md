# 生命周期

- default：默认。进行项目编译打包等工作的阶段
  - validate：验证。验证项目所有必要信息可用
  - compile：**编译**。编译项目源代码
  - test：测试。不用打入最后的包中
  - package：**打包**。
  - verify：验证。
  - install：**安装**。
  - deploy：部署。
- clean：清理。为执行接下来的操作进行必要的清理，删除target文件夹
- site：站点。生成项目报告，站点、发布站点

# 坐标

## 版本规范

maven通过版本规范来定位一个项目

- groupId：团体
- artifactId：项目标识符
- version：版本
- packaging：项目类型，默认jar

## 依赖范围

scope标签可以指定依赖运行于哪种特定环境

- compile：编译依赖范围。默认依赖范围，针对编译、测试、运行都有效
- test：测试依赖范围。只针对测试有效
- provided：只针对编译和测试有效，对运行无效
- runtime：只针对测试和运行有效。