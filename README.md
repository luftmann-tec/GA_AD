# Anaerobic Digester – Graef and Andrews Model (Simulink)

[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=luftmann-tec/Anaerobic_Digester_Graef_Andrews_model_and_control)

## Author

**Rodolfo Salazar Peña** - Chemical Engineer

_Luftmann Technologies_

## Description

This repository contains a reproducible implementation of the classical **Graef and Andrews (GA)** dynamic model for anaerobic digesters, developed in **MATLAB/Simulink**; _AD_model.slx_. The model integrates the biological, liquid, and gas phases of the process and includes a pH-based control strategy to prevent acidification. A detailed description of the theoretical framework can be found in the supplementary resource _Anaerobic_Digester_Graef_and_Andrews_Model.pdf_. Parameters of the model in metric system are in _AnaerobicDigestorParameters.m_

## 📌 Overview

Anaerobic digesters are widely used for wastewater treatment and biogas production, but their operation is sensitive to instability caused by volatile fatty acid accumulation and pH drop. The Graef and Andrews model is one of the earliest dynamic models addressing this issue and remains a valuable educational and control-oriented framework due to its relative simplicity.

This project reproduces the simulations presented in **Bailey and Ollis (1986)** with high fidelity, serving as:

* A learning tool for biochemical process modeling

* A baseline for control strategy development

* A collaborative and extensible modeling framework

## ⚙️ Model Structure

The digester is divided into three coupled phases:

### Biological Phase

* Generalized biomass and substrate

* Haldane-type kinetics with substrate inhibition

* Biogas generation (CH₄ and CO₂)

### Liquid Phase

* Dissolved CO₂ and volatile fatty acids (VFAs)

* Acid–base equilibria and ionic interactions

* Gas–liquid mass transfer

* pH calculation and monitoring

### Gas Phase

* Biogas composition (CH₄, CO₂, H₂O vapor, H₂, traces)

* CO₂ partial pressure dynamics

* Inert gas injection for control purposes

## 🎛️ Control Strategy

A **pH-based control system**, originally proposed by Graef and Andrews, is implemented:

* The liquid-phase pH is continuously monitored

* Two relay elements with different thresholds activate staged inert gas injection

* Gas pumping stops automatically once neutral pH is recovered

* Control effectiveness is evaluated via closed-loop simulations

## 📊 Simulations Included

* Open-loop simulations with step changes in:

  * Influent substrate concentration: _run_AD_s.m_

  * Influent flow rate: _run_AD_F.m_

* Closed-loop simulations comparing:

  * Controlled vs. uncontrolled operation: _run_AD_control.m_

  * Acidification prevention under high organic loading: _run_AD_s_control.m_

## 🧰 Requirements

* MATLAB (tested with recent versions)

* Simulink
 
  (Optional) Simscape / SimBiology for future extensions

## 📚 References

* Andrews, J.F., & Graef, S.P. (1971). Dynamic Modeling and Simulation of the Anaerobic Digestion Process, _Anaerobic Biological Treatment Processes_. Ed. by Frederick G. Pohland. Vol. 105. Advances in Chemistry. American Chemical Society, 1971. Chap. 8, pp. 126–162. doi:[10.1021/ba-1971-0105.ch008](https://doi.org/10.1021/ba-1971-0105.ch008).

* Bailey, J.E., & Ollis, D.F. (1986). _Biochemical Engineering Fundamentals_.  2nd ed. Chemical Engineering Series. Singapore: McGraw-Hill, 1986.

* W. Wesley Eckenfelder Jr. _Industrial Water Pollution Control_. 2nd ed. Civil Engineering Series. Singapore: McGraw-Hill, 1989.

## 🚀 Future Work

* Replace relay logic with PID or advanced control schemes

* Enable real-time parameter variation via MATLAB UI elements

* Develop an independent implementation using SimBiology

## 🤝 Contributions

Contributions are welcome. This repository is intended to stimulate **collaborative exploration, educational use**, and **control-oriented research** on anaerobic digestion systems.
