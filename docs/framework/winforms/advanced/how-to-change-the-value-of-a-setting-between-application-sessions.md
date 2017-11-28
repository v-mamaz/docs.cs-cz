---
title: "Postupy: Změna hodnoty nastavení mezi relacemi aplikace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2dff90e499ce421f372137903daf34c09c21d5c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="60474-102">Postupy: Změna hodnoty nastavení mezi relacemi aplikace</span><span class="sxs-lookup"><span data-stu-id="60474-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="60474-103">V některých případech můžete chtít změnit hodnoty nastavení mezi relacemi aplikace po aplikaci byl zkompilován a nasazení.</span><span class="sxs-lookup"><span data-stu-id="60474-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="60474-104">Můžete například změnit připojovací řetězec tak, aby odkazovaly na správné databázi umístění.</span><span class="sxs-lookup"><span data-stu-id="60474-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="60474-105">Vzhledem k tomu, že nástrojů návrhu nejsou k dispozici po aplikaci byl zkompilován a nasazení, je nutné změnit hodnotu nastavení ručně v souboru.</span><span class="sxs-lookup"><span data-stu-id="60474-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="60474-106">Chcete-li změnit hodnoty nastavení mezi relacemi aplikace</span><span class="sxs-lookup"><span data-stu-id="60474-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="60474-107">Pomocí Microsoft Notepad nebo některé další text nebo editoru XML, otevřete soubor .config související s vaší aplikací.</span><span class="sxs-lookup"><span data-stu-id="60474-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="60474-108">Vyhledejte položku s nastavením, které chcete změnit.</span><span class="sxs-lookup"><span data-stu-id="60474-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="60474-109">By měla vypadat podobně jako v příkladu níže uvedené.</span><span class="sxs-lookup"><span data-stu-id="60474-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="60474-110">Zadejte novou hodnotu pro vaše nastavení a uložte soubor.</span><span class="sxs-lookup"><span data-stu-id="60474-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60474-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="60474-111">See Also</span></span>  
 [<span data-ttu-id="60474-112">Použití nastavení aplikace a nastavení uživatele</span><span class="sxs-lookup"><span data-stu-id="60474-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="60474-113">Přehled nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="60474-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)