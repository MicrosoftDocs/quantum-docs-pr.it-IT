---
title: 'Variabili locali-tecniche Q # | Microsoft Docs'
description: 'Variabili locali-tecniche Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: 8b1de5c096210fb36a81c127a8bbbe1b39522741
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820182"
---
# <a name="local-variables"></a><span data-ttu-id="56d29-103">Variabili locali</span><span class="sxs-lookup"><span data-stu-id="56d29-103">Local Variables</span></span> #

<span data-ttu-id="56d29-104">Un valore di qualsiasi tipo in Q # può essere assegnato a una variabile per il riutilizzo all'interno di un'operazione o funzione tramite la parola chiave `let`.</span><span class="sxs-lookup"><span data-stu-id="56d29-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="56d29-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="56d29-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="56d29-106">Questa operazione assegna una matrice specifica di operatori Pauli a una variabile denominata `measurementOperator`.</span><span class="sxs-lookup"><span data-stu-id="56d29-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="56d29-107">Si noti che non è stato necessario specificare in modo esplicito il tipo della nuova variabile, poiché l'espressione a destra dell'istruzione `let` non è ambigua e il tipo viene dedotto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="56d29-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="56d29-108">Le variabili in Q # sono non *modificabili*, ovvero una volta che una variabile è stata definita in questo modo, non può più essere modificata in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="56d29-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="56d29-109">Ciò consente di eseguire diverse ottimizzazioni utili, inclusa l'ottimizzazione della logica classica che agisce sulle variabili da riordinare per l'applicazione del `Adjoint` variante di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="56d29-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="56d29-110">Le variabili definite tramite il binding `let` come sopra sono locali rispetto a un ambito specifico, ad esempio il corpo di un'operazione o il contenuto di un ciclo di `for`.</span><span class="sxs-lookup"><span data-stu-id="56d29-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="56d29-111">Modificabilità</span><span class="sxs-lookup"><span data-stu-id="56d29-111">Mutability</span></span> ##

<span data-ttu-id="56d29-112">In alternativa alla creazione di una variabile con `let`, la parola chiave `mutable` creerà una variabile speciale modificabile che può essere riassociata dopo che è stata creata inizialmente usando la parola chiave `set`.</span><span class="sxs-lookup"><span data-stu-id="56d29-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="56d29-113">Tutti i tipi in Q #, incluse le matrici, seguono la semantica del valore.</span><span class="sxs-lookup"><span data-stu-id="56d29-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="56d29-114">In particolare, non è possibile aggiornare gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="56d29-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="56d29-115">Per modificare una matrice esistente, è necessario utilizzare un meccanismo di copia e aggiornamento simile a quello per i record in F#.</span><span class="sxs-lookup"><span data-stu-id="56d29-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="56d29-116">Usando gli strumenti di libreria per le matrici fornite in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), è possibile, ad esempio, definire una funzione che restituisce una matrice di Paulis in cui Pauli in index `i` accetta il valore specificato e tutte le altre voci sono l'identità:</span><span class="sxs-lookup"><span data-stu-id="56d29-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="56d29-117">Verranno approfondite le procedure per l'utilizzo delle matrici quando si discutono le istruzioni e le espressioni Q #.</span><span class="sxs-lookup"><span data-stu-id="56d29-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="56d29-118">La mutevolezza in Q # è un concetto che si applica a un *simbolo* anziché a un tipo o a un valore.</span><span class="sxs-lookup"><span data-stu-id="56d29-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="56d29-119">In particolare, non dispone di una rappresentazione nel sistema di tipi, in modo implicito o esplicito e indipendentemente dal fatto che un'associazione sia modificabile (come indicato dalla parola chiave `mutable`) o immutabile (come indicato da `let`) non modifichi il tipo della variabile associata.</span><span class="sxs-lookup"><span data-stu-id="56d29-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="56d29-120">Questo fornisce un modo importante per isolare la mutabilità all'interno di funzioni e operazioni specializzate.</span><span class="sxs-lookup"><span data-stu-id="56d29-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="56d29-121">In particolare, anche se una specializzazione contigua per un'operazione che usa una variabile modificabile non può essere generata automaticamente, la generazione automatica funziona correttamente per un'operazione che chiama una funzione che usa la mutabilità.</span><span class="sxs-lookup"><span data-stu-id="56d29-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="56d29-122">Per questo motivo, è consigliabile rendere le funzioni e le operazioni che usano la mutabilità il più breve e compatto possibile, in modo che il resto del programma Quantum possa essere scritto usando variabili non modificabili ordinarie.</span><span class="sxs-lookup"><span data-stu-id="56d29-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="56d29-123">Decostruzione</span><span class="sxs-lookup"><span data-stu-id="56d29-123">Deconstruction</span></span> ##

<span data-ttu-id="56d29-124">Oltre ad assegnare una singola variabile, le parole chiave `let` e `mutable`, o in realtà qualsiasi altro costrutto di associazione, consentono anche di decomprimere il contenuto di un [tipo di tupla](xref:microsoft.quantum.language.type-model#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="56d29-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="56d29-125">Un'assegnazione di questo form è detta *decostruzione* degli elementi di tale tupla.</span><span class="sxs-lookup"><span data-stu-id="56d29-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="56d29-126">Ad esempio, se si modella un termine in un'Hamiltoniana da una tupla, è possibile usare la decostruzione per accedere ai diversi dati che è necessario simulare in questo periodo:</span><span class="sxs-lookup"><span data-stu-id="56d29-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


