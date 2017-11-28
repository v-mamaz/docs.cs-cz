---
title: "IMetaDataImport::EnumMembersWithName – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembersWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64568fb185cd8a18e43639568ecb67fcfa350dba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="c1dfb-102">IMetaDataImport::EnumMembersWithName – metoda</span><span class="sxs-lookup"><span data-stu-id="c1dfb-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="c1dfb-103">Vytvoří výčet MemberDef tokeny představující členů zadaného typu se zadaným názvem.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1dfb-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c1dfb-104">Syntax</span></span>  
  
```  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1dfb-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c1dfb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c1dfb-106">[ve out] Ukazatel na enumerátor.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="c1dfb-107">[v] TypeDef token představující typ se členy do zobrazení výčtu.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="c1dfb-108">[v] Název člena, který omezuje obor enumerátor.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="c1dfb-109">[out] Pole používá k ukládání MemberDef tokenů.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c1dfb-110">[v] Maximální velikost `rMembers` pole.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c1dfb-111">[out] Skutečný počet MemberDef tokeny, vrátí se v `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1dfb-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c1dfb-112">Remarks</span></span>  
 <span data-ttu-id="c1dfb-113">Tato metoda zobrazí pole a metody, ale ne vlastnosti nebo události.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="c1dfb-114">Na rozdíl od [imetadataimport::enummembers –](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` zahodí všechny pole a člen tokeny, které nemají zadaný název.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1dfb-115">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="c1dfb-115">Return Value</span></span>  
  
|<span data-ttu-id="c1dfb-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1dfb-116">HRESULT</span></span>|<span data-ttu-id="c1dfb-117">Popis</span><span class="sxs-lookup"><span data-stu-id="c1dfb-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c1dfb-118">`EnumTypeDefs`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c1dfb-119">Neexistují žádné MemberDef tokenů pro zobrazení výčtu.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="c1dfb-120">V takovém případě `pcTokens` je nulová.</span><span class="sxs-lookup"><span data-stu-id="c1dfb-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1dfb-121">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c1dfb-121">Requirements</span></span>  
 <span data-ttu-id="c1dfb-122">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1dfb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1dfb-123">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1dfb-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1dfb-124">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1dfb-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1dfb-125">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1dfb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1dfb-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="c1dfb-126">See Also</span></span>  
 [<span data-ttu-id="c1dfb-127">Imetadataimport – rozhraní</span><span class="sxs-lookup"><span data-stu-id="c1dfb-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c1dfb-128">Imetadataimport2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="c1dfb-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)