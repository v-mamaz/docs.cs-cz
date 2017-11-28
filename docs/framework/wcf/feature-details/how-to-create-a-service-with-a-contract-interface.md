---
title: "Postupy: Vytvoření služby pomocí rozhraní kontraktu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b00a7cbbab343eb209895affbbbba76ef2af2959
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="7e633-102">Postupy: Vytvoření služby pomocí rozhraní kontraktu</span><span class="sxs-lookup"><span data-stu-id="7e633-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="7e633-103">Upřednostňovaný způsob, jak vytvořit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kontrakt je pomocí rozhraní.</span><span class="sxs-lookup"><span data-stu-id="7e633-103">The preferred way to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="7e633-104">Tento kontrakt určuje kolekci a struktura zpráv, které jsou nutné pro přístup k činnosti nabídky služeb.</span><span class="sxs-lookup"><span data-stu-id="7e633-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="7e633-105">Toto rozhraní definuje vstupní a výstupní typy použitím <xref:System.ServiceModel.ServiceContractAttribute> třídy rozhraní a <xref:System.ServiceModel.OperationContractAttribute> třídy metody, které chcete vystavit.</span><span class="sxs-lookup"><span data-stu-id="7e633-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7e633-106">kontrakty najdete v tématu [navrhování kontraktů služby](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="7e633-106"> service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="7e633-107">Vytvoření kontraktu WCF pomocí rozhraní</span><span class="sxs-lookup"><span data-stu-id="7e633-107">Creating a WCF contract with an interface</span></span>  
  
1.  <span data-ttu-id="7e633-108">Vytvoření nové rozhraní pomocí [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C# nebo jakéhokoli jiného common language runtime jazyka.</span><span class="sxs-lookup"><span data-stu-id="7e633-108">Create a new interface using [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="7e633-109">Použít <xref:System.ServiceModel.ServiceContractAttribute> třídy rozhraní.</span><span class="sxs-lookup"><span data-stu-id="7e633-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3.  <span data-ttu-id="7e633-110">Definujte metody v rozhraní.</span><span class="sxs-lookup"><span data-stu-id="7e633-110">Define the methods in the interface.</span></span>  
  
4.  <span data-ttu-id="7e633-111">Použít <xref:System.ServiceModel.OperationContractAttribute> třída pro každou metodu, který musí být zveřejněný v rámci veřejnosti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kontrakt.</span><span class="sxs-lookup"><span data-stu-id="7e633-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e633-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="7e633-112">Example</span></span>  
 <span data-ttu-id="7e633-113">Následující příklad kódu ukazuje rozhraní, které definuje kontrakt služby.</span><span class="sxs-lookup"><span data-stu-id="7e633-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="7e633-114">Metody, které mají <xref:System.ServiceModel.OperationContractAttribute> třída použije ve výchozím nastavení používá vzor zprávu požadavku a odpovědi.</span><span class="sxs-lookup"><span data-stu-id="7e633-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7e633-115">Tento vzor zpráv najdete v části [postupy: vytvoření kontraktu požadavku a odpovědi](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="7e633-115"> this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="7e633-116">Můžete také vytvořit a použít dalších zpráv vzorech nastavením vlastnosti atributu.</span><span class="sxs-lookup"><span data-stu-id="7e633-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="7e633-117">Další příklady najdete v tématu [postupy: vytvoření kontraktu One-Way](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) a [postupy: vytvoření duplexního kontraktu](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="7e633-117">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e633-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="7e633-118">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>