---
title: 提示词工程化工具：promptfoo
subtitle: ""
date: 2025-09-15T12:50:24+08:00
lastmod: 2025-09-15T12:50:24+08:00
draft: false
author: CRIO
authorLink: ""
description: ""
license: ""
images: []
tags:
  - 提示词
  - 提示词工程
  - AI工具
categories:
  - 创业
featuredImage: https://pic1.zhimg.com/70/v2-a816141683ff94aa678d757f64f64a96_1440w.avis?source=172ae18b&biz_tag=Post
featuredImagePreview: ""
hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false
toc:
  enable: true
  auto: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
mapbox:
share:
  enable: true
comment:
  enable: true
library:
  css:
  js:
seo:
  images: []
---
## 什么是promptfoo

`promptfoo` 是一个用于评估和红队测试 LLM 应用的 CLI 和库。  
`promptfoo`的主要功能：

- **构建可靠的提示、模型和 RAG**，使用针对您用例的基准测试
- **保障应用安全**，通过自动化的[红队测试](https://link.zhihu.com/?target=https%3A//www.aidoczh.com/promptfoo/docs/red-team/)和渗透测试
- **加速评估**，通过缓存、并发和实时重载
- **自动评分输出**，通过定义[指标](https://link.zhihu.com/?target=https%3A//www.aidoczh.com/promptfoo/docs/configuration/expected-outputs/)
- 作为[CLI](https://link.zhihu.com/?target=https%3A//www.aidoczh.com/promptfoo/docs/usage/command-line/)、[库](https://link.zhihu.com/?target=https%3A//www.aidoczh.com/promptfoo/docs/usage/node-package/)或[CI/CD](https://link.zhihu.com/?target=https%3A//www.aidoczh.com/promptfoo/docs/integrations/github-action/)使用
- 使用 [OpenAI](https://zhida.zhihu.com/search?content_id=263061277&content_type=Article&match_order=1&q=OpenAI&zhida_source=entity)、[Anthropic](https://zhida.zhihu.com/search?content_id=263061277&content_type=Article&match_order=1&q=Anthropic&zhida_source=entity)、[Azure](https://zhida.zhihu.com/search?content_id=263061277&content_type=Article&match_order=1&q=Azure&zhida_source=entity)、Google、[HuggingFace](https://zhida.zhihu.com/search?content_id=263061277&content_type=Article&match_order=1&q=HuggingFace&zhida_source=entity)、开源模型如 [Llama](https://zhida.zhihu.com/search?content_id=263061277&content_type=Article&match_order=1&q=Llama&zhida_source=entity)，或集成自定义 API 提供商以支持[任何 LLM API](https://link.zhihu.com/?target=https%3A//www.aidoczh.com/promptfoo/docs/providers/)

## 为什么选择promptfoo

- **开发者友好**：promptfoo 快速，具有实时重载和缓存等生活质量功能。
- **久经考验**：最初为服务于超过 1000 万用户的 LLM 应用构建。我们的工具灵活，可以适应多种设置。
- **简单、声明式的测试用例**：无需编写代码或使用繁重的笔记本即可定义评估。
- **语言无关**：使用 Python、Javascript 或其他任何语言。
- **共享与协作**：内置共享功能和网页查看器，便于与团队合作。
- **开源**：LLM 评估是商品，应由 100% 开源项目提供，无附加条件。
- **私有**：此软件完全本地运行。评估在您的机器上运行，并与 LLM 直接通信。

## 工作流程和理念

基于TDD的思路，通过测试驱动提示词的调试。

![](https://picx.zhimg.com/v2-c612c870697e2ecbddf1cddbfc2dd9d5_1440w.jpg)

  
工作过程：

- 定义测试用例
- 配置评估
- 运行评估
- 分析结果

## promptfoo验证框架Demo

可以使用Jupyter Notebook来运行和验证：

![](https://pic3.zhimg.com/v2-08eb3f8fe695429cc6357e648caea63e_1440w.jpg)

### 安装

- 命令：brew install promptfoo. 说明：在MAC上安装，也可以使用npm、或者npx安装。

![](https://pic1.zhimg.com/v2-44e6d81fa8412e330e5b2abc846f62a6_1440w.jpg)

  

- 验证安装  
    通过!promptfoo --version命令查看安装情况：

![](https://pic1.zhimg.com/v2-5611c9a3b256de987b26fb04e25ee4f4_1440w.jpg)

### 配置promptfoo：

**创建提示词文件**

```text
%%writefile prompts.txt
You're an ecommerce chat assistant for a shoe company.
Answer this user's question: {{name}}: "{{question}}"
---
You're a smart, bubbly chat assistant for a shoe company.
Answer this user's question: {{name}}: "{{question}}"
```

**完成promptfooconfig.yaml文件的配置**

```text
%%writefile promptfooconfig.yaml
prompts: [prompts.txt]

providers: 
  - id: deepseek:deepseek-chat
    config:
      temperature: 0.7
      max_tokens: 4000
      apiKey: sk-00d1539cb5894e7daeb23099646c165b

tests:
  - vars:
      name: Bob
      question: Can you help me find a pair of sandals on your website?
  - vars:
      name: Jane
      question: Do you have any discounts available?
  - vars:
      name: Dave
      question: What are your shipping and return policies?
  - vars:
      name: Jim
      question: Can you provide more info on your hiking boot options?
  - vars:
      name: Alice
      question: What is the latest trend in winter footwear?
```

这里特别需要注意：

- 这个配置文件中，对于空格和对其有很严格的要求。每一行都需要严格缩进2个空哥，不能使用Tab缩进。

**运行和评估**

- 运行命令行：

```text
!npx promptfoo eval -c promptfooconfig.yaml
```

- 产生测试报告  
    测试结果的总结：

![](https://pic1.zhimg.com/v2-b694af73c80fb0f708370a2723a7bb8e_1440w.jpg)

测试结果的记录：

![](https://pic2.zhimg.com/v2-c51cbc23227619ac4d42eef975cb8aa7_1440w.jpg)

**查看最终的评估报告**

通过命令行查看：

```text
!npx promptfoo view
```

![](https://picx.zhimg.com/v2-5762f293972d3a7e71b7b1089c5d9a57_1440w.jpg)

## 数据集的生成

在测试中，测试的数据集是核心，如何可以批量化生成测试集？  
可以通过如下的命令：

```text
promptfoo generate dataset -o tests.**yaml**
```

run_promptfoo_onMAC