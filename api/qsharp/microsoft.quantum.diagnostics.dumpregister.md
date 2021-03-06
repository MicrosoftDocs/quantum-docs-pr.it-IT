---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829222"
---
# <a name="dumpregister-function"></a>DumpRegister (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Scarica lo stato del computer di destinazione corrente associato al qubits specificato.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="location--t"></a>Località:' t

Fornisce informazioni sulla posizione in cui generare il dump dello stato.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Elenco di qubits da segnalare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

Nessuna.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Questo metodo consente di eseguire il dump delle informazioni associate allo stato del qubits specificato in un file o in un altro percorso.
Le informazioni effettive generate e la semantica di `location` sono specifiche per ogni computer di destinazione. Tuttavia, se si specifica una tupla vuota come posizione ( `()` ), in genere viene generato l'output nella console.

Per il simulatore di stato completo locale distribuito come parte del quantum Development Kit, questo metodo prevede una stringa con il percorso di un file in cui scriverà lo stato del qubits specificato (ovvero la funzione Wave del sottosistema corrispondente) come matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta le ampiezze della probabilità di misurazione dello stato corrispondente.
Se i qubits specificati sono associati ad altri qubit e il relativo stato non può essere separato, viene semplicemente segnalato che i qubits sono aggrovigliati.