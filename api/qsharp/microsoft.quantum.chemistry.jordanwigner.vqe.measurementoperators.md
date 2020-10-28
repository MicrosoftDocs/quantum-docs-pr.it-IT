---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713681"
---
# <a name="measurementoperators-function"></a>MeasurementOperators (funzione)

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacchetto [](https://nuget.org/packages/)


Calcola tutti gli operatori di misurazione necessari per calcolare l'aspettativa di un termine di Jordan-Wigner.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Input

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Numero di qubits necessari per simulare il sistema molecolare.


### <a name="indices--int"></a>indici: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice contenente gli indici di qubit a cui viene applicato ogni operatore Pauli.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)

Tipo del termine del Jordan-Wigner.



## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Matrice di operatori di misurazione (ognuno dei quali è una matrice di Pauli).