---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: b6f3fe0ececc58d86b916841c513377fbcb59054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716330"
---
# <a name="decomposeintotimestepsca-function"></a>DecomposeIntoTimeStepsCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


> [!WARNING]
> DecomposeIntoTimeStepsCA è stato deprecato. Usare invece <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA>.



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--intdoublet--unit-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),' t) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL




### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--doublet--unit-adj--ctl"></a>Output: ([Double](xref:microsoft.quantum.lang-ref.double),' t'=> [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

