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

# Overview
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

<Transform :scale="0.8">
<div>
```mermaid
timeline
    section Baseline 1.0
    2020 Aug - 2021 Dec : Baseline 1.0
    section Baseline 1.5
    2022 Apr - Jun : Add DSimu optical simulation
                   : Add truth information - DTruth
                   : Optimized simulation speed, event storage, and data transmission between DAna processors
    2022 Jul - Sep : Add SideHCAL
                   : Add DSimu flexible Biasing / BiasParticle
                   : Add DSimu arguments
    2022 Oct - Dec : Add Staggered ECAL
                   : Add HCAL MC Calibration
                   : Optimized DAna Event Classification
    2023 Jan - Mar : Add DAna Riemann Fitting 
                   : Fixe Sensitive Detector bug
                   : Optimize Sensitive Detector Speed
```
</div>
</Transform>

---
layout: pageBar
hideInToc: true
---

# Versions and Milstones

<Transform :scale="0.9">
<div>
```mermaid
timeline
    section Baseline 1.6
    2023 Apr - Jun : Add Vertexing, and GNN Tracking 
                   : Add ECAL TopoClustering, ML IO
                   : Add DDis MC Particle Propagation
    2023 Nov - Dec : Add DSimu truth filter
                   : More flexible RecECAL
                   : Add options to tune Tracking speed and resolution
    2024 Feb - Apr : Add DAna ActsSequencer
                   : Optimized Tracking Algorithm
                   : Add Tracking Parser
```
</div>
</Transform>

---
layout: pageBar
---

# Pipeline and Validation

<br>

<div grid="~ cols-2 gap-2">
<div>

Pipeline will be triggered when :
- **Merge request** to master branch
- With keyword `[CI]` or `[VIP]` in the commit message

![img](/images/pipeline.png){width=400px}

</div>
<div>

Validation plots will be downloadable in the artifacts.

![img](/images/validation_plots.png){width=400px}
</div>
</div>

---
layout: pageBar
---

# CPU Performance and Sample Production

<br>

<div grid="~ cols-2 gap-1">
<div>

## DSimu Simulation

Current Simulation Speed is **x21** faster than Baseline 1.0 (900ms)

![img](/images/SimuTime.png){width=500px}

</div>
<div>

## DAna Reconstruction

<br><br>

![img](/images/DAnaTime.png){width=400px}

</div>
</div>

---
layout: pageBar
---

# CPU Performance and Sample Production

---
layout: pageBar
---

# Tracking Performance (ActsSequencer)

Tracking Efficiency and Energy Resolution 

<Transform :scale="0.9">

| Efficiency | Inclusive | Signal 5 MeV |
|------------| ---   | --- |
| Tagging | 99.94% | 99.94% |
| Recoil | 99.76% | 80.49 %|

</Transform>

<div grid="~ cols-2 gap-20">

<Transform :scale="0.65">
<PlotlyGraph filePath="/Graph/Acts_TagTrk_P__cut2.json"/>
</Transform>

<Transform :scale="0.65">
<PlotlyGraph filePath="/Graph/Res_dActs_RecTrk_P_1_precut.json"/>
</Transform>

</div>

---
layout: pageBar
---

# Calorimetry
<br>

## ECAL Smearing method
The smearing of ECAL is done in reconstruction/analysis level. For each ECAL cell, the energy of hits are summed, then Gaussian function is used to do the smearing, with the mean value set to truth energy and sigma from the formula $\frac{\sigma}{E}=\frac{A}{\sqrt{E}}+B+\frac{C}{E}$ . The A B C parameters are extracted from standalone simulation with optical process enabled.

## Smearing parameter used in analysis
<div grid="~ cols-2 gap-20">

|                     | $A\sqrt{MeV}$ |     $A\sqrt{GeV}$    |       $B$      |      $C/MeV$     |
|:-------------------:|:-------------:|:-----------------:|:------------:|:----------------:|
|       R90_LYSO      |    31.62%     |        1.00%      |     0.00%    |     0.0000       |
|       R10_LYSO      |    211.69%    |        6.69%      |     0.00%    |     0.0851       |
|      R90_S9_PWO4    |    134.56%    |        4.26%      |     0.70%    |     0.0001       |
|     R90_S36_PWO4    |    73.32%     |        2.32%      |     0.17%    |     0.7051       |

<div>

**Detailed plots: set1**

![img](/images/setup1.png){width=500px}
</div>

</div>

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
hideInToc: true
---

# Thanks

[Documentations](https://code.ihep.ac.cn/darkshine/darkshine-simulation/-/wikis/home) / [Git Repo](https://code.ihep.ac.cn/darkshine/darkshine-simulation/-/commits/master)


---
layout: pageBar
---
