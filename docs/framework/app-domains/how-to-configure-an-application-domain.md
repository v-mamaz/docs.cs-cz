---
title: "Postupy: Konfigurace domény aplikace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79a05be9b3ddb9ca8aaabe13165efc5d851125a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="50265-102">Postupy: Konfigurace domény aplikace</span><span class="sxs-lookup"><span data-stu-id="50265-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="50265-103">Modul common language runtime můžete poskytnout informace o konfiguraci pro novou doménu aplikace pomocí <xref:System.AppDomainSetup> třídy.</span><span class="sxs-lookup"><span data-stu-id="50265-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="50265-104">Při vytváření vlastní domény aplikace, je nejdůležitější vlastnost <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="50265-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="50265-105">Druhá **AppDomainSetup** vlastnosti jsou používány především modulu runtime pro konfiguraci určité domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="50265-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="50265-106">**ApplicationBase** vlastnost definuje kořenový adresář aplikace.</span><span class="sxs-lookup"><span data-stu-id="50265-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="50265-107">Když modul runtime potřebuje vyhovovaly žádosti o typ, sondy pro sestavení obsahující typ v adresáři určeného **ApplicationBase** vlastnost.</span><span class="sxs-lookup"><span data-stu-id="50265-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50265-108">Nová doména aplikace dědí pouze **ApplicationBase** vlastnosti Tvůrce.</span><span class="sxs-lookup"><span data-stu-id="50265-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="50265-109">Následující příklad vytvoří instanci **AppDomainSetup** třída, používá tuto třídu k vytvoření nové domény aplikace, zapíše informace do konzoly a poté uvolní doménu aplikace.</span><span class="sxs-lookup"><span data-stu-id="50265-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50265-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="50265-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="50265-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="50265-111">See Also</span></span>  
 [<span data-ttu-id="50265-112">Programování s doménami aplikací</span><span class="sxs-lookup"><span data-stu-id="50265-112">Programming with Application Domains</span></span>](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="50265-113">Používání domén aplikací</span><span class="sxs-lookup"><span data-stu-id="50265-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)