---
title: "Výjimky transakce a kompenzace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be803580a4d8ed195222e5960cfa6e26804d91c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="07d95-102">Výjimky transakce a kompenzace</span><span class="sxs-lookup"><span data-stu-id="07d95-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="07d95-103">poskytuje několik různých mechanismů pro nakládání běhu chybové stavy v pracovních postupech.</span><span class="sxs-lookup"><span data-stu-id="07d95-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="07d95-104">Pracovní postupy můžete použít kombinaci obslužné rutiny výjimek, transakce, zrušení a náhrady ke zpracování a elegantně zotavit chybové stavy.</span><span class="sxs-lookup"><span data-stu-id="07d95-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07d95-105">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="07d95-105">In This Section</span></span>  
 [<span data-ttu-id="07d95-106">Výjimky</span><span class="sxs-lookup"><span data-stu-id="07d95-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="07d95-107">Ukazuje, jak používat <xref:System.Activities.Statements.TryCatch> aktivity zpracování výjimek v pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="07d95-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="07d95-108">Transakce</span><span class="sxs-lookup"><span data-stu-id="07d95-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="07d95-109">Ukazuje, jak používat <xref:System.Activities.Statements.TransactionScope> aktivity pro použití transakcí v pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="07d95-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="07d95-110">Kompenzace</span><span class="sxs-lookup"><span data-stu-id="07d95-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="07d95-111">Popisuje kompenzace v pracovních postupech a ukazuje, jak pomocí aktivity kompenzace, jako například <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, a <xref:System.Activities.Statements.Confirm>.</span><span class="sxs-lookup"><span data-stu-id="07d95-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="07d95-112">Zrušení</span><span class="sxs-lookup"><span data-stu-id="07d95-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="07d95-113">Popisuje postup při zrušení zpracování v pracovních postupech, pomocí zabudované aktivity, jakož i vlastní aktivity.</span><span class="sxs-lookup"><span data-stu-id="07d95-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="07d95-114">Ladění pracovních postupů</span><span class="sxs-lookup"><span data-stu-id="07d95-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="07d95-115">Popisuje, jak k ladění pracovních postupů.</span><span class="sxs-lookup"><span data-stu-id="07d95-115">Describes how to debug workflows.</span></span>