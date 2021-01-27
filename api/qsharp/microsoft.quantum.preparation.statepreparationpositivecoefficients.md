---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855851"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationPositiveCoefficients è stato deprecato. Usare invece <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>.

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



## <a name="output--littleendian--unit--is-adj--ctl"></a>Output: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL

Operazione unitaria di preparazione dello stato $U $.

## <a name="example"></a>Esempio

Il frammento di codice seguente prepara lo stato quantico $ \ket{\psi} = \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {2} $ nel registro qubit `qubitsLE` .

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a>Commenti

I coefficienti di input negativi $ \ alpha_j < $0 verranno trattati come se fossero positivi con il valore $ | \ alpha_j | $. `coefficients` verrà riempito con gli elementi $ \ alpha_j = $0,0 se sono specificati meno di $2 ^ n $.