# KRICT-ChemDX-Hackathon: Temperature-dependent thermoelectric figure-of-merit (ZT) curve prediction

**Main contribution**

This project aims to develop a multi-task model to predict the temperature dependence of the thermoelectric figure-of-merit (ZT) for different inorganic materials.

**Other functionalities**
1. ZT-T curve extrapolation
2. Visualization of data via Elemental Mover Distance (ELMD)

### Authors
- **Andre K. Y. Low**
- **Hyunwoo Jang**  
- **Sanghyuk Lee**
- **Jose Recatala-Gomez**  
- **Harikrishna Sahu**  

## Background
Thermoelectric (TE) materials convert heat into electricity through the Seebeck effect or use electricity to generate a temperature gradient via the Peltier effect. Their efficiency is related to the dimensionless figure of merit, **ZT = (S²σT)/κ** , where **S** is the Seebeck coefficient, **σ** is electrical conductivity, **T** is absolute temperature, and **κ** is thermal conductivity. Ideal thermoelectric materials exhibit high electrical conductivity, a large Seebeck coefficient, and low thermal conductivity. Understanding the temperature dependence of **ZT** is crucial for optimizing performance, identifying peak efficiency, and ensuring long-term stability. Since electrical and thermal transport properties evolve with temperature, analyzing **ZT(T)** provides insights into carrier transport mechanisms and material degradation. This knowledge is essential for designing efficient thermoelectric generators, including multi-stage systems where different materials operate at varying temperatures.

## Dataset
We used the LitDX dataset, provided as an xlsx file (data/estm.xlsx) that contains zT, S, σ, and κ values at different temperatures for various inorganic materials. The same dataset was used as input to a generative design workflow (Figure 1) and to perform property prediction and a
physics-informed zT-T curve fitting.
## Methodology
We used a structure-agnostic model CrabNet algorithm for adjusting the property predictions based on domain expertise. Candidate materials are sampled in a combinatorial manner considering their chemical similarity based on Earth mover’s distance.
![image](https://github.com/user-attachments/assets/c59f22bb-dc86-4686-997a-d3c7029bdae6)

Figure 1. Generative design workflow to perform property prediction and a physicsinformed ZT-T curve fitting.

## Installation
Create a new Conda environment and install dependencies with requirements.txt.
Clone or download the directory.

## Using our work
The main dataset is in estm.xlsx.
Start by training the Crabnet model following crabnet.ipynb, or you can use our trained model pretrained_crabnet.pth.
![image](https://github.com/user-attachments/assets/88f9f0c0-9986-4731-b63d-604790a15bd2)

The zt-t curves.ipynb notebook shows the implementation of the ZT curve workflow, meant to convert the predictions from Crabnet into a complete curve.
![image](https://github.com/user-attachments/assets/0d977726-411e-4bb3-b6af-9c7b8fbd7260)

The elmd_plotting.ipynb notebook provides a means of visualizing all structures in the dataset. The end goal is to select compositions within 'columns' of materials to be predicted by the Crabnet model for further experimental validation.
![image](https://github.com/user-attachments/assets/0cad4d7c-8e29-4adc-9276-492f2e7253ed)



