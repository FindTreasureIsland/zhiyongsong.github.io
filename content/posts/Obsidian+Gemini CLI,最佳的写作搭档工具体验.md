---
title: Obsidian+Gemini CLI,最佳的写作搭档工具体验
subtitle: ""
date: 2025-10-06T12:50:24+08:00
lastmod: 2025-10-06T12:50:24+08:00
draft: false
author: CRIO
authorLink: ""
description: ""
license: ""
images: []
tags:
  - 产品分析
categories:
  - 产品
  - 技术
featuredImage: https://pic1.zhimg.com/70/v2-bda2c57d9737a47e2124afb9139d54d0_1440w.avis?source=172ae18b&biz_tag=Post
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
### 引子

我以前使用Notion较多，之前对于Obsidian并不是太感冒。但是后来发现Notion很多AI相关功能都要收费，且当时Notion尚不支持离线模式，后来就逐渐开始尝试使用Obsidian来进行Markdown写作。  
  
用了Obsidian之后，我才逐渐认识到了Obsidian和Notion其实完全是两个不同的产品。从折腾党的角度来看，Obsidian的开放性为其带来了更多的玩法和乐趣。  
  
最终让我完全放弃Notion，转用Obsidian的原因，是发现了其分屏用法，极大地提升了我的效率，因此现在我已经几乎完全放弃Notion了。  
  
然而，Obsidian并非没有槽点，其对AI的支持一直是个短板。虽然有很多社区插件可以支持AI写作，但是说实话，其产品的成熟度和用户体验都很糟糕，可能试用一下尚可，但若要重度使用，总感觉功能上仍有不足。  
  
相比之下，Notion提供的Notion AI则完善许多，且与Notion的诸多工具打通，用户体验的完整性也更佳。奈何Notion太不厚道了，Notion PRO收了一次费，Notion AI还要再收费。  
  
加之Obsidian的双屏模式在一定程度上弥补了缺少优秀AI插件的遗憾，所以我仍义无反顾地将Obsidian作为了我的主力知识库和写作工具。

### 对Obsidian上各种AI插件的吐槽

目前Obsidian上的各类AI插件，我基本都尝试过一遍，但使用下来都相当令人失望。

**Text Generator**

Github开源地址：  
  
