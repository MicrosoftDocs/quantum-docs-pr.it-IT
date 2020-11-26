---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: Operazione AssertOperationsEqualReferenced
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualReferenced has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: e6c5d4b0005cc0cf1fb62a52b4a75a0370dfa293
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212512"
---
# <a name="assertoperationsequalreferenced-operation"></a>Operazione AssertOperationsEqualReferenced

Spazio dei nomi: [Microsoft. Quantum. Extensions. testing](xref:Microsoft.Quantum.Extensions.Testing)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


> [!WARNING]
> AssertOperationsEqualReferenced è stato deprecato. Usare invece <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced>.
>
> Usare @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".
> Si noti che l'ordine degli argomenti di questa operazione è stato modificato.



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a>Input

### <a name="actual--qubit--unit"></a>effettivo: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="expected--qubit--unit--is-adj"></a>previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ




### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

