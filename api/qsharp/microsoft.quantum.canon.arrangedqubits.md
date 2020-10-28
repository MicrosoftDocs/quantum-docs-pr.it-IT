---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716747"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Disporre qubits di controllo, di destinazione e di supporto in base a un indice

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Descrizione

Restituisce una matrice qubit con la destinazione in corrispondenza dell'indice 0 e il controllo i in corrispondenza dell'indice 2 ^ i.  Il qubits Helper viene inserito in tutte le altre posizioni nella matrice.

## <a name="input"></a>Input

### <a name="controls--qubit"></a>Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>Helper: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

