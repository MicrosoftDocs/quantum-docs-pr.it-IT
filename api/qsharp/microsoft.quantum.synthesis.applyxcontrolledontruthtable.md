---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Operazione ApplyXControlledOnTruthTable
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 6e956038f7cd15db7348ff830da8bc9eae53aa61
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855550"
---
# <a name="applyxcontrolledontruthtable-operation"></a>Operazione ApplyXControlledOnTruthTable

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica l' @"microsoft.quantum.intrinsic.x" operazione su `target` , se la funzione booleana `func` restituisce true per l'assegnazione classica in `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

L'operazione implementa l'operazione unitaria \begin{align} U\ket {x} \ KET {y} = \ket{x}\ket{y \oplus f (x)} \end{align} in cui $x $ e $y $ `controlRegister` rappresentano `target` rispettivamente e.

La funzione booleana $f $ viene rappresentata come una tabella di verità in termini di un valore Integer grande.
La funzione di maggioranza su tre input, ad esempio, è rappresentata da Bitstring `11101000` , dove il bit più significativo `1` corrisponde all'assegnazione di input `(1, 1, 1)` e il bit meno significativo `0` corrisponde all'assegnazione di input `(0, 0, 0)` .
Può essere rappresentata da un Big Integer `0xE8L` in notazione esadecimale o come `232L` notazione decimale.  Il `L` suffisso indica che la costante è di tipo `BigInt` .
Altre informazioni su questa rappresentazione sono disponibili anche nella pagina relativa alla [verità Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).

L'implementazione utilizza le attività di controllo @"microsoft.quantum.intrinsic.cnot" e @"microsoft.quantum.intrinsic.r1" .

## <a name="input"></a>Input

### <a name="func--bigint"></a>Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Tabella di verità booleana rappresentata come valore Big Integer


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro dei qubits di controllo


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit di destinazione



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

- [*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv: quanti-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken*, *Martin Roetteler*, arXiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)