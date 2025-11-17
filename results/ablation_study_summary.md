
## Estudio de Ablación (Base: Modelo 3-Block,)

| Variante (Componente Retirado) | Augment | L2 | Dropout | Val Accuracy | Test Accuracy | Caída (Test) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **A (Control)** | **Sí** | **Sí** | **Sí** | **0.7641** | **0.7664** | **0.00%** |
| B (Sin Augment) | No | Sí | Sí | 0.7575 | 0.7554 | 1.10% |
| C (Sin L2) | Sí | No | Sí | 0.7638 | 0.7612 | 0.52% |
| D (Sin Dropout) | Sí | Sí | No | 0.7770 | 0.7724 | -0.60% |
