---
uid: Microsoft.Quantum.Intrinsic.T
title: Operazione T
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720855"
---
# <a name="t-operation"></a>Operazione T

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Applica il controllo T a un singolo qubit.

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Questa operazione può essere simulata dalla matrice di unità \begin{align} T \mathrel{: =} \begin{Bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \Pi/4} \end{Bmatrix}.
\end{align}

## <a name="input"></a>Input

### <a name="qubit--qubit"></a>Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit a cui deve essere applicato il controllo.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