[https://github.com/nhaouari/obsidian-textgenerator-plugin](https://link.zhihu.com/?target=https%3A//github.com/nhaouari/obsidian-textgenerator-plugin)  
  
Text Generator是我在Obsidian上使用的第一个插件，但也是最快放弃的一个。最开始装它的原因就是看到它和OB的融合。Text Generator没有单独的聊天窗口，而是通过斜杠命令或命令面板使用其功能。它融入到用户的写作过程中，可理解为在原有写作中增加了AI能力。  
  
然而缺点也很明显，Text Generator仅能辅助用户生成文档，且该工具只是对LLM模型进行了简单的套壳，因此内容生成质量平平。插件安装试用后，我便直接卸载了，因为它对我的写作实在没有任何帮助。  
  

![](https://pic3.zhimg.com/80/v2-81fad99b3149c041571920b2c4e8c1d4_1440w.webp)

**Smart Composer**
Github开源地址：  
[https://github.com/glowingjade/obsidian-smart-composer](https://link.zhihu.com/?target=https%3A//github.com/glowingjade/obsidian-smart-composer)  
  
Smart Composer安装后，在右侧边栏提供了独立的AI交互窗口。Smart Composer在产品形态和使用体验上很像Vibe Coding的Cursor，但可能由于用户可自定义LLM，因此在不同LLM上的体验差异巨大。我通过Deepseek和Openrouter尝试切换了多个大模型，但文档的输出质量同样平平。此外，我发现Obsidian的AI插件普遍存在一些通病：由于仅以插件形式存在，它们难以提供流畅的用户体验。无论是信息流的输出，还是用户操作的交互，都存在不流畅和卡顿的情况。这些小问题最终导致我放弃了这些插件应用，因为若需每日重度使用，我实在无法忍受如此糟糕的用户体验。

![](https://pic2.zhimg.com/80/v2-8f644051095dea5c0450c9615c73698b_1440w.webp)

**总结**

我也尝试过其他一些AI插件，其实这些插件工具的问题都大同小异。  
通过对这些插件工具的使用，我也在思考为何它们无法满足大家对Obsidian上AI产品的要求，我的理解如下：

- 目前Obsidian上的插件基本上都号称可以开放支持各种模型，看起来支持的模型很全面，用户可按需配置。但深入分析便会发现问题很明显：不同模型由于能力差异，其实需要专门的系统提示词和产品设计与之配合，且需进行完备测试后方能开放使用。从这点上可以观察到，目前号称支持多种模型的AI产品，主要是一些简单的Chatbox类工具（尽管像Cursor这类编程工具也号称可以支持，但它们仍以自己推荐的主要模型为主）。对于具有一定复杂性和专业性的产品，反而不适合这种开放模型的方式。
- 插件类产品由于仅作为工具的插件存在，很难与产品更好地融合，因此无法提供一体化的用户体验。

### Obsidian分屏模式

在写作中，AI工具其实主要有几个作用：

- 资料查询；
- 通过和AI对话，辅助梳理写作思路；
- 辅助写作或润色。  
      
    这几个功能其实基本上贯穿了我们写作的整个过程。

**资料查询**

由于目前不同的AI各有其擅长方向，因此在查询资料时，往往需要多个AI工具辅助完成。例如，有时我会使用ChatGPT，有时则通过Perplexity来检索资料。  
  
由于在不同写作场景下，对资料的要求往往不同，因此一个AI工具仍无法完全满足我的需求。加之对于一些我尚不了解的领域，可能也无从知晓如何提问，此时多询问几个AI工具，也更容易补充我的知识盲区。

**整理写作思路**

通过与AI对话，可以很好地梳理和理顺写作逻辑。你可以要求AI从你期望的角度提出一些想法和见解，而这些在以前的写作前期是很难解决的。

**辅助写作和润色**

关于这部分，不同的人可能有不同的看法。有些人喜欢将提纲交给AI，让AI完全代写。而另一些人则享受写作的乐趣，因此这部分会选择自己动手。  
  
我更倾向于这部分自己去写，因为写作其实是我们学习和思考的过程，这部分我认为才是写作最核心和最重要的环节。我也很乐意写完后，让AI帮我检查，并提出一些写作和改进建议。

**为什么我推荐采用分屏模式**

以前我会打开多个窗口，一个是写作窗口，一个是AI窗口。你会发现这个过程对于写作而言非常割裂。因为实际上在写作中，这几个过程并非线性，而是可能反复并行的动作。

- 我在整理思路时，会再去查询一些之前遗漏的资料或素材。
- 我在写作中若有新的想法，也会重新整理思路并调整写作大纲，当然这个过程中也可能会再补充查询一些资料。  
    所以实际上在整个过程中，我会不断进行工具和窗口的切换。  
    而分屏模式则解决了我的这个问题。  
    通过分屏，我可以边查边写、边聊边写、边写边聊、边写边查，通过一个界面并行完成多项工作，从而大大提升了我的效率。

![](https://pic4.zhimg.com/80/v2-a8ecde1131f3bbedb353eb1063db86cb_1440w.webp)

  
Obsidian分屏+标签页+网页浏览器功能的灵活组合，让Obsidian的生产力一下子得到了最大程度的放大，这也是我义无反顾地放弃Notion，开始使用Obsidian的最大原因。

### Obsidian和Gemini CLI的配合使用

虽然通过Obsidian的分屏模式+标签页+网页浏览器的功能可以解决AI查询和AI对话的问题，但却无法解决知识库检索+AI辅助写作的问题。

**Obsidian+Cursor模式**

因为Obsidian的Vault实际上就是一个本地文件夹，因此网上有一些采用Cursor+Obsidian的方案。  
  

![](https://pic2.zhimg.com/80/v2-59cec1ea40c447c49a9ed9c7384a4671_1440w.webp)

  
但是有两个原因让我对这种方案非常反感：

- 我好不容易在一个软件里可以完成所有工作，现在却又要我切换到另外的软件，再次在不同软件中来回切换，我很难接受这种方式。
- Cursor毕竟并非为写作而生，因此其界面非常不适合进行写作。实际上在让AI辅助我写作的过程中，我也需要自己编辑文档，因此我很在意写作体验。  
      
    因此我一直在寻找更优雅的方案。

**Obsidian+Gemini CLI模式**

之前我其实一直没有太理解Gemini CLI这类产品的产品逻辑。上周我有一个产品想法，想快速制作一个产品原型Demo，因此开始研究Vibe Coding工具。  
  
之前我一直使用Cursor或Trae这类工具，但看到网上说Gemini CLI目前每天可有1000次调用机会，且很多人对其编程能力评价很高，因此想体验一番。  
  
由于Gemini CLI要求Google的OAuth认证，且需要严格的魔法环境，所以经过一番折腾，最终总算安装好了Gemini CLI的工作环境。  

![](https://pic3.zhimg.com/80/v2-9751aed487c78aacc5fb96e04cd6122c_1440w.webp)

  
**Gemini CLI**绝对是只有工程师才能构思出的AI工具产品。  
  
我仍记得第一次使用电脑时，那还是386年代，最开始接触的编程其实就是基于Basic的命令编程，当时人机交互主要通过CLI界面。鼠标和Windows发明后，乃至智能手机时代，各种用户友好的GUI已成为人机交互的主流。然而在各类企业级领域，包括服务器后端、数据库开发、网络设备等复杂或专业领域，CLI仍是主流。  
  
我记得以前我们进行路由器开发时，当时主要的功能开发都是基于CLI完成的。对于大型核心路由器，WebUI或GUI一直处于开发鄙视链的底端。  
  
所以针对开发人员提供的AI编程工具，推出CLI化的工具就再自然不过了。  
  
在CLI下，用户可以在任何路径下启用Gemini CLI的功能，这提供了自然的工作上下文，使Gemini CLI能更好地与工程师协同工作。  
  
鉴于Gemini CLI的特点，因此在Obsidian中，通过Terminal插件便可很好地将其集成进来。  
  
Obsidian Terminal是一款可在Obsidian中操作Shell的社区插件。  
  
GitHub地址：[https://github.com/polyipseity/obsidian-terminal](https://link.zhihu.com/?target=https%3A//github.com/polyipseity/obsidian-terminal)

![](https://pic1.zhimg.com/80/v2-70e35609457d79a987f8f3ec7056b50e_1440w.webp)

  
  
所以使用Obsidian+Terminal+分屏功能，终于可以支持我所期望的Obsidian与AI写作场景了：

![](https://pic3.zhimg.com/80/v2-bda2c57d9737a47e2124afb9139d54d0_1440w.webp)

### Obsidian+Gemini CLI+Hugo的升级玩法

国庆节在家里继续折腾，在看了很多人通过MD写博客的方法后，也萌生了通过Obsidian进行博客写作和发布的想法。  
  
最后在GitHub的Page功能中，通过Hugo搭建了一个个人博客网站：

![](https://picx.zhimg.com/80/v2-d6b3416df02eb9f60dfb3dbabafcae9b_1440w.webp)

  
在搭建GitHub个人博客网站时，网站源代码和发布后的文件往往会分别同步到不同的代码仓库。以前大家推荐的方法是通过GitHub的自动化工作流来完成的。  
  
但现在可以通过集成的Gemini CLI，输入一句话：‘同时同步到两个仓库’，便可搞定。  
  
此外，还可以在Obsidian中通过Shell Command插件，将这条命令直接整合为一个系统命令或一个快捷键，便可搞定。