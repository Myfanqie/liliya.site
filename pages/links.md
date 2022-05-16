---
title: Links -- firends
display: Projects
subtitle: List of projects that I am proud of
description: List of projects that I am proud of
projects:
  React-前端开发方向:
    - name: '胡先生'
      link: 'http://zyx.ee'
      desc: 'react方向的大佬'
      icon: 'i-mdi-clock-fast'
    - name: 'reTypewriter'
      link: 'https://twitter.com/antfu7/status/1505236765447458817'
      desc: 'Smartly reply the steps of your changes at ease.'
      icon: 'i-carbon-keyboard'

  Windows:
    - name: 'Live Draw'
      link: 'https://github.com/antfu/live-draw'
      desc: 'A tool allows you to draw on screen real-time'
      icon: 'i-carbon-brush-freehand'

  Toys:
    - name: '1990 Script'
      link: 'https://github.com/antfu/1990-script'
      desc: 'Make your GitHub history back to 1990'
      icon: 'i-carbon-time'
---

[Sponsors](/sponsors-list)

<ListProjects :projects="frontmatter.projects"/>

<StarsRanking/>
