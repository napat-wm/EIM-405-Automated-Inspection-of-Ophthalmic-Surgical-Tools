<div align="center">

<h1>CDE4301 Interim Report</h1>

<p><b>Automated Inspection of Ophthalmic Surgical Tools</b></p>

<p>In collaboration with the Singapore National Eye Centre (SNEC)</p>

<br>


<img src="assets/nus-logo.png" width="400" alt="National University of Singapore">

<br>

<p>Project EIM-405: Automated Inspection of Ophthalmic Surgical Tools</p>

<br>

<div align="center">

<table>
  <thead>
    <tr>
      <th>Student Name</th>
      <th>Student No.</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Wongmuang Napatsawan</td>
      <td>A0287748E</td>
    </tr>
    <tr>
      <td>Christoph Franz Cuan</td>
      <td>A0288302E</td>
    </tr>
  </tbody>
</table>

</div>

<p><b>Supervisor:</b> Mr. Nicholas Chew</p>

</div>

<br>

---
<h2 align="center">Project Team</h2>

<br>

<div align="center">

<img src="assets/napat.png" width="150" height="150" alt="Napatsawan Wongmuang">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src="assets/christoph.png" width="150" height="150" alt="Christoph Franz Czuan">

<br><br>

<b>Napatsawan Wongmuang</b>
&nbsp;&nbsp;&nbsp;&nbsp;
<b>Christoph Franz Czuan</b>

<br><br>

Biomedical Engineering
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
XX Engineering

</div>
---

---

# Acknowledgment 
We would like to express our sincere gratitude to our supervisor, Mr. Nicholas Chew, for his guidance, constructive feedback, and continued support through the semester. We also extend our appreciation to the Singapore National Eye Centre (SNEC) and the staff for facilitating our hospital visit and providing valuable insights into the clinical workflow and challenges associated with ophthalmic surgical instrument inspection. Finally, we would like to thank the NUS IDP Hub and Centralised Workshop for their technical assistance, facilities and support in the fabrication and production of our prototype components.

---

# Abstract
This interim report documents the development, improvement, and preliminary evaluation of an automated ophthalmic surgical-instrument inspection system developed with the Singapore National Eye Centre (SNEC). Building upon the inherited MEDetect project from the previous cohort with the two linked challenges in mind: acquiring more than one side of the tool images (2D) within a practical physical setup, and improving defect detection accuracy. Semester 1 development included alternative initial concepts of mechanical parts, a final prototype of a transparent-base tray and trolley design, and the training and development of defect detection using Mask R-CNN. The proposed operational camera is the Keyence VS-L160CX, while the machine learning development uses photographs from a handphone camera (iPhone 15). Comparative calculations examine the consequences of camera resolution and field of view for fine instrument tips will be demonstrated alongside an idealised cantilever analysis that estimates camera-arm deformation under assumed loading and stiffness. For the initial Hook Sinskey pilot happened in Semester 1, 226 original images were used for training, validation and test sets. Mask R-CNN among YOLO and DETRs achieved a reported 100% classification accuracy on 20 usable test crops while a full-pipeline accuracy fell to 83.3% across 24 test images, and its wet-condition accuracy was 66.7%. The results indicate promising crop-level defect classification but highlight unresolved limitations in localisation, wet-image robustness and transfer from smartphone to industrial-camera imaging. Semester 2 work will focus on Keyence-native training data, full integration of mechanical and machine learning systems, and the development of user interface for the seamless workflow in a real hospital setting. 
 

---

# Table of Contents

**Preliminary Sections**

