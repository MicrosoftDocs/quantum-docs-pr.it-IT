---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operazione ApplyTransposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725263"
---
# <a name="applytransposition-operation"></a>Operazione ApplyTransposition

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto [](https://nuget.org/packages/)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrizione

Questa operazione scambia l'ampiezza in corrispondenza dell'indice `a` con l'ampiezza in corrispondenza dell'indice `b` nel vettore di stato specificato di `register` lunghezza $n $.  Se `a` è uguale `b` a, il vettore di stato non viene modificato.

## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Primo indice (deve essere un valore compreso tra 0 e $2 ^ n-$1)


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Secondo indice (deve essere un valore compreso tra 0 e $2 ^ n-$1)


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Elenco di $n $ qubits a cui viene applicata la trasposizione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

