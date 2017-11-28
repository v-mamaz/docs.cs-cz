---
title: "Čtení z registru a zápis do něj pomocí oboru názvů My (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: db564b428d585829b220674271f4636bfcc68562
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a><span data-ttu-id="bb410-102">Čtení z registru a zápis do něj pomocí oboru názvů My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb410-102">Reading from and Writing to the Registry (Visual Basic)</span></span>
<span data-ttu-id="bb410-103">Toto téma popisuje úlohy a koncepční témata, které jsou přidruženy registru.</span><span class="sxs-lookup"><span data-stu-id="bb410-103">This topic describes task and conceptual topics that are associated with the registry.</span></span>  
  
 <span data-ttu-id="bb410-104">Při programování v [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], můžete získat přístup k registru formou funkce poskytované [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] nebo registru tříd rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb410-104">When programming in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], you can choose to access the registry by means of either the functions provided by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] or the registry classes of the .NET Framework.</span></span> <span data-ttu-id="bb410-105">Registru hostuje informace z operačního systému a informace z aplikace hostované na počítači.</span><span class="sxs-lookup"><span data-stu-id="bb410-105">The registry hosts information from the operating system as well as information from applications hosted on the machine.</span></span> <span data-ttu-id="bb410-106">Práce s registrem může ohrozit zabezpečení tím, že nevhodný přístup k systémovým prostředkům nebo chráněný informace.</span><span class="sxs-lookup"><span data-stu-id="bb410-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb410-107">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="bb410-107">In This Section</span></span>  
 [<span data-ttu-id="bb410-108">Postupy: vytvoření klíče registru a nastavení jeho hodnoty</span><span class="sxs-lookup"><span data-stu-id="bb410-108">How to: Create a Registry Key and Set Its Value</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 <span data-ttu-id="bb410-109">Popisuje postup použití `CreateSubKey` a `SetValue` metody `My.Computer.Registry` objekt k vytvoření klíče registru a nastavení jeho hodnoty.</span><span class="sxs-lookup"><span data-stu-id="bb410-109">Describes how to use the `CreateSubKey` and `SetValue` methods of the `My.Computer.Registry` object to create a registry key and set its value.</span></span>  
  
 [<span data-ttu-id="bb410-110">Postupy: načtení hodnoty z klíče registru</span><span class="sxs-lookup"><span data-stu-id="bb410-110">How to: Read a Value from a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 <span data-ttu-id="bb410-111">Popisuje postup použití `GetValue` metodu `My.Computer.Registry` objekt k načtení hodnoty z klíče registru.</span><span class="sxs-lookup"><span data-stu-id="bb410-111">Describes how to use the `GetValue` method of the `My.Computer.Registry` object to read a value from a registry key.</span></span>  
  
 [<span data-ttu-id="bb410-112">Postupy: odstranění klíče z registru</span><span class="sxs-lookup"><span data-stu-id="bb410-112">How to: Delete a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 <span data-ttu-id="bb410-113">Popisuje postup použití `DeleteSubKey` metodu `My.Computer.Registry.CurrentUser` vlastnost odstranit klíč registru.</span><span class="sxs-lookup"><span data-stu-id="bb410-113">Describes how to use the `DeleteSubKey` method of the `My.Computer.Registry.CurrentUser` property to delete a registry key.</span></span>  
  
 [<span data-ttu-id="bb410-114">Čtení a zápis do registru pomocí Namespace Microsoft.Win32</span><span class="sxs-lookup"><span data-stu-id="bb410-114">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 <span data-ttu-id="bb410-115">Popisuje postup použití `Registry` a `RegistryKey` třídy [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pro přístup k registru.</span><span class="sxs-lookup"><span data-stu-id="bb410-115">Describes how to use the `Registry` and `RegistryKey` classes of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to access the registry.</span></span>  
  
 [<span data-ttu-id="bb410-116">Zabezpečení a registr</span><span class="sxs-lookup"><span data-stu-id="bb410-116">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 <span data-ttu-id="bb410-117">Popisuje problémy se zabezpečením zahrnující registru.</span><span class="sxs-lookup"><span data-stu-id="bb410-117">Discusses security issues involving the registry.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bb410-118">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="bb410-118">Related Sections</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <span data-ttu-id="bb410-119">Uvádí a vysvětluje členy `My.Computer.Registry` objektu.</span><span class="sxs-lookup"><span data-stu-id="bb410-119">Lists and explains members of the `My.Computer.Registry` object.</span></span>  
  
 <xref:Microsoft.Win32.Registry>  
 <span data-ttu-id="bb410-120">Obsahuje přehled nástroje `Registry` třída, spolu s odkazy na jednotlivé klíče a členy.</span><span class="sxs-lookup"><span data-stu-id="bb410-120">Presents an overview of the `Registry` class, along with links to individual keys and members.</span></span>