---
title: "Úprava XML stromů (technologie LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 8ec47e6d-2363-4694-be46-8d5ca4d15fc9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8cf3ffabeb7c3caa5f0e3e38fb6f69551ce791b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-xml-trees-linq-to-xml-c"></a><span data-ttu-id="5432b-102">Úprava XML stromů (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5432b-102">Modifying XML Trees (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="5432b-103">je úložiště v paměti pro strom XML.</span><span class="sxs-lookup"><span data-stu-id="5432b-103"> is an in-memory store for an XML tree.</span></span> <span data-ttu-id="5432b-104">Po načíst a analyzovat strom XML ze zdroje, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] umožňuje měnit stromové struktuře na místě a pak serializovat stromu, případně ho uložit do souboru nebo odeslání na vzdálený server.</span><span class="sxs-lookup"><span data-stu-id="5432b-104">After you load or parse an XML tree from a source, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lets you modify that tree in place, and then serialize the tree, perhaps saving it to a file or sending it to a remote server.</span></span>  
  
 <span data-ttu-id="5432b-105">Při úpravě stromu v místě, použijete některé metody, jako například <xref:System.Xml.Linq.XContainer.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="5432b-105">When you modify a tree in place, you use certain methods, such as <xref:System.Xml.Linq.XContainer.Add%2A>.</span></span>  
  
 <span data-ttu-id="5432b-106">Je však jiný přístup, kde je použít funkční konstrukce vygenerovat novou větev s jinou obrazce.</span><span class="sxs-lookup"><span data-stu-id="5432b-106">However, there is another approach, which is to use functional construction to generate a new tree with a different shape.</span></span> <span data-ttu-id="5432b-107">V závislosti na typech změn, které musíte udělat na vaše strom XML a v závislosti na velikosti stromu tento přístup může být robustnější a usnadňují vývoj.</span><span class="sxs-lookup"><span data-stu-id="5432b-107">Depending on the types of changes that you need to make to your XML tree, and depending on the size of the tree, this approach can be more robust and easier to develop.</span></span> <span data-ttu-id="5432b-108">První téma v této části porovnání těchto dvou přístupů.</span><span class="sxs-lookup"><span data-stu-id="5432b-108">The first topic in this section compares these two approaches.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5432b-109">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="5432b-109">In This Section</span></span>  
  
|<span data-ttu-id="5432b-110">Téma</span><span class="sxs-lookup"><span data-stu-id="5432b-110">Topic</span></span>|<span data-ttu-id="5432b-111">Popis</span><span class="sxs-lookup"><span data-stu-id="5432b-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5432b-112">Změna stromové struktury v paměti XML vs. Funkční konstrukce (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5432b-112">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)|<span data-ttu-id="5432b-113">Porovná úprava strom XML v paměti, aby funkční konstrukce.</span><span class="sxs-lookup"><span data-stu-id="5432b-113">Compares modifying an XML tree in memory to functional construction.</span></span>|  
|[<span data-ttu-id="5432b-114">Přidání prvky, atributy a uzly na strom XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5432b-114">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|<span data-ttu-id="5432b-115">Poskytuje informace o přidání prvky, atributy a uzly na strom XML.</span><span class="sxs-lookup"><span data-stu-id="5432b-115">Provides information about adding elements, attributes, or nodes to an XML tree.</span></span>|  
|[<span data-ttu-id="5432b-116">Úprava prvky, atributy a uzly ve stromu XML</span><span class="sxs-lookup"><span data-stu-id="5432b-116">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|<span data-ttu-id="5432b-117">Poskytuje informace o úpravě existující prvky, atributy a uzly.</span><span class="sxs-lookup"><span data-stu-id="5432b-117">Provides information about modifying existing elements, attributes, or nodes.</span></span>|  
|[<span data-ttu-id="5432b-118">Odebrání prvky, atributy a uzly ze stromu XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5432b-118">Removing Elements, Attributes, and Nodes from an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|<span data-ttu-id="5432b-119">Poskytuje informace o odebrání prvky, atributy a uzly ve stromové struktuře XML.</span><span class="sxs-lookup"><span data-stu-id="5432b-119">Provides information about removing elements, attributes, or nodes from the XML tree.</span></span>|  
|[<span data-ttu-id="5432b-120">Zachování dvojice název hodnota (C#)</span><span class="sxs-lookup"><span data-stu-id="5432b-120">Maintaining Name/Value Pairs (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|<span data-ttu-id="5432b-121">Popisuje, jak udržovat informace o aplikaci, která je lepší je ponechat jako dvojice název/hodnota, například informace o konfiguraci nebo globální nastavení.</span><span class="sxs-lookup"><span data-stu-id="5432b-121">Describes how to maintain application information that is best kept as name/value pairs, such as configuration information or global settings.</span></span>|  
|[<span data-ttu-id="5432b-122">Postupy: Změna Namespace pro strom celý XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5432b-122">How to: Change the Namespace for an Entire XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|<span data-ttu-id="5432b-123">Ukazuje, jak přesunout strom XML z jednoho oboru názvů do jiné.</span><span class="sxs-lookup"><span data-stu-id="5432b-123">Shows how to move an XML tree from one namespace into another.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5432b-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="5432b-124">See Also</span></span>  
 [<span data-ttu-id="5432b-125">Průvodce programováním (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5432b-125">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)