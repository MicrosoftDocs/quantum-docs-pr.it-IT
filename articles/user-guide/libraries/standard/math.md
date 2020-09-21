---
title: Matematica nelle Q# librerie standard
description: Informazioni sulle funzioni matematiche classiche nelle Q# librerie standard usate con i tipi di dati incorporati.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833607"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="696a5-103">Funzioni matematiche classiche</span><span class="sxs-lookup"><span data-stu-id="696a5-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="696a5-104">Queste funzioni vengono utilizzate principalmente per lavorare con i Q# tipi di dati incorporati `Int` , `Double` e `Range` .</span><span class="sxs-lookup"><span data-stu-id="696a5-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="696a5-105">L' <xref:microsoft.quantum.intrinsic.random> operazione è firmata `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="696a5-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="696a5-106">Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int` .</span><span class="sxs-lookup"><span data-stu-id="696a5-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="696a5-107">La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice.</span><span class="sxs-lookup"><span data-stu-id="696a5-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="696a5-108">n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.</span><span class="sxs-lookup"><span data-stu-id="696a5-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="696a5-109">Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="696a5-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
