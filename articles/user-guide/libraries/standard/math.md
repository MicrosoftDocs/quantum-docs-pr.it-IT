---
title: 'Matematica nelle :::no-loc(Q#)::: librerie standard'
description: 'Informazioni sulle funzioni matematiche classiche nelle :::no-loc(Q#)::: librerie standard usate con i tipi di dati incorporati.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692062"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="9e158-103">Funzioni matematiche classiche</span><span class="sxs-lookup"><span data-stu-id="9e158-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="9e158-104">Queste funzioni vengono utilizzate principalmente per lavorare con i :::no-loc(Q#)::: tipi di dati incorporati `Int` , `Double` e `Range` .</span><span class="sxs-lookup"><span data-stu-id="9e158-104">These functions are primarily used to work with the :::no-loc(Q#)::: built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="9e158-105">L' <xref:Microsoft.Quantum.Intrinsic.Random> operazione è firmata `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="9e158-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="9e158-106">Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int` .</span><span class="sxs-lookup"><span data-stu-id="9e158-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="9e158-107">La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice.</span><span class="sxs-lookup"><span data-stu-id="9e158-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="9e158-108">n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.</span><span class="sxs-lookup"><span data-stu-id="9e158-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="9e158-109">Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="9e158-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
