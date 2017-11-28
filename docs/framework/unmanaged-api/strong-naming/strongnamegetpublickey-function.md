---
title: "StrongNameGetPublicKey – funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type: DLLExport
f1_keywords: StrongNameGetPublicKey
helpviewer_keywords: StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 243b5f8d94805d8631c7c79f424d9e6434213bb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="5a8a4-102">StrongNameGetPublicKey – funkce</span><span class="sxs-lookup"><span data-stu-id="5a8a4-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="5a8a4-103">Získá veřejný klíč z páru soukromého a veřejného klíče.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="5a8a4-104">Pár klíčů můžete zadat jako název kontejneru klíčů v rámci zprostředkovatele kryptografických služeb (CSP) nebo jako soubor raw bajtů.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="5a8a4-105">Tato funkce je zastaralá.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-105">This function has been deprecated.</span></span> <span data-ttu-id="5a8a4-106">Použití [iclrstrongname::strongnamegetpublickey –](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) metoda místo.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a8a4-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5a8a4-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a8a4-108">Parametry</span><span class="sxs-lookup"><span data-stu-id="5a8a4-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="5a8a4-109">[v] Název kontejneru klíčů, který obsahuje pár veřejného a privátního klíče.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="5a8a4-110">Pokud `pbKeyBlob` má hodnotu null, `szKeyContainer` musíte zadat platný kontejner v rámci CSP.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="5a8a4-111">V takovém případě `StrongNameGetPublicKey` extrahuje veřejný klíč z tohoto páru klíčů ukládat do kontejneru.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="5a8a4-112">Pokud `pbKeyBlob` nemá hodnotu null, dvojici klíčů se předpokládá, že mají být obsažena v klíče binární rozsáhlý objekt (binární rozsáhlý OBJEKT).</span><span class="sxs-lookup"><span data-stu-id="5a8a4-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="5a8a4-113">Klíče musí být Rivest-Shamir-Adleman 1024 bitů (RSA) podpisových klíčů.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="5a8a4-114">Žádné jiné typy klíčů jsou podporovány v tuto chvíli.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5a8a4-115">[v] Ukazatel na pár veřejného a privátního klíče.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="5a8a4-116">Tato dvojice je ve formátu vytvořené Win32 `CryptExportKey` funkce.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="5a8a4-117">Pokud `pbKeyBlob` je null, kontejner klíčů určeného `szKeyContainer` se předpokládá, že obsahovat dvojici klíčů.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5a8a4-118">[v] Velikost v bajtech z `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="5a8a4-119">[out] Vrácený veřejný klíč objektu BLOB.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="5a8a4-120">`ppbPublicKeyBlob` Parametr je přidělena modul common language runtime a vrácen volajícímu.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="5a8a4-121">Volající musí uvolnění paměti pomocí [strongnamefreebuffer –](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funkce.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-121">The caller must free the memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="5a8a4-122">[out] Velikost veřejného klíče vráceného objektu BLOB.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a8a4-123">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="5a8a4-123">Return Value</span></span>  
 <span data-ttu-id="5a8a4-124">`true`Při úspěšném dokončení; v opačném `false`.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a8a4-125">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5a8a4-125">Remarks</span></span>  
 <span data-ttu-id="5a8a4-126">Veřejný klíč je součástí [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) struktury.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="5a8a4-127">Pokud `StrongNameGetPublicKey` není úspěšně dokončit, volání funkce [strongnameerrorinfo –](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funkce načíst poslední generované chyba.</span><span class="sxs-lookup"><span data-stu-id="5a8a4-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a8a4-128">Požadavky</span><span class="sxs-lookup"><span data-stu-id="5a8a4-128">Requirements</span></span>  
 <span data-ttu-id="5a8a4-129">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a8a4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a8a4-130">**Záhlaví:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5a8a4-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5a8a4-131">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a8a4-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a8a4-132">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a8a4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a8a4-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="5a8a4-133">See Also</span></span>  
 [<span data-ttu-id="5a8a4-134">Strongnamegetpublickey – metoda</span><span class="sxs-lookup"><span data-stu-id="5a8a4-134">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="5a8a4-135">Strongnametokenfrompublickey – metoda</span><span class="sxs-lookup"><span data-stu-id="5a8a4-135">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="5a8a4-136">Iclrstrongname – rozhraní</span><span class="sxs-lookup"><span data-stu-id="5a8a4-136">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="5a8a4-137">PublicKeyBlob – struktura</span><span class="sxs-lookup"><span data-stu-id="5a8a4-137">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)