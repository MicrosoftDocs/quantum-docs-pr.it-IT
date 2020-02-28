---
title: 'Math nelle librerie standard Q #'
description: 'Informazioni sulle funzioni matematiche classiche nelle librerie standard Q # usate con i tipi di dati incorporati.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906152"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="7f56a-103">Funzioni matematiche classiche</span><span class="sxs-lookup"><span data-stu-id="7f56a-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="7f56a-104">Queste funzioni vengono utilizzate principalmente per lavorare con i tipi di dati predefiniti Q # `Int`, `Double`e `Range`.</span><span class="sxs-lookup"><span data-stu-id="7f56a-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="7f56a-105">L'operazione <xref:microsoft.quantum.intrinsic.random> ha `(Double[] => Int)`di firma.</span><span class="sxs-lookup"><span data-stu-id="7f56a-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="7f56a-106">Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int`.</span><span class="sxs-lookup"><span data-stu-id="7f56a-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="7f56a-107">La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice.</span><span class="sxs-lookup"><span data-stu-id="7f56a-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="7f56a-108">n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.</span><span class="sxs-lookup"><span data-stu-id="7f56a-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="7f56a-109">Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="7f56a-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
