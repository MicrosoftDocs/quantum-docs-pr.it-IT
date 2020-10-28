---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Operazione EstimateEnergy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713751"
---
# <a name="estimateenergy-operation"></a>Operazione EstimateEnergy

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacchetto [](https://nuget.org/packages/)


Stima l'energia della molecola sommando l'energia fornita dai singoli termini di Jordan-Wigner.

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a>Descrizione

Questa operazione si basa in modo implicito sulla convenzione di indicizzazione della selezione.

## <a name="input"></a>Input

### <a name="jwhamiltonian--jordanwignerencodingdata"></a>jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Il Jordan-Wigner hamiltoniana.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di campioni da utilizzare per la stima del termine aspettative.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

Energia stimata della molecola