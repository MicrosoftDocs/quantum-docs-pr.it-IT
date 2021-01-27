---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: Operazione ApplyAndChain
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842009"
---
# <a name="applyandchain-operation"></a>Operazione ApplyAndChain

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcola una catena di porte e

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a>Descrizione

Il qubits ausiliario per calcolare i risultati temporanei deve essere specificato in modo esplicito.
La lunghezza di tale registro è `Length(ctrlRegister) - 2` , se sono presenti almeno due controlli; in caso contrario, la lunghezza è 0.

## <a name="input"></a>Input

### <a name="auxregister--qubit"></a>auxRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="ctrlregister--qubit"></a>ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

