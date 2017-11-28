---
title: 1026 - ScheduleTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d881f1be4e809cf45f100b966d6013ae8fa88f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="44bb5-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="44bb5-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="44bb5-103">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="44bb5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44bb5-104">ID</span><span class="sxs-lookup"><span data-stu-id="44bb5-104">ID</span></span>|<span data-ttu-id="44bb5-105">1026</span><span class="sxs-lookup"><span data-stu-id="44bb5-105">1026</span></span>|  
|<span data-ttu-id="44bb5-106">Klíčová slova</span><span class="sxs-lookup"><span data-stu-id="44bb5-106">Keywords</span></span>|<span data-ttu-id="44bb5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="44bb5-107">WFRuntime</span></span>|  
|<span data-ttu-id="44bb5-108">úroveň</span><span class="sxs-lookup"><span data-stu-id="44bb5-108">Level</span></span>|<span data-ttu-id="44bb5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="44bb5-109">Verbose</span></span>|  
|<span data-ttu-id="44bb5-110">Kanál</span><span class="sxs-lookup"><span data-stu-id="44bb5-110">Channel</span></span>|<span data-ttu-id="44bb5-111">Aplikaci Microsoft Windows Server – aplikace/Debug</span><span class="sxs-lookup"><span data-stu-id="44bb5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="44bb5-112">Popis</span><span class="sxs-lookup"><span data-stu-id="44bb5-112">Description</span></span>  
 <span data-ttu-id="44bb5-113">Označuje, že bylo naplánováno TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="44bb5-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="44bb5-114">Zpráva</span><span class="sxs-lookup"><span data-stu-id="44bb5-114">Message</span></span>  
 <span data-ttu-id="44bb5-115">Bylo naplánováno TransactionContextWorkItem aktivity %1, DisplayName: %2, identifikátor InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="44bb5-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="44bb5-116">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="44bb5-116">Details</span></span>  
  
|<span data-ttu-id="44bb5-117">Název položky dat</span><span class="sxs-lookup"><span data-stu-id="44bb5-117">Data Item Name</span></span>|<span data-ttu-id="44bb5-118">Datová položka – Typ</span><span class="sxs-lookup"><span data-stu-id="44bb5-118">Data Item Type</span></span>|<span data-ttu-id="44bb5-119">Popis</span><span class="sxs-lookup"><span data-stu-id="44bb5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="44bb5-120">Aktivita</span><span class="sxs-lookup"><span data-stu-id="44bb5-120">Activity</span></span>|<span data-ttu-id="44bb5-121">xs:String</span><span class="sxs-lookup"><span data-stu-id="44bb5-121">xs:string</span></span>|<span data-ttu-id="44bb5-122">Název typu aktivity.</span><span class="sxs-lookup"><span data-stu-id="44bb5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="44bb5-123">displayName</span><span class="sxs-lookup"><span data-stu-id="44bb5-123">DisplayName</span></span>|<span data-ttu-id="44bb5-124">xs:String</span><span class="sxs-lookup"><span data-stu-id="44bb5-124">xs:string</span></span>|<span data-ttu-id="44bb5-125">Zobrazovaný název aktivity.</span><span class="sxs-lookup"><span data-stu-id="44bb5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="44bb5-126">identifikátor instanceId</span><span class="sxs-lookup"><span data-stu-id="44bb5-126">InstanceId</span></span>|<span data-ttu-id="44bb5-127">xs:String</span><span class="sxs-lookup"><span data-stu-id="44bb5-127">xs:string</span></span>|<span data-ttu-id="44bb5-128">Id instance aktivity.</span><span class="sxs-lookup"><span data-stu-id="44bb5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="44bb5-129">Domény aplikace</span><span class="sxs-lookup"><span data-stu-id="44bb5-129">AppDomain</span></span>|<span data-ttu-id="44bb5-130">xs:String</span><span class="sxs-lookup"><span data-stu-id="44bb5-130">xs:string</span></span>|<span data-ttu-id="44bb5-131">Řetězec vrácený AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="44bb5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|