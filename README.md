# 📹 Progetto Deep Vision: Classificazione CIFAR-10 con CNNs

**Autore:** Alessio Cicilano

Questo repository contiene un progetto completo di Deep Vision per la classificazione di immagini del dataset **CIFAR-10** (10 classi) utilizzando TensorFlow e Keras.

## 🎯 Obiettivi del Progetto

L'obiettivo principale è confrontare le prestazioni di diverse architetture di reti neurali per la classificazione delle immagini:

* Stabilire un **baseline** utilizzando una rete neurale MLP (Multi-Layer Perceptron)
* Costruire e ottimizzare **architetture CNN** (Convolutional Neural Networks) con diversi livelli di complessità
* Implementare tecniche di **regolarizzazione** (L2, Dropout, Early Stopping) per prevenire l'overfitting
* Applicare **Data Augmentation** per migliorare la generalizzazione del modello
* Sperimentare con diverse **profondità di rete** (CNN a 2 e 3 blocchi) e confrontare ottimizzatori (Adam vs SGD)
* Analizzare le prestazioni attraverso **matrici di confusione** e analisi degli errori
* Condurre uno **studio di ablazione** per quantificare l'impatto di ciascuna tecnica di regolarizzazione

## 📊 Risultati Principali

La CNN a 3 blocchi con regolarizzazione completa ha mostrato le migliori prestazioni. Lo studio di ablazione ha dimostrato che il **Data Augmentation** è stata la tecnica singola più importante per la generalizzazione.

### Studio di Ablazione (Risultati su Test Set)

| Variante (Componente Rimosso) | Test Accuracy | Differenza vs Controllo |
| :--- | :---: | :---: |
| **A (Controllo - Tutto Attivo)** | **~77.5%** | **N/A** |
| B (Senza Data Augmentation) | ~68.0% | -9.5% |
| C (Senza L2) | ~76.1% | -1.4% |
| D (Senza Dropout) | ~75.8% | -1.7% |

### Analisi degli Errori

L'analisi del miglior modello (vedi `figuras/confusion_matrix_BEST_...png`) mostra che gli errori di classificazione più comuni si verificano tra classi visualmente simili a risoluzione 32x32px:

* **Gatto ↔ Cane**
* **Camion ↔ Auto**
* **Uccello ↔ Aereo**

## 🛠️ Come Eseguire il Progetto

1. Clona il repository:
   ```bash
   git clone [URL_DEL_TUO_REPO]
   cd Desafio_DeepVision-main
   ```

2. (Opzionale) Crea un ambiente virtuale e installa le dipendenze:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Su Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. Apri il notebook principale in Jupyter o Google Colab:
   ```bash
   jupyter notebook ElDesafioDeepVision_AlessioCicilano.ipynb
   ```

4. Esegui tutte le celle del notebook dall'inizio alla fine. Il notebook genererà automaticamente tutte le figure e i risultati nelle cartelle `figuras/` e `results/`.

## 📁 Struttura del Progetto

```
Desafio_DeepVision-main/
├── ElDesafioDeepVision_AlessioCicilano.ipynb  # Notebook principale
├── README.md                                   # Questo file
├── requirements.txt                            # Dipendenze Python
├── ENVIRONMENT.md                              # Informazioni sull'ambiente
├── figuras/                                    # Grafici e visualizzazioni
│   ├── confusion_matrix_BEST_*.png
│   ├── data_visualization.png
│   ├── typical_errors_BEST_*.png
│   └── [altri grafici...]
└── results/                                    # Metriche e risultati
    ├── metrics_*.json
    ├── comparison_*.md
    └── [altri file di risultati...]
```

## 🔬 Metodologia

Il progetto è diviso in 5 fasi principali:

1. **Fase 1:** Configurazione dell'ambiente, caricamento dati e trazabilità
2. **Fase 2:** Confronto tra diverse architetture di reti neurali (MLP vs CNN)
3. **Fase 3:** Ottimizzazione e fine-tuning della rete neurale
4. **Fase 4:** Miglioramenti e analisi degli errori
5. **Fase 5:** Metriche finali e conclusioni

## 🧬 Riproducibilità

Per garantire la riproducibilità dei risultati:

* **Seed Globale:** `42`
* **Versioni Software:** Vedi `ENVIRONMENT.md`
* **Dataset:** CIFAR-10 (caricato automaticamente da Keras)
* **Risultati Completi:** Disponibili nella cartella `results/`

## 📝 Note

Tutti i grafici nella cartella `figuras/` e i risultati in `results/` sono stati generati automaticamente dal notebook durante l'esecuzione degli esperimenti.

## 📄 Licenza

Vedi file `LICENSE` per i dettagli.
