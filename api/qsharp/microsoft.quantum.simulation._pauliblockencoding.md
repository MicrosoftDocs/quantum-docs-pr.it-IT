---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: Funzione _PauliBlockEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 6ad3e692f68ec2d405e19a7e467ef8fe33d449fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225568"
---
# <a name="_pauliblockencoding-function"></a>Funzione _PauliBlockEncoding

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea un Unity di codifica a blocchi per un'Hamiltoniana.

Hamiltoniana $H = \ sum_ {j} \ alpha_j P_j $ è descritto da una somma dei termini di Pauli $P _j $, ognuno con un coefficiente reale $ \ alpha_j $.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Input

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Oggetto `GeneratorSystem` che descrive $H $ come somma dei termini di Pauli


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a>statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL

Un'operazione unitaria $V $ che applica il $V unitario _j $ controllato sull'indice $ \ket{j} $, data una funzione $f: j\rightarrow V_j $.


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a>multiplexer: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unit](xref:microsoft.quantum.lang-ref.unit)  is ADJ + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unit](xref:microsoft.quantum.lang-ref.unit)  Is ADJ + CTL





## <a name="output--doubleblockencodingreflection"></a>Output: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Primo parametro

La regola uno dei coefficienti $ \Alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Secondo parametro

`BlockEncodingReflection`Unitario $U $ dell'hamiltoniana $U $. Poiché questo unitario soddisfa $U ^ 2 = I $, è anche una reflection.

## <a name="remarks"></a>Commenti

Operazioni di esempio: preparare e annullare la preparazione dello stato $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ e costruire un Unity controllato da Multiply sono <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .