---
title: "Postupy: Vytvoření základního informačního kanálu Atom"
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
ms.assetid: 6e0cacc1-9b11-4665-adb7-577a62626fd6
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d395e286bb42cb8533f7a8d62a8fdd68fd2b9204
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-basic-atom-feed"></a><span data-ttu-id="a1c5c-102">Postupy: Vytvoření základního informačního kanálu Atom</span><span class="sxs-lookup"><span data-stu-id="a1c5c-102">How to: Create a Basic Atom Feed</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="a1c5c-103">Umožňuje vytvořit službu, která zveřejňuje syndikace informačního kanálu.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-103"> allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="a1c5c-104">Toto téma popisuje postup vytvoření syndikace služby, která zveřejňuje Atom syndikace informačního kanálu.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-104">This topic discusses how to create a syndication service that exposes an Atom syndication feed.</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="a1c5c-105">Vytvoření služby základní syndikace</span><span class="sxs-lookup"><span data-stu-id="a1c5c-105">To create a basic syndication service</span></span>  
  
1.  <span data-ttu-id="a1c5c-106">Definování kontraktu služby pomocí rozhraní označené jako <xref:System.ServiceModel.Web.WebGetAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-106">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="a1c5c-107">Každé operace, která je vystavená, protože by měla vrátit syndikace informační kanál <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> objektu.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-107">Each operation that is exposed as a syndication feed should return a <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> object.</span></span>  
  
     [!code-csharp[htAtomBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#0)]
     [!code-vb[htAtomBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="a1c5c-108">Všechny operace služby, které se vztahují <xref:System.ServiceModel.Web.WebGetAttribute> jsou namapované na požadavky HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-108">All service operations that apply the <xref:System.ServiceModel.Web.WebGetAttribute> are mapped to HTTP GET requests.</span></span> <span data-ttu-id="a1c5c-109">Pokud chcete mapovat tuto operaci na jinou metodu HTTP, používat <xref:System.ServiceModel.Web.WebInvokeAttribute> místo.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-109">To map your operation to a different HTTP method, use the <xref:System.ServiceModel.Web.WebInvokeAttribute> instead.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="a1c5c-110">[Postupy: vytvoření webové služby HTTP WCF základní](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span><span class="sxs-lookup"><span data-stu-id="a1c5c-110"> [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span></span>  
  
2.  <span data-ttu-id="a1c5c-111">Implementujte kontrakt služby.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-111">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#1)]
     [!code-vb[htAtomBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#1)]  
  
3.  <span data-ttu-id="a1c5c-112">Vytvoření <xref:System.ServiceModel.Syndication.SyndicationFeed> objektu a přidejte vytváření, kategorie a popis.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-112">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#2)]
     [!code-vb[htAtomBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#2)]  
  
4.  <span data-ttu-id="a1c5c-113">Vytvořit několik <xref:System.ServiceModel.Syndication.SyndicationItem> objekty.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-113">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#3)]
     [!code-vb[htAtomBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#3)]  
  
5.  <span data-ttu-id="a1c5c-114">Přidat <xref:System.ServiceModel.Syndication.SyndicationItem> objekty k informačnímu kanálu.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-114">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#4)]
     [!code-vb[htAtomBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#4)]  
  
6.  <span data-ttu-id="a1c5c-115">Vrátí informačního kanálu.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-115">Return the feed.</span></span>  
  
     [!code-csharp[htAtomBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#5)]
     [!code-vb[htAtomBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="a1c5c-116">K hostování služby</span><span class="sxs-lookup"><span data-stu-id="a1c5c-116">To host the service</span></span>  
  
1.  <span data-ttu-id="a1c5c-117">Vytvoření <xref:System.ServiceModel.Web.WebServiceHost> objektu.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-117">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htAtomBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#6)]
     [!code-vb[htAtomBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#6)]  
  
2.  <span data-ttu-id="a1c5c-118">Otevření hostitele služby, načtěte informačního kanálu ze služby, zobrazit informační kanál a počkejte uživateli stiskněte klávesu ENTER.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-118">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#8)]
     [!code-vb[htAtomBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="a1c5c-119">K volání GetBlog() s HTTP GET</span><span class="sxs-lookup"><span data-stu-id="a1c5c-119">To call GetBlog() with an HTTP GET</span></span>  
  
1.  <span data-ttu-id="a1c5c-120">Otevřete Internet Explorer, zadejte následující adresu URL a stiskněte klávesu ENTER: http://localhost: 8000/BlogService/GetBlog</span><span class="sxs-lookup"><span data-stu-id="a1c5c-120">Open Internet Explorer, type the following URL, and press ENTER: http://localhost:8000/BlogService/GetBlog</span></span>  
  
     <span data-ttu-id="a1c5c-121">Adresa URL obsahuje základní adresa služby (http://localhost: 8000/BlogService), relativní adresa koncového bodu a volat operace služby.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-121">The URL contains the base address of the service (http://localhost:8000/BlogService), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="a1c5c-122">GetBlog() volat z kódu</span><span class="sxs-lookup"><span data-stu-id="a1c5c-122">To call GetBlog() from code</span></span>  
  
1.  <span data-ttu-id="a1c5c-123">Vytvoření <xref:System.Xml.XmlReader> s základní adresu a při volání metody.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-123">Create a <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#9)]
     [!code-vb[htAtomBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#9)]  
  
2.  <span data-ttu-id="a1c5c-124">Zavolejte statickou <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> předávání v případě metody <xref:System.Xml.XmlReader> jste právě vytvořili.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-124">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#10)]
     [!code-vb[htAtomBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#10)]  
  
     <span data-ttu-id="a1c5c-125">To vyvolá operaci služby a naplní novou <xref:System.ServiceModel.Syndication.SyndicationFeed> k formátování vrácená z operace služby.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-125">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3.  <span data-ttu-id="a1c5c-126">Přístup k objekt informačního kanálu.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-126">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#11)]
     [!code-vb[htAtomBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="a1c5c-127">Příklad</span><span class="sxs-lookup"><span data-stu-id="a1c5c-127">Example</span></span>  
 <span data-ttu-id="a1c5c-128">Zde je úplný výpis pro tento příklad kódu.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-128">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#12)]
 [!code-vb[htAtomBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1c5c-129">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="a1c5c-129">Compiling the Code</span></span>  
 <span data-ttu-id="a1c5c-130">Při kompilování předchozí kód, odkazuje System.ServiceModel.dll a System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="a1c5c-130">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c5c-131">Viz také</span><span class="sxs-lookup"><span data-stu-id="a1c5c-131">See Also</span></span>  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>