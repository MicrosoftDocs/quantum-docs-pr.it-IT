---
uid: Microsoft.Quantum.Synthesis.Extended
title: Funzione estesa
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855481"
---
# <a name="extended-function"></a>Funzione estesa

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Estende uno spettro con coefficienti invertiti

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>Input

### <a name="spectrum--int"></a>Spectrum: [int](xref:microsoft.quantum.lang-ref.int)[]

Coefficienti spettrali



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Coefficienti seguiti da copia invertita

## <a name="example"></a>Esempio

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```