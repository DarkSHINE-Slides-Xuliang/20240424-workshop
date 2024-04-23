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

DarkSHINE Software is a software package, including five parts: <span style="color:#4ec4d4">**DSimu**</span>, <span style="color:#4ec4d4">**DAna**</span>, <span style="color:#4ec4d4">**DDis**</span>, and <span style="color:#4ec4d4">**DPlot**</span>.

<div grid="~ cols-[310px_1fr] gap-2">
<div>

- <span style="color:#4ec4d4">**DSimu**</span> is the <span style="color:#4ec4d4">**simulation program**</span> based on Geant4, characterized by Dark SHINE detector, controlled by <span style="color:#4ec4d4">**yaml configuration**</span>.
- <span style="color:#4ec4d4">**DAna**</span> is a <span style="color:#4ec4d4">**framework for the analysis and reconstruction tools**</span>. It requires the output ROOT file (involving Geometry, DMagnet and DEvent) from DSimu.
- <span style="color:#4ec4d4">**DDis**</span> is the <span style="color:#4ec4d4">**event display**</span> for DSS. (requires Geometry and DEvent)
- <span style="color:#4ec4d4">**DPlot**</span> is a quick plotting program for newbies and lazy man.
- <span style="color:#4ec4d4">**DEvent**</span> is the <span style="color:#4ec4d4">**generic data structure**</span> in DSS.
</div>

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
</div>

---
layout: pageBar
---

# From Baseline 1.0 to 1.6: Detector Construction

Detector Construction Overview

<div grid="~ cols-2 gap-2">

![img](/images/overview_1.0.png){width=600px}

<div class="flex justify-center items-center" style="height: 50vh;">

![img](/images/overview_1.6.png){width=400px}
</div>

</div>  

---
layout: pageBar
hideInToc: true
---

# From Baseline 1.0 to 1.6: Detector Construction

Tracking System

Baseline 1.6 Tracker uses <span style="color:#4ec4d4">**Si micro-strip**</span> ( $30 \mathrm{\mu m}$ ) and <span style="color:#4ec4d4">**non-uniform magnetic field**</span>, while Baseline 1.0 uses non-strip (truth hit) and uniform magnetic field.

| Baseline |                                                  | Magnetic Field                                  | Component                                              | Material                | Center Z (mm)                                   | Size (mm)                                                                                                                                                                            | Layer<br>Number           |
|----------|--------------------------------------------------|-------------------------------------------------|--------------------------------------------------------|-------------------------|-------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
| 1.0      | ![img.png](/images/tracker_1.0.png){width=100px} | $B_y=-1.5 \mathrm{T}$                  | Tagging Tracker<br> <br>Target<br> <br>Recoil Tracker  | Si<br> <br>W<br> <br>Si | -607.83 ~ -7.83<br> <br>0<br> <br>7.73 ~ 180.23 | 10, 20, 0.1<br> <br>10, 20, 0.35<br> <br>10~25, 20, 0.1                                                                                                                              | 7x2<br> <br>1<br> <br>6x2 |
| 1.6      | ![img.png](/images/tracker_1.6.png){width=100px} | ![img.png](/images/bfiled_1.6.png){width=200px} | Tagging Tracker<br> <br>Target<br> <br>Recoil Tracker  | Si<br> <br>W<br> <br>Si | -607.83 ~ -7.83<br> <br>0<br> <br>7.73 ~ 180.23 | 20.1, 10, <span style="color:#4ec4d4">**0.15**</span><br> <br>20, 10, 0.35<br> <br>20.1~50.1, 20, <span style="color:#4ec4d4">**0.15**</span> | 7x2<br> <br>1<br> <br>6x2 |

---
layout: pageBar
hideInToc: true
---

# From Baseline 1.0 to 1.6: Detector Construction

ECAL

| Baseline |                                               | Cell Number | Cell Gap | Gap<br>Material | Cell Components | Material | Size |
|----------|-----------------------------------------------|-------------|----------|-----------------|-----------------|----------|------|
| 1.0      | ![img.png](/images/ecal_1.0.png){width=100px} |             |          |                 |                 |          |      |
| 1.6      | ![img.png](/images/ecal_1.6.png){width=120px} |             |          |                 |                 |          |      |

