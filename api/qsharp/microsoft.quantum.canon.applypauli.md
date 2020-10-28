---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Operazione ApplyPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717814"
---
# <a name="applypauli-operation"></a>Operazione ApplyPauli

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Dato un operatore Pauli multiqubit, applica l'operazione corrispondente a un registro.

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Operatore Pauli multiqubit rappresentato come una matrice di operatori Pauli a qubit singolo.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Eseguire la registrazione per applicare l'operazione di Pauli specificata in.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

