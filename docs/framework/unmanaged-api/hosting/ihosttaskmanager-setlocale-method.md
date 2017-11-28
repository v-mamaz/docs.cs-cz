---
title: "IHostTaskManager::SetLocale – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetLocale
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 885dd41a3bc5afb156d1f338fb3564731d5a742a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="2f8c4-102">IHostTaskManager::SetLocale – metoda</span><span class="sxs-lookup"><span data-stu-id="2f8c4-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="2f8c4-103">Upozorní hostitele, že se změnila common language runtime (CLR), národní prostředí nebo jazykovou verzi na aktuálně spuštěné úlohy.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f8c4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2f8c4-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f8c4-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2f8c4-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="2f8c4-106">[v] Hodnota identifikátoru národního prostředí, která se mapuje na nově přiřazené zeměpisné jazykovou verzi a jazyka.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f8c4-107">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="2f8c4-107">Return Value</span></span>  
  
|<span data-ttu-id="2f8c4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f8c4-108">HRESULT</span></span>|<span data-ttu-id="2f8c4-109">Popis</span><span class="sxs-lookup"><span data-stu-id="2f8c4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f8c4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f8c4-110">S_OK</span></span>|<span data-ttu-id="2f8c4-111">`SetLocale`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="2f8c4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f8c4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f8c4-113">Modul CLR nebyla načtena do procesu nebo CLR je ve stavu, ve kterém nemůže běžet spravovaného kódu nebo úspěšně zpracovat volání.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f8c4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f8c4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f8c4-115">Vypršel časový limit volání.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-115">The call timed out.</span></span>|  
|<span data-ttu-id="2f8c4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f8c4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f8c4-117">Volající není vlastníkem zámek.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f8c4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f8c4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f8c4-119">Událost byla zrušena při blokované vlákna nebo fiber čekal na něm.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f8c4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f8c4-120">E_FAIL</span></span>|<span data-ttu-id="2f8c4-121">Došlo k neznámému závažné selhání.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f8c4-122">Po návratu metody E_FAIL modulu CLR již není použitelné v rámci procesu.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f8c4-123">Následující volání hostování metody vrací HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2f8c4-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2f8c4-124">E_NOTIMPL</span></span>|<span data-ttu-id="2f8c4-125">Hostiteli neumožňuje spravované uživatelského kódu k úpravě národní prostředí.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f8c4-126">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2f8c4-126">Remarks</span></span>  
 <span data-ttu-id="2f8c4-127">Volání modulu runtime `SetLocale` při hodnotu <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> vlastnost je změnit pomocí spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="2f8c4-128">Tato metoda poskytuje možnost pro hostitele k provedení nějaké mechanismy, které může mít pro synchronizaci národní prostředí.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="2f8c4-129">Pokud hostitel neumožňuje národní prostředí se musí změnit ze spravovaného kódu nebo neimplementuje mechanismus k synchronizaci národní prostředí, měla by vrátit E_NOTIMPL z této metody.</span><span class="sxs-lookup"><span data-stu-id="2f8c4-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f8c4-130">Požadavky</span><span class="sxs-lookup"><span data-stu-id="2f8c4-130">Requirements</span></span>  
 <span data-ttu-id="2f8c4-131">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f8c4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f8c4-132">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2f8c4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f8c4-133">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f8c4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f8c4-134">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f8c4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8c4-135">Viz také</span><span class="sxs-lookup"><span data-stu-id="2f8c4-135">See Also</span></span>  
 [<span data-ttu-id="2f8c4-136">Iclrtask – rozhraní</span><span class="sxs-lookup"><span data-stu-id="2f8c4-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2f8c4-137">Iclrtaskmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="2f8c4-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2f8c4-138">Ihosttask – rozhraní</span><span class="sxs-lookup"><span data-stu-id="2f8c4-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2f8c4-139">Ihosttaskmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="2f8c4-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="2f8c4-140">Setuilocale – metoda</span><span class="sxs-lookup"><span data-stu-id="2f8c4-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)