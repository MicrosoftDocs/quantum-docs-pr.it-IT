---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 6614b78c8e64c205cc94052cc64dd957814ab3d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724076"
---
# <a name="blochspherecoordinates-function"></a>BlochSphereCoordinates (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Calcola le coordinate della sfera Bloch per un singolo stato di qubit.

Dati due numeri complessi $a 0, a1 $ che rappresentano lo stato qubit, calcola le coordinate sulla sfera Bloch in modo che $a 0 \ket {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i \Phi/2}\cos{(\ Theta/2)} \ket {0} + e ^ {i \Phi/2}\sin{(\ Theta/2)} \ket {1} ) $.

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a>Input

### <a name="a0--complexpolar"></a>a0: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Coefficiente complesso dello stato $ \ket {0} $.


### <a name="a1--complexpolar"></a>a1: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Coefficiente complesso dello stato $ \ket {1} $.



## <a name="output--complexpolardoubledouble"></a>Output: ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))

Tupla contenente `(ComplexPolar(r, t), phi, theta)` .