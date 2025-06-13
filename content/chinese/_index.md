---
weight: 0
title: "樊刹 - 学习心得分享"
description: "樊刹 专业 学习 考证"
categories: ["主页"]
---


{{< intro
  introtitle="樊刹"
  id="introHome"
>}}
{
  "onexit": "manageDefaultCollapsibleSidebar();toggleExtendMenu(false);",
  "oncomplete": "window.location.href = './';",
  "steps": [
    {
      "title": "樊刹",
      "intro": "欢迎访问范庙网站。<br>通过这个循序渐进的入门指南，您将发现几个网站功能。",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(false);"
    },{
      "title": "图标",
      "intro": "网站图标允许返回主页。",
      "element": "#globalLogo",
      "position": "right",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(false);"
    },{
      "title": "导航栏",
      "intro": "位于屏幕顶部的水平条，也称为导航条，包含多种功能，可简化网站上的导航和用户体验。根据窗口宽度，将出现一个扩展菜单，允许显示隐藏的导航栏按钮。",
      "element": "#navbar",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(false);"
    },{
      "title": "搜索",
      "intro": "搜索功能允许搜索整个网站的内容。<br><i>注意：使用正则表达式的高级搜索不可用。</i>",
      "element": "#search",
      "position": "left",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(false);"
    },{
      "title": "打印",
      "intro": "打印功能允许打印当前页面内容。",
      "element": "getFirstVisibleElement('#printButton, #printButtonExtend');",
      "position": "left",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(true);"
    },{
      "title": "二维码",
      "intro": "二维码功能允许显示与当前页面URL关联的二维码。",
      "element": "getFirstVisibleElement('#qrCodeButton, #qrCodeButtonExtend');",
      "position": "left",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(true);"
    },{
      "title": "快捷键",
      "intro": "快捷方式按钮提供对网站上可用快捷方式列表的访问。",
      "element": "getFirstVisibleElement('#shortcutsInfo, #shortcutsInfoExtend');",
      "position": "left",
      "triggerexcept": ["nohover"],
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(true);"
    },{
      "title": "分类",
      "intro": "分类按钮提供对网站的多个分类法的访问。<br><i>注意：仅当至少存在一个分类时，此按钮才可见。</i>",
      "element": "getFirstVisibleElement('#taxonomiesSelector, #taxonomiesSelectorExtend');",
      "position": "left",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(true);"
    },{
      "title": "多语言",
      "intro": "多语言按钮提供对当前页面的多个翻译的访问。<br><i>注意：仅当当前页面存在翻译页面时，此按钮才可见。</i>",
      "element": "getFirstVisibleElement('#langsSelector, #langsSelectorExtend');",
      "position": "left",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(true);"
    },{
      "title": "版本",
      "intro": "版本控制按钮提供网站的其他可用版本。",
      "element": "getFirstVisibleElement('#versionsSelector, #versionsSelectorExtend');",
      "position": "left",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(true);"
    },{
      "title": "关于",
      "intro": "关于按钮提供有关网站的一般信息。",
      "element": "getFirstVisibleElement('#siteInfo, #siteInfoExtend');",
      "position": "left",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(true);"
    },{
      "title": "侧边栏",
      "intro": "屏幕左侧的侧边栏允许浏览网站的所有页面。",
      "element": "#sidebarWrapper",
      "onbeforechange": "toggleSidebar(true,true);toggleExtendMenu(false);"
    },{
      "title": "侧边栏",
      "intro": "可以折叠侧边栏以仅显示主要部分图标。",
      "element": "#sidebarCollapse",
      "onbeforechange": "toggleSidebar(true,true);toggleExtendMenu(false);"
    },{
      "title": "侧边栏",
      "intro": "当侧边栏折叠时，将鼠标悬停在某个部分上以显示关联的子菜单（或单击触摸设备）。<br><i>注意：当窗口宽度小于 1024 像素时，侧边栏默认折叠。</i>",
      "element": "#sidebarUncollapse",
      "onbeforechange": "toggleSidebar(false,true);toggleExtendMenu(false);"
    },{
      "title": "祝贺！",
      "intro": "祝贺！！<br>您现在可以浏览该网站以了解有关该主题的更多信息。<br><i>单击“已完成”以继续载入。</i>",
      "onbeforechange": "manageDefaultCollapsibleSidebar();toggleExtendMenu(false);"
    }
  ]
}
{{< /intro >}}