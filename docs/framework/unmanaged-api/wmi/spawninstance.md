---
title: "Funkce SpawnInstance (referenční dokumentace nespravovaného rozhraní API)"
description: "Funkce SpawnInstance vytvoří novou instanci třídy."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnInstance
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnInstance
helpviewer_keywords: SpawnInstance function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 65050772e2f933583506b6612c32c6060f1d20df
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="spawninstance-function"></a><span data-ttu-id="7c27e-103">SpawnInstance – funkce</span><span class="sxs-lookup"><span data-stu-id="7c27e-103">SpawnInstance function</span></span>
<span data-ttu-id="7c27e-104">Vytvoří novou instanci třídy.</span><span class="sxs-lookup"><span data-stu-id="7c27e-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7c27e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7c27e-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="7c27e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="7c27e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7c27e-107">[v] Tento parametr se nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="7c27e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7c27e-108">[v] Ukazatel na [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span><span class="sxs-lookup"><span data-stu-id="7c27e-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="7c27e-109">[v] Vyhrazena.</span><span class="sxs-lookup"><span data-stu-id="7c27e-109">[in] Reserved.</span></span> <span data-ttu-id="7c27e-110">Tento parametr musí být 0.</span><span class="sxs-lookup"><span data-stu-id="7c27e-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="7c27e-111">[out] Obdrží má ukazatel na novou instanci třídy.</span><span class="sxs-lookup"><span data-stu-id="7c27e-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="7c27e-112">Pokud dojde k chybě, nový objekt, který se vrátí, a `ppNewInstance` je ponechat beze změny doleva.</span><span class="sxs-lookup"><span data-stu-id="7c27e-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="7c27e-113">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="7c27e-113">Return value</span></span>

<span data-ttu-id="7c27e-114">Následující hodnoty, vrátí tato funkce jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:</span><span class="sxs-lookup"><span data-stu-id="7c27e-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7c27e-115">Konstanta</span><span class="sxs-lookup"><span data-stu-id="7c27e-115">Constant</span></span>  |<span data-ttu-id="7c27e-116">Hodnota</span><span class="sxs-lookup"><span data-stu-id="7c27e-116">Value</span></span>  |<span data-ttu-id="7c27e-117">Popis</span><span class="sxs-lookup"><span data-stu-id="7c27e-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="7c27e-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="7c27e-118">0x80041020</span></span> | <span data-ttu-id="7c27e-119">`ptr`není platnou třídu definice a nelze vytvořit nové instance.</span><span class="sxs-lookup"><span data-stu-id="7c27e-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="7c27e-120">Buď je neúplný nebo nebyl zaregistrován s Správa systému Windows voláním [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="7c27e-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7c27e-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7c27e-121">0x80041006</span></span> | <span data-ttu-id="7c27e-122">Je k dispozici k dokončení operace není dostatek paměti.</span><span class="sxs-lookup"><span data-stu-id="7c27e-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7c27e-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7c27e-123">0x80041008</span></span> | <span data-ttu-id="7c27e-124">`ppNewClass`je `null`.</span><span class="sxs-lookup"><span data-stu-id="7c27e-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7c27e-125">0</span><span class="sxs-lookup"><span data-stu-id="7c27e-125">0</span></span> | <span data-ttu-id="7c27e-126">Volání funkce byla úspěšná.</span><span class="sxs-lookup"><span data-stu-id="7c27e-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7c27e-127">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7c27e-127">Remarks</span></span>

<span data-ttu-id="7c27e-128">Tato funkce zabalí volání [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="7c27e-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="7c27e-129">`ptr`musí být definice třídy získány z Správa systému Windows.</span><span class="sxs-lookup"><span data-stu-id="7c27e-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="7c27e-130">(Všimněte si, že při vytváření kopie instance z instance je podporována, ale vrácené instance je prázdný.) Tato definice třídy pak použijete k vytvoření nové instance.</span><span class="sxs-lookup"><span data-stu-id="7c27e-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="7c27e-131">Volání [PutInstanceWmi](putinstancewmi.md) funkce je povinný, pokud máte v úmyslu zápis instance správy systému Windows.</span><span class="sxs-lookup"><span data-stu-id="7c27e-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="7c27e-132">Nový objekt vrácený v `ppNewClass` automaticky stane podtřídy aktuálního objektu.</span><span class="sxs-lookup"><span data-stu-id="7c27e-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="7c27e-133">Toto chování nelze přepsat.</span><span class="sxs-lookup"><span data-stu-id="7c27e-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="7c27e-134">Není k dispozici žádnou jinou metodu, pomocí kterého lze vytvořit podtřídy (odvozené třídy).</span><span class="sxs-lookup"><span data-stu-id="7c27e-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c27e-135">Požadavky</span><span class="sxs-lookup"><span data-stu-id="7c27e-135">Requirements</span></span>  
 <span data-ttu-id="7c27e-136">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c27e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c27e-137">**Záhlaví:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7c27e-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7c27e-138">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7c27e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c27e-139">Viz také</span><span class="sxs-lookup"><span data-stu-id="7c27e-139">See also</span></span>  
[<span data-ttu-id="7c27e-140">Rozhraní WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)</span><span class="sxs-lookup"><span data-stu-id="7c27e-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)