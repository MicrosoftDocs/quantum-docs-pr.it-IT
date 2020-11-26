---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210370"
---
# <a name="statepreparationcomplexcoefficients-function"></a>StatePreparationComplexCoefficients (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationComplexCoefficients è stato deprecato. Usare invece <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>.

Restituisce un'operazione che prepara uno stato quantico specifico.

L'operazione restituita $U $ prepara uno stato quantico arbitrario $ \ket{\psi} $ con coefficienti complessi $r _j e ^ {i t_j} $ dallo stato di base di calcolo $n $-qubit $ \ket{0...0} $.

L'azione di U in un registro appena allocato viene fornita da $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="coefficients--complexpolar"></a>coefficienti: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Matrice di un massimo di $2 ^ n $ coefficienti complessi, rappresentati dal valore assoluto e dalla fase $ (r_j, t_j) $. Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL

Operazione unitaria di preparazione dello stato $U $.

## <a name="remarks"></a>Commenti

I coefficienti di input negativi $r _j < $0 verranno trattati come se fossero positivi con il valore $ | r_j | $. `coefficients` verrà riempito con gli elementi $ (r_j, t_j) = (0,0, 0,0) $ se sono specificati meno di $2 ^ n $.