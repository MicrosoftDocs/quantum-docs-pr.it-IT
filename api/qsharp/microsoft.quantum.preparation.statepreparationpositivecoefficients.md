---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722897"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Restituisce un'operazione che prepara lo stato del quantum specificato.

L'operazione restituita $U $ prepara uno stato quantico arbitrario $ \ket{\psi} $ con coefficienti positivi $ \ alpha_j \ge $0 dallo stato di base di calcolo $n $-qubit $ \ket{0...0} $.

L'azione di U in un registro appena allocato viene fornita da $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di un massimo di $2 ^ n $ coefficienti $ \ alpha_j $. Il coefficiente $j $ TH indicizza lo stato del numero $ \ket{j} $ codificato in formato little-endian.



## <a name="output--littleendian--unit-adj--ctl"></a>Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => ADJ [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian + CTL

Operazione unitaria di preparazione dello stato $U $.

## <a name="remarks"></a>Commenti

I coefficienti di input negativi $ \ alpha_j < $0 verranno trattati come se fossero positivi con il valore $ | \ alpha_j | $. `coefficients` verrà riempito con gli elementi $ \ alpha_j = $0,0 se sono specificati meno di $2 ^ n $.