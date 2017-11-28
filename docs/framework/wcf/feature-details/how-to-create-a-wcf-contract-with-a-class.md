---
title: "Postupy: Vytvoření kontraktu Windows Communication Foundation s třídou"
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
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bf32559f9b5a1040390562cc8492646288494638
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="e211c-102">Postupy: Vytvoření kontraktu Windows Communication Foundation s třídou</span><span class="sxs-lookup"><span data-stu-id="e211c-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="e211c-103">Upřednostňovaný způsob vytváření [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kontrakt je pomocí rozhraní.</span><span class="sxs-lookup"><span data-stu-id="e211c-103">The preferred way of creating a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="e211c-104">[Postupy: definování kontraktu služby](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="e211c-104"> [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="e211c-105">Alternativní, popsané tady, je vytvoření třídy a následně použít <xref:System.ServiceModel.ServiceContractAttribute> atribut třídy přímo a <xref:System.ServiceModel.OperationContractAttribute> atribut každá z metod ve třídě, které jsou součástí smlouvy.</span><span class="sxs-lookup"><span data-stu-id="e211c-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e211c-106">`[ServiceContract]`a `[ServiceContractAttribute]` stejnou věc udělat.</span><span class="sxs-lookup"><span data-stu-id="e211c-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="e211c-107">Samé ho true pro `[OperationContract]` a `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="e211c-107">The same thing it true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="e211c-108">V každém případě je sdružená vlastnost pro tento první.</span><span class="sxs-lookup"><span data-stu-id="e211c-108">In each case the former is shorthand for the latter.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e211c-109">kontrakty najdete v tématu [navrhování kontraktů služby](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="e211c-109"> service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="e211c-110">Vytvoření kontraktu Windows Communication Foundation s třídou</span><span class="sxs-lookup"><span data-stu-id="e211c-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="e211c-111">Vytvoření nové třídy pomocí [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C# nebo jakéhokoli jiného common language runtime jazyka.</span><span class="sxs-lookup"><span data-stu-id="e211c-111">Create a new class using [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="e211c-112">Použít <xref:System.ServiceModel.ServiceContractAttribute> třída pro třídu.</span><span class="sxs-lookup"><span data-stu-id="e211c-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="e211c-113">Vytvoření metody ve třídě.</span><span class="sxs-lookup"><span data-stu-id="e211c-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="e211c-114">Použít <xref:System.ServiceModel.OperationContractAttribute> třída pro každou metodu, který musí být zveřejněný v rámci veřejnosti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kontrakt.</span><span class="sxs-lookup"><span data-stu-id="e211c-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e211c-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="e211c-115">Example</span></span>  
 <span data-ttu-id="e211c-116">Následující příklad kódu ukazuje třídu, která definuje kontrakt služby.</span><span class="sxs-lookup"><span data-stu-id="e211c-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="e211c-117">Metody, které mají <xref:System.ServiceModel.OperationContractAttribute> třída použije ve výchozím nastavení používá vzor zprávu požadavku a odpovědi.</span><span class="sxs-lookup"><span data-stu-id="e211c-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e211c-118">Tento vzor zpráv najdete v části [postupy: vytvoření kontraktu požadavku a odpovědi](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="e211c-118"> this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="e211c-119">Můžete také vytvořit a použít dalších zpráv vzorech nastavením vlastnosti atributu.</span><span class="sxs-lookup"><span data-stu-id="e211c-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="e211c-120">Další příklady najdete v tématu [postupy: vytvoření kontraktu One-Way](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) a [postupy: vytvoření duplexního kontraktu](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="e211c-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e211c-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="e211c-121">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>