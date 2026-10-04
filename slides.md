---
# You can also start simply with 'default'
theme: neversink
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Let your CI catch your stack overflows, before they hit your testing or the field
# apply unocss classes to the current slide
class: text-center
color: dark
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
# transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
hideInToc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
---

# Let your CI catch your stack overflows, before they hit your testing or the field

<small>

Open Source + Zephyr Developer Summit - 07-09. October 2026 | Prague, Czechia <br>

Paul Würtz, Juan-Felipe Gutiérrez-Gómez

</small>

:: note ::

<div class="center">



<div class="fw-200" >

Slidev template neversink by <a href="https://todd.gureckislab.org" class="ns-c-iconlink">Todd Gureckis</a>

</div>
</div>

---
hideInToc: true
---

# Intro + Motivation

<v-click>

What we will talk about today:

<Toc />

</v-click>

---
title: Build CLI + CI - sample applications
---

# Build CLI - sample applications - stackcheck OK

![](/stackuseCLI.png)

* similar to `size` after building shows known stack size
* tries to show limitations of the numbers found
* warns on found stack overflows

---
title: CLI applications sample regular+overflow
level: 2
---

# Build CLI - sample applications - stackcheck overflow

<img src="/stackoverflowCLI.png" width="65%">

---
layout: top-title-two-cols
color: dark
title: gitlab CI single board stack diff
level: 2
---

:: title ::

### Build CI - sample applications - stackdiff of a single board

:: left ::

* proposal for a single board build
    * [gitlab MR comment](https://gitlab.com/potwal/cannectivity/-/merge_requests/3#note_3895740814) on merge request
    * pipeline fails on an detected overflow
    * shows all functions with changed stacksizes
    * \[no ideas how to give info on changes on the calltree so far - any ideas welcome :)\]
    * gives more details of each threads worst call path and unresolved functions in it's calltree

![alt text](/gitlab-pipeline.png)

:: right ::

![alt text](/gitlab-stackdiff.png)



---
layout: top-title-two-cols
color: dark
title: github CI multi board stack check
level: 2
---

:: title ::

### Build CI - sample applications - stackcheck_boards of an array of boards

:: left ::

* proposal for many targets
    * [github PR comment](https://github.com/paulwuertz/cannectivity/pull/1#issuecomment-5881633701) on pull requests
    * example for Release and Debug build comment
    * pipeline fails on an detected overflow on any board
    * grouped by each threads stack use for each board - notice the effects drivers and different instructions have on utilization


:: right ::

![alt text](/githubPR.png)


---
src: pages/02_howToStackEstimation.md
---

<!-- this page will be loaded from './pages/toc.md' -->

Contents here are ignored
