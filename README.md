# Anaerobic Digester – Graef and Andrews Model (Simulink)

This repository contains a reproducible implementation of the classical **Graef and Andrews (GA)** dynamic model for anaerobic digesters, developed in **MATLAB/Simulink**. The model integrates the biological, liquid, and gas phases of the process and includes a pH-based control strategy to prevent acidification.

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

  * Influent substrate concentration

  * Influent flow rate

* Closed-loop simulations comparing:

  * Controlled vs. uncontrolled operation

  * Acidification prevention under high organic loading

## 🧰 Requirements

* MATLAB (tested with recent versions)

* Simulink
 
  (Optional) Simscape / SimBiology for future extensions

## 📚 References

* Andrews, J.F., & Graef, S.P. (1971). _Dynamic Modeling and Simulation of the Anaerobic Digestion Process_.

* Bailey, J.E., & Ollis, D.F. (1986). _Biochemical Engineering Fundamentals_.

* Batstone et al. (2002). ADM1 Model.

## 🚀 Future Work

* Replace relay logic with PID or advanced control schemes

* Enable real-time parameter variation via MATLAB UI elements

* Develop an independent implementation using SimBiology

## 🤝 Contributions

Contributions are welcome. This repository is intended to stimulate **collaborative exploration, educational use**, and **control-oriented research** on anaerobic digestion systems.
