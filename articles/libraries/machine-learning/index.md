---
title: Introduzione al pacchetto di apprendimento automatico quantistico | Microsoft Docs
description: Introduzione al pacchetto di apprendimento automatico quantistico
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907852"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="04ef0-103">Introduzione alla libreria di apprendimento automatico quantistico</span><span class="sxs-lookup"><span data-stu-id="04ef0-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="04ef0-104">La libreria di apprendimento automatico quantistico è un'API, scritta in Q#, che consente di eseguire esperimenti di apprendimento automatico ibrido quantistico/classico.</span><span class="sxs-lookup"><span data-stu-id="04ef0-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="04ef0-105">Con la libreria è possibile:</span><span class="sxs-lookup"><span data-stu-id="04ef0-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="04ef0-106">Caricare dati personalizzati per la classificazione con simulatori quantistici</span><span class="sxs-lookup"><span data-stu-id="04ef0-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="04ef0-107">Usare esempi ed esercitazioni per avvicinarsi al campo dell'apprendimento automatico quantistico</span><span class="sxs-lookup"><span data-stu-id="04ef0-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="04ef0-108">Le prestazioni previste sono decisamente inferiori rispetto a quelle degli attuali framework di apprendimento automatico classico. Tenere presente infatti che gli esperimenti vengono eseguiti sulla simulazione di un dispositivo quantistico che è già di per sé oneroso dal punto di vista del calcolo.</span><span class="sxs-lookup"><span data-stu-id="04ef0-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="04ef0-109">Lo scopo di questa documentazione è:</span><span class="sxs-lookup"><span data-stu-id="04ef0-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="04ef0-110">Offrire una breve introduzione agli strumenti di apprendimento automatico (scritti in Q\#) per l'apprendimento ibrido quantistico/classico.</span><span class="sxs-lookup"><span data-stu-id="04ef0-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="04ef0-111">Introdurre i concetti di apprendimento automatico e, in particolare, la loro realizzazione in classificatori incentrati sul circuito quantistico (noti anche come classificatori sequenziali quantistici).</span><span class="sxs-lookup"><span data-stu-id="04ef0-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="04ef0-112">Fornire un set di esercitazioni sulle nozioni di base per iniziare a usare gli strumenti forniti dalla libreria.</span><span class="sxs-lookup"><span data-stu-id="04ef0-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="04ef0-113">Illustrare i metodi di training e convalida per questi classificatori e spiegare in che modo vengono convertiti in specifiche operazioni Q\# fornite dalla libreria.</span><span class="sxs-lookup"><span data-stu-id="04ef0-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="04ef0-114">Il modello implementato in questa libreria è basato sullo schema di training classico quantistico illustrato nel documento [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633).</span><span class="sxs-lookup"><span data-stu-id="04ef0-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>