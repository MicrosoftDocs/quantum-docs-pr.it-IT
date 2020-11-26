---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: Operazione AssertOperationsEqualInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 0f22bcbf74a33b1501acf9222d6dc6327b16bbbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212546"
---
# <a name="assertoperationsequalinplace-operation"></a>Operazione AssertOperationsEqualInPlace

Spazio dei nomi: [Microsoft. Quantum. Extensions. testing](xref:Microsoft.Quantum.Extensions.Testing)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


> [!WARNING]
> AssertOperationsEqualInPlace è stato deprecato. Usare invece <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace>.
>
> Usare @"microsoft.quantum.diagnostics.assertoperationsequalinplace".
> Si noti che l'ordine degli argomenti di questa operazione è stato modificato.



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a>Input

### <a name="actual--qubit--unit"></a>effettivo: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="expected--qubit--unit--is-adj"></a>previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ




### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