---
layout: pageBar
hideInToc: true
---

# From Baseline 1.0 to 1.6: Detector Construction

HCAL

In Baseline 1.6, The Number is optimized. The Configuration changed to X-Abs-Y. And SideHCAL is added around the 4 sides of ECAL.

| Baseline |                                               | Cell Number | Cell Gap | Gap<br>Material | Cell Components | Material | Size |
|----------|-----------------------------------------------|-------------|----------|-----------------|-----------------|----------|------|
| 1.0      | ![img.png](/images/hcal_1.0.png){width=200px} |             |          |                 |                 |          |      |
| 1.6      | ![img.png](/images/hcal_1.6.png){width=150px} |             |          |                 |                 |          |      |


---
layout: pageBar
---

# From Baseline 1.0 to 1.6: Versions and Milstones

Many functions and optimizations have been added to the software since 2020.

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

---
layout: pageBar
---

# CI/CD Pipeline and Validation

<br>

<div grid="~ cols-2 gap-2">
<div>

Pipeline to build and draw <span style="color:#4ec4d4">**validation plots**</span> will be triggered in each commit to <span style="color:#4ec4d4">**master**</span> branch.
- Or with keyword `[CI]` or `[VIP]` in the commit message

![img](/images/pipeline.png){width=400px}

</div>
<div>

- Validation plots in the pipeline artifacts, and can be posted on wiki.

![img](/images/validation_plots.png){width=400px}
</div>
</div>

---
layout: pageBar
---

# CPU Performance and Event Storage

<br>

<div grid="~ cols-2 gap-1">
<div>

## DSimu (Simulation)

Current Simulation Speed is <span style="color:#4ec4d4">**x21**</span> faster than Baseline 1.0 (900ms)

![img](/images/SimuTime.png){width=500px}

</div>
<div>

## DAna (Reconstruction)

~9ms per event

![img](/images/DAnaTime.png){width=400px}

</div>
</div>

---
layout: pageBar
---

# Sample Production

<br>

![img](/images/Production.png){width=1100px}

---
layout: pageBar
---

# Tracking

---
layout: pageBar
hideInToc: true
---

# Tracking

We have two seperate Tracking Algorithms. Here only shows the Tracking Efficiency and Energy Resolution of ActsSequencer.

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
(For ECAL Clustering etc., see Qibin & Zhiyu's Talk)

## ECAL Smearing method
The smearing of ECAL is done in reconstruction/analysis level. For each ECAL cell, the energy of hits are summed, then Gaussian function is used to do the smearing, with the mean value set to truth energy and sigma from the formula $\frac{\sigma}{E}=\frac{A}{\sqrt{E}}+B+\frac{C}{E}$ . The A B C parameters are extracted from standalone simulation with optical process enabled.

## Smearing parameter used in analysis
<div grid="~ cols-2 gap-20">

<Transform :scale="0.9">
<br>

|                     | $A\sqrt{MeV}$ |     $A\sqrt{GeV}$    |       $B$      |      $C/MeV$     |
|:-------------------:|:-------------:|:-----------------:|:------------:|:----------------:|
|       R90_LYSO      |    31.62%     |        1.00%      |     0.00%    |     0.0000       |
|       R10_LYSO      |    211.69%    |        6.69%      |     0.00%    |     0.0851       |
|      R90_S9_PWO4    |    134.56%    |        4.26%      |     0.70%    |     0.0001       |
|     R90_S36_PWO4    |    73.32%     |        2.32%      |     0.17%    |     0.7051       |

</Transform>

<div>

**Detailed plots: set1**

![img](/images/setup1.png){width=400px}
</div>

</div>

---
layout: pageBar
hideInToc: true
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
hideInToc: true
---

# Thanks

[Documentations](https://code.ihep.ac.cn/darkshine/darkshine-simulation/-/wikis/home) / [Git Repo](https://code.ihep.ac.cn/darkshine/darkshine-simulation/-/commits/master)


---
layout: pageBar
---
