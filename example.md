---
theme: ./
layout: cover
class: text-left
transition: slide-left
mdc: true
backgroud: '/ATLAS/ATLAS-Logo.png'
authors:  # First author should be the presenter
  - Yulei Zhang: ["INPAC"]
  - Yifan Zhu: ["INPAC"]
  - Qibin Liu: ["TDLI"] 
  - Xuliang Zhu: ["TDLI"]

meeting: "Dark SHINE Seasonal Workshop"
preTitle: "Baseline 1.6 Simulation Framework, and Plans for Baseline 2.0"
---

<br>

<img id="ATLAS" src="/DarkSHINE/DarkSHINE-Logo.png"> </img>

<style scoped>
#ATLAS {
  width: 160px;
  position: absolute;
  right: 3%;
  bottom: 4%;
  /* background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 15%, #146b8c 50%); */
}
</style>

---
layout: pageBar
hideInToc: true
---

# Outline

<br>

<div class="flex justify-center items-center" style="height: 50vh;">

### <Toc />

</div>

---
layout: pageBar
---

# Simulation Framework Overview
<br>

<Transform :scale="1.0">
<div>
```mermaid
mindmap
  root((Dark SHINE Software))
    DSimu
      Signal Generation with Calchep
      Full Simulation
        DEvent: Data Structure
    DAna
      MC Truth Analysis
      Digitization
        Reconstruction
            Tracking
            Calorimeters
    Tools
      DDis: Event Display
      DPlot: Validation
    Pipeline
      Validation History
      Wiki
    Other Projects
      Fast Simulation
      Dark SHINE Webpage
      New Event Display
```
</div>
</Transform>

---
layout: pageBar
---

# Versions and Milstones

```mermaid
timeline
    section Baseline 1.0
    2021 Dec. : Baseline 1.0
    section Baseline 1.5
    2022 Apr. : DSimu Optical Simulation
    2022 Jul. : DSimu v1.5.0
    2022 Dec. : DSimu v1.6.0
    section Baseline 1.6
    2023 Oct. : Bla
    2023 Nov. : Bla
    2024 Apr. : [YF] Parser
        : [YF] Tracking
```

---
layout: pageBar
---

# Version Update Detail

<br>

## blabla

---
layout: pageBar
---

# Validation and Pipeline

---
layout: pageBar
---

# CPU Performance and Sample Production

Hover on the bottom-left corner to see the navigation's controls panel

## Simulation

## Reconstruction

---
layout: pageBar
---

# Multi-threading for DSimu

<br>

---
layout: pageBar
---

# Tracking Performance

Two 3D plots for display

Try to interact with the graphs 🥰

<div grid="~ cols-2 gap-20">

<Transform :scale="0.65">
<PlotlyGraph filePath="Graph/plotly2.json" graphWidth="900"/>
</Transform>

<Transform :scale="0.65">
<PlotlyGraph filePath="Graph/plotly3.json" graphWidth="900"/>
</Transform>

</div>

---
layout: pageBar
---

# Calorimetry

---
layout: pageBar
---

# Future Plans and Timeline

---
layout: pageBar
---

# Summary

---
layout: center
class: "text-center"
---

# Thanks

[Documentations](https://code.ihep.ac.cn/darkshine/darkshine-simulation/-/wikis/home) / [Git Repo](https://code.ihep.ac.cn/darkshine/darkshine-simulation/-/commits/master)


---
layout: pageBar
---