- [Abstract](#abstract)
- [List of Figures](#list-of-figures)
- [List of Tables](#list-of-tables)
- [Acronyms](#acronyms)

**1. Introduction**

- [1.1 Clinical Context and Current Inspection Workflow](#11-clinical-context-and-current-inspection-workflow)
- [1.2 Problem Statement and Engineering Need](#12-problem-statement-and-engineering-need)
- [1.3 Project Objectives, Scope, and Value](#13-project-objectives-scope-and-value)

**2. System Requirements and Design Specifications**

- [2.1 Proposed System Overview](#21-proposed-system-overview)
- [2.2 Hardware Design Requirements](#22-hardware-design-requirements)
- [2.3 Software Design Requirements](#23-software-design-requirements)
- [2.4 Performance Specifications and Acceptance Criteria](#24-performance-specifications-and-acceptance-criteria)

**3. System Design and Prototype Development**

- [3.1 Mechanical Design Development](#31-mechanical-design-development)
  - [3.1.1 Initial Concepts and Evaluation](#311-initial-concepts-and-evaluation)
  - [3.1.2 Selected Design](#312-selected-design)
    - [3.1.2.1 Final Tray Design](#3121-final-tray-design)
    - [3.1.2.2 Three-Tier Trolley Design and Camera Arm](#3122-three-tier-trolley-design-and-camera-arm)

- [3.2 Imaging System Design and Feasibility](#32-imaging-system-design-and-feasibility)
  - [3.2.1 Proposed Keyence Camera Configuration](#321-proposed-keyence-camera-configuration)
  - [3.2.2 Comparative Optical Resolution Analysis](#322-comparative-optical-resolution-analysis)

- [3.3 Machine-Learning Prototype Development](#33-machine-learning-prototype-development)
  - [3.3.1 ML Architectures, Detection and Segmentation Paradigms](#331-ml-architectures-detection-and-segmentation-paradigms)
  - [3.3.2 Training Procedure and Dataset Preparation](#332-training-procedure-and-dataset-preparation)
  - [3.3.3 Prototype Testing and Performance Evaluation](#333-prototype-testing-and-performance-evaluation)
  - [3.3.4 Prototype Selection and Analysis](#334-prototype-selection-and-analysis)

**4. Discussion, Limitations and Semester 2 Plan**

- [4.1 Interpretation and Limitations](#51-interpretation-and-limitations)
- [4.2 Prioritised Semester 2 Milestones](#52-prioritised-semester-2-milestones)

**5. Conclusion**

- [Conclusion](#6-conclusion)

**References and Appendices**

- [References](#references)
- [Appendix A: Existing Surgical Tray](#appendix-a-existing-surgical-tray)
- [Appendix B: Interactive CAD Models](#appendix-b-interactive-cad-models)
- [Appendix C: Bill of Material from NUS Central Workshop](#appendix-c-bill-of-material-from-nus-central-workshop)
- [Appendix D: Gantt Chart for Semester 2](#appendix-d-gantt-chart-for-semester-2)

---
# List of Figures
Figure 1. Value Proposition

---

# List of Tables 
Table 1. Value Proposition
Table 2. Acceptance Criteria

---

# Acronyms

| Acronym | Definition |
|:--------|:-----------|
| SNEC | Singapore National Eye Centre |
| HS | Hook Sinskey |
| CP | Chop Phaco |
| FM | Forceps Macpherson |
| FU | Forceps Utrata |
| FNR | False-negative Rate |
| DETR | Detection Transformer |
| YOLO | You-Only-Look-Once |
| M6 | Metric fastener with nominal 6 mm thread diameter |

---
# 1 Introduction

## 1.1 Clinical Context and Current Inspection Workflow

The inspection of ophthalmic surgical instruments at the Singapore National Eye Centre (SNEC) remains largely manual, requiring nurses to examine tools at multiple stages before and after surgery and during reprocessing. With over 21,000 cataract procedures annually at the SNEC (SNEC, n.d.) and approximately four inspection checkpoints per procedure or an estimated 84,000 inspections are performed each year. Although tray inspection and counting typically take only one to two minutes, these repetitive tasks add to nurses’ workload and may contribute to inconsistent assessments due to fatigue, varying lighting conditions and subjective judgement. Furthermore, preliminary measurements conducted by the previous MEDetect project team under a microscope identified ophthalmic instrument tip dimensions ranging from approximately 0.18 to 0.42 mm, highlighting the difficulty of identifying subtle defects such as bending, chipping and micro-fractures. These challenges are supported by studies reporting residual debris in nearly two-thirds of reprocessed ophthalmic surgical trays (Dinakaran & Kayarkar, 2002) and foreign material or structural abnormalities in over half of examined ophthalmic handpieces (Zhan et al., 2025). Together, these findings highlight the need for a more consistent and efficient inspection system that supports clinical staff without replacing their professional judgement.

## 1.2 Problem Statement and Engineering Need

e

## 1.3 Problem Objectives, Scope, and Value

This project aims to create a tray-compatible automated inspection aid combining opposing-view imaging with a computer-vision pipeline. Initial algorithmic evaluation focused on the Hook Sinskey (HS) with the chance of future extension including Chop Phaco and Macpherson, and Utrata forceps. The envisioned system counts or localises instruments, evaluates visible damage and flags abnormal or uncertain outcomes for nurse review. It is not intended to replace clinical judgement or independently approve instruments for reuse. The anticipated contribution lies in joining a practical optical-mechanical fixture to defect-focused image analysis rather than improving a model score in isolation.


| **Value proposition** | **Rationale and intended contribution** |
|:---|:---|
| **More consistent defect screening** | The same trained models apply to every tray, reducing variation caused by fatigue, workload, and individual judgement. |
| **Identification of subtle damage** | The model evaluates fine contours, enabling focused analysis of features such as bent, chipped or partially broken tips. |
| **Better use of skilled nursing time** | Automating repetitive screening and instrument counting is intended to reduce routine inspection demands, allowing nurses to focus on clinical judgement and cases requiring further review. |
| **Transparent and auditable decisions** | The proposed workflow prioritises interpretable inspection results, including tool identification, defect classifications and confidence information, while retaining human verification of uncertain findings. |
| **Robustness under realistic inspection conditions** | Since ophthalmic instruments may be wet, reflective or positioned differently during inspection, these conditions are prioritised in prototype evaluation to assess the system's suitability for clinical use. |

<p align="center"><em>Table 1. Value Proposition</em></p>
---
# 2 System Requirements and Design Specifications

## 2.1 Proposed System Overview

The proposed workflow is: **tray positioning → image capture → tool localisation/counting → cropped detail analysis → reviewed result.**

The proposed system was developed to address two limitations of the inherited MEDetect project: the inability to inspect both sides of surgical instruments without manual repositioning and inconsistent defect detection. To address these challenges, the team proposed a transparent-base tray with cameras positioned above and below the instruments. This arrangement aims to improve surface visibility while minimising additional handling by nurses. The inspection process also retains two stages: instrument localisation and counting, followed by detailed defect assessment. This approach was selected because identifying entire instruments and examining fine defects require different levels of image detail.

## 2.2 Hardware Design Requirements

Hardware requirements were established by considering clinical workflow compatibility and imaging consistency. The team prioritised maintaining dimensions similar to the existing SNEC surgical tray to minimise changes to instrument handling and placement. The tray specifications and photographs of the existing tray are provided in Appendix A for reference.

A transparent base was selected to permit imaging from below, while a modular aluminium trolley with a top clear acrylic tier was proposed to support the opposing cameras. Since even small changes in camera positioning may affect image focus and repeatability, mounting stability was identified as an important design consideration alongside optical resolution and field of view.

## 2.3 Software Design Requirements

Given these contextual considerations, the following design specifications were established as target objectives for addressing the identified use cases and pain points. In lieu of a Singapore precedent, numeric targets were informed by the FDA-cleared IDx-DR autonomous AI system, which evaluates ophthalmic images for diabetic-retinopathy screening and reported 87.2% sensitivity and 90.7% specificity (Abràmoff et al., 2018). However, since the proposed system screens surgical instruments as opposed to producing diagnoses, the project establishes stricter ideal-case performance targets than the IDx-DR benchmark.

## 2.4 Performance Specifications and Acceptance Criteria

The resulting design specifications are presented in Table 2, together with their proposed verification methods. Numerical targets were established to guide prototype evaluation, with particular emphasis on minimising false negatives and maintaining practical inspection times. These specifications represent the team's intended performance criteria rather than confirmed achievements, providing a basis for identifying limitations and planning further verification in Semester 2.

| **Design requirement** | **Target** | **Engineering rationale** | **Verification method** |
|:---|:---|:---|:---|
| **Inspection time** | ≤60 s per tray | Reduce processing time compared with the current 1–2-minute manual inspection. | Measure total time from image capture to displayed results. |
| **Defect detection** | FNR ≤5% | Prioritise minimising missed defects due to potential patient-safety consequences. | Evaluate against labelled defective instruments. |
| **Instrument counting** | ≥95% accuracy | Support reliable verification of instrument presence during tray preparation. | Compare predicted counts with actual tray contents. |
| **Wet-condition performance** | Sensitivity ≥90%; FNR ≤10% | Assess performance when moisture and reflections affect instrument visibility. | Evaluate using a separate wet-image test set. |
| **Human verification** | All positive and uncertain cases reviewed | Retain clinical judgement for potentially defective instruments. | Verify that flagged results require user review. |
| **Camera-arm stability** | To be established in Semester 2 | Minimise camera movement that could affect image consistency and focus. | Measure and calculate loaded displacement. |
| **Optical resolution** | Smallest relevant defect must be distinguishable | Ensure sufficient image detail for detecting fine instrument damage. | Calibrate field of view and measure image sampling. |

<p align="center"><em>Table 2. Acceptance Criteria</em></p>
