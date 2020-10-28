---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712872"
---
# <a name="dumpmachine-function"></a>DumpMachine (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Scarica lo stato del computer di destinazione corrente.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Input

### <a name="location--t"></a>Località:' t

Fornisce informazioni sulla posizione in cui generare il dump del computer.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

Nessuno.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Questo metodo consente di eseguire il dump delle informazioni sullo stato corrente del computer di destinazione in un file o in un altro percorso.
Le informazioni effettive generate e la semantica di `location` sono specifiche per ogni computer di destinazione. Tuttavia, se si specifica una tupla vuota come posizione ( `()` ) o semplicemente si omette il parametro, in `location` genere significa generare l'output nella console.

Per il simulatore di stato completo locale distribuito come parte del quantum Development Kit, questo metodo prevede una stringa con il percorso di un file in cui verrà scritta la funzione Wave come matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta le ampiezze della probabilità di misurazione dello stato corrispondente.