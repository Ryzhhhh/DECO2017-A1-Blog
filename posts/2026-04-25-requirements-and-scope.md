---
title: Identifying the Core Functional Requirements
date: 2026-04-25
author: Runyu Zhou
summary: This post reflects on the core functional requirements of my proposed web application and explains how I decided which features should be essential for the prototype.
tags:
  - requirements
  - scope
  - web-app
---

# Identifying the Core Functional Requirements


我的 A2 Web App Prototype 想做的是一个帮助大学生管理作业 deadline 和学习任务的任务管理应用。这个应用主要帮助同时修多门课的学生解决任务太多、deadline 容易混乱、优先级不清楚的问题。在这个阶段，我认为最重要的不是加入很多复杂功能，而是先判断这个应用真正需要完成什么，才能对用户有实际帮助。

我认为这个应用最核心的功能需求是让用户能够添加、查看、编辑和删除学习任务，因为任务管理是这个应用的主要目的。如果用户不能记录自己的任务，这个应用就无法解决最基本的问题。第二个重要功能是让用户能够按照 deadline 或优先级整理任务，因为学生通常需要快速判断哪些任务最紧急。如果没有这个功能，应用可能只是一个普通列表，而不能真正帮助用户做学习规划。

我也考虑过一些额外功能，例如账户登录、日历同步、提醒通知和个性化主题。这些功能可能会让应用更完整，也能提升用户体验，但它们不是第一版 prototype 必须完成的功能。比如提醒通知很有用，但它会增加技术复杂度，也需要考虑浏览器权限和用户设置。考虑到项目时间有限，我决定先不把这些功能作为核心范围。

我现在最大的取舍是功能范围和完成质量之间的平衡。如果我加入太多功能，应用看起来会更丰富，但也会更难测试、调试和实现。相反，一个范围较小的 prototype 更现实，因为我可以专注于让核心交互稳定工作。因此，我决定第一版先专注于任务创建、任务展示和任务排序，而不是加入太多附加功能。

之后如果核心功能完成得比较稳定，我可以再考虑加入提醒通知、账户系统或日历视图。这样可以保证我的 prototype 既可行，又能清楚展示用户需求和功能需求之间的关系。

