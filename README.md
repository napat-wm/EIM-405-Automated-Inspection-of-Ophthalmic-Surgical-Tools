<div align="center">

<h1>CDE4301 Interim Report</h1>

<p><b>Automated Inspection of Ophthalmic Surgical Tools</b></p>

<p>In collaboration with the Singapore National Eye Centre (SNEC)</p>

<br>


<img src="assets/nus-logo.png" width="400" alt="National University of Singapore">

<br>

<p>Project EIM-405: Automated Inspection of Ophthalmic Surgical Tools</p>

<br>

<table>
<tr>
<th>Student Name</th>
<th>Student No.</th>
</tr>
<tr>
<td>Wongmuang Napatsawan</td>
<td>A0287748E</td>
</tr>
<tr>
<td>Christoph Franz Cuan</td>
<td>A0288302E</td>
</tr>
</table>

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
- [1.4 Project Objectives, Scope, and Value](#14-project-objectives-scope-and-value)

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
- [Appendix A: Mechanical Design Drawings](#appendix-a-mechanical-design-drawings)
- [Appendix B: Interactive CAD Models](#appendix-b-interactive-cad-models)
- [Appendix C: Bill of Material from NUS Central Workshop](#appendix-c-bill-of-material-from-nus-central-workshop)
- [Appendix D: Gantt Chart for Semester 2](#appendix-d-gantt-chart-for-semester-2)

---
# List of Figures
Figure 1. xx []

---

# List of Tables 
Table 1. xx []

---

