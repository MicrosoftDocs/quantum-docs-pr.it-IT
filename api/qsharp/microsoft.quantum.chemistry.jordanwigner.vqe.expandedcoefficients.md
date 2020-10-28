---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713712"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients (funzione)

Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacchetto [](https://nuget.org/packages/)


Espande la rappresentazione compatta dei coefficienti di Jordan-Wigner per ottenere un mapping uno-a-uno tra questi e i termini di Pauli.

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>Input

### <a name="coeff--double"></a>Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di coefficienti, come letto dalla struttura di dati Jordan-Wigner hamiltoniana.


### <a name="termtype--int"></a>termType: [int](xref:microsoft.quantum.lang-ref.int)

Tipo del termine del Jordan-Wigner.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrici di coefficienti espanse, una per ogni termine di Pauli.