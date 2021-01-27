---
title: Caricamento di dati classici
description: Informazioni su come caricare un set di dati personalizzato per eseguire il training di un modello di classificazione con il Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7ebfe085e50d4647fdb1027250cf3134f8d8f8c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856463"
---
# <a name="load-and-classify-your-own-datasets"></a>Caricare e classificare i propri set di impostazioni

In questa breve esercitazione si apprenderà come caricare un set di dati personalizzato per eseguire il training di un modello di classificazione con Quantum Development Kit (QDK).

È consigliabile usare un formato di serializzazione standardizzato, ad esempio [file JSON](https://en.wikipedia.org/wiki/JSON) , per archiviare i dati.
Questi formati offrono una compatibilità elevata con Framework diversi come Python e l'ecosistema .NET.
In particolare, è consigliabile usare il modello per il caricamento dei dati, in modo che sia possibile copiare e incollare il codice direttamente dagli esempi.

## <a name="template-for-loading-your-datasets"></a>Modello per il caricamento dei set di impostazioni

Si supponga di avere un set di dati di training $ (x, y) $ of size $N = $2, in cui ogni istanza $x _i $ of $x $ include tre funzionalità: $x _ {I1} $, $x _ {I2} $ e $x _ {i3} $.
Il set di dati di convalida ha la stessa struttura.
Questi set possono essere rappresentati da un `data.json` file simile al seguente:

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Esempio di utilizzo del modello

Si supponga di avere un set di dati di piccole dimensioni con le altezze e i pesi dei diversi gatti e cani. Questo set di dati è molto piccolo per eseguire il training di un modello, ma sarà sufficiente per illustrare il processo di caricamento di un set di dati.

| Altezza (m) | Weight (kg) | Animale |
|-----------|------------|--------|
| 0.54      | 30         | Cane    |
| 0,30      | 8          | Gatto    |
| 0,91      | 44         | Cane    |
| 0,86      | 31          | Cane    |
| 0,32      | 5         | Gatto    |
| 0,25      | 4          | Gatto    |

Il processo è:

- Per prima cosa, è necessario separare il set di dati in training e convalida. In questo caso, è possibile adottare solo i primi tre esempi per il training e il resto degli esempi per la convalida. In generale, è consigliabile campionare in modo casuale il set di dati di training e convalida per evitare distorsioni indesiderate nei dati di training.
- In secondo luogo, è necessario assegnare un'etichetta numerica a ogni classe. Si noti che, per il momento, la libreria QML ammette solo problemi di classificazione binaria. Si assegnerà quindi l'etichetta 0 alla classe `Dog` e il numero 1 alla classe `Cat` .
- Infine, il modello viene compilato usando i dati del set di dati. Si noti che per i set di dati di grandi dimensioni è necessario compilare uno script di piccole dimensioni per generare automaticamente il modello dal set di dati specifico. Lo script dipenderà dal formato originale del set di dati.

Per il set di dati il `data.json` file è:

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Caricamento dei dati

Una volta che i dati sono stati serializzati come file JSON, è possibile caricarli in usando le librerie JSON fornite con la lingua host scelta.

### <a name="python"></a>[Python](#tab/tabid-python)

Python fornisce il [ `json` pacchetto predefinito](https://docs.python.org/3.7/library/json.html) per l'uso di dati serializzati in JSON:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

La piattaforma .NET Core fornisce il [ `System.Text.Json` pacchetto](https://www.nuget.org/packages/System.Text.Json) per l'uso di dati serializzati in JSON:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Passaggi successivi

A questo punto è possibile iniziare a eseguire i propri esperimenti con i propri set di impostazioni. Prova diversi classificatori e set di dati e contribuisci alla community che condivide i risultati.
