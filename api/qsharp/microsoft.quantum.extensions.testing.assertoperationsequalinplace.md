---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: Operazione AssertOperationsEqualInPlace
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: 64cc1e5c78af100b652ced24f00f3097c35ea5d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820230"
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

