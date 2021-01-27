---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841071"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

