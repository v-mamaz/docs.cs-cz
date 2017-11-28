---
title: Mappings1 typ dat Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 746013a11d10162a78116ff41d0b09d942f7651b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-data-type-mappings"></a><span data-ttu-id="acb8f-102">Mapování datového typu Oracle</span><span class="sxs-lookup"><span data-stu-id="acb8f-102">Oracle Data Type Mappings</span></span>
<span data-ttu-id="acb8f-103">Následující tabulka uvádí typy dat Oracle a jejich mapování <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="acb8f-103">The following table lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
|<span data-ttu-id="acb8f-104">Oracle datový typ</span><span class="sxs-lookup"><span data-stu-id="acb8f-104">Oracle data type</span></span>|<span data-ttu-id="acb8f-105">Datový typ rozhraní .NET framework vrácený OracleDataReader.GetValue</span><span class="sxs-lookup"><span data-stu-id="acb8f-105">.NET Framework data type returned by OracleDataReader.GetValue</span></span>|<span data-ttu-id="acb8f-106">OracleClient datový typ vrácený OracleDataReader.GetOracleValue</span><span class="sxs-lookup"><span data-stu-id="acb8f-106">OracleClient data type returned by OracleDataReader.GetOracleValue</span></span>|<span data-ttu-id="acb8f-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="acb8f-107">Remarks</span></span>|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|<span data-ttu-id="acb8f-108">**BFILE**</span><span class="sxs-lookup"><span data-stu-id="acb8f-108">**BFILE**</span></span>|<span data-ttu-id="acb8f-109">**Byte]**</span><span class="sxs-lookup"><span data-stu-id="acb8f-109">**Byte[]**</span></span>|<xref:System.Data.OracleClient.OracleBFile>||  
|<span data-ttu-id="acb8f-110">**OBJEKT BLOB**</span><span class="sxs-lookup"><span data-stu-id="acb8f-110">**BLOB**</span></span>|<span data-ttu-id="acb8f-111">**Byte]**</span><span class="sxs-lookup"><span data-stu-id="acb8f-111">**Byte[]**</span></span>|<xref:System.Data.OracleClient.OracleLob>||  
|<span data-ttu-id="acb8f-112">**CHAR –**</span><span class="sxs-lookup"><span data-stu-id="acb8f-112">**CHAR**</span></span>|<span data-ttu-id="acb8f-113">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-113">**String**</span></span>|<xref:System.Data.OracleClient.OracleString>||  
|<span data-ttu-id="acb8f-114">**DATOVÝ TYP CLOB**</span><span class="sxs-lookup"><span data-stu-id="acb8f-114">**CLOB**</span></span>|<span data-ttu-id="acb8f-115">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-115">**String**</span></span>|<xref:System.Data.OracleClient.OracleLob>||  
|<span data-ttu-id="acb8f-116">**DATUM**</span><span class="sxs-lookup"><span data-stu-id="acb8f-116">**DATE**</span></span>|<span data-ttu-id="acb8f-117">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-117">**DateTime**</span></span>|<xref:System.Data.OracleClient.OracleDateTime>||  
|<span data-ttu-id="acb8f-118">**PLOVOUCÍ DESETINNÁ ČÁRKA**</span><span class="sxs-lookup"><span data-stu-id="acb8f-118">**FLOAT**</span></span>|<span data-ttu-id="acb8f-119">**Decimal**</span><span class="sxs-lookup"><span data-stu-id="acb8f-119">**Decimal**</span></span>|<xref:System.Data.OracleClient.OracleNumber>|<span data-ttu-id="acb8f-120">Tento datový typ je alias **číslo** datového typu a je navržený tak, tak, aby <xref:System.Data.OracleClient.OracleDataReader> vrátí **System.Decimal** nebo <xref:System.Data.OracleClient.OracleNumber> místo hodnotu s plovoucí desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="acb8f-120">This data type is an alias for the **NUMBER** data type, and is designed so that the <xref:System.Data.OracleClient.OracleDataReader> returns a **System.Decimal** or <xref:System.Data.OracleClient.OracleNumber> instead of a floating-point value.</span></span> <span data-ttu-id="acb8f-121">Použití datový typ rozhraní .NET Framework může způsobit přetečení.</span><span class="sxs-lookup"><span data-stu-id="acb8f-121">Using the .NET Framework data type can cause an overflow.</span></span>|  
|<span data-ttu-id="acb8f-122">**CELÉ ČÍSLO**</span><span class="sxs-lookup"><span data-stu-id="acb8f-122">**INTEGER**</span></span>|<span data-ttu-id="acb8f-123">**Decimal**</span><span class="sxs-lookup"><span data-stu-id="acb8f-123">**Decimal**</span></span>|<xref:System.Data.OracleClient.OracleNumber>|<span data-ttu-id="acb8f-124">Tento datový typ je alias **NUMBER(38)** datového typu a je navržený tak, tak, aby <xref:System.Data.OracleClient.OracleDataReader> vrátí **System.Decimal** nebo <xref:System.Data.OracleClient.OracleNumber> místo celočíselnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="acb8f-124">This data type is an alias for the **NUMBER(38)** data type, and is designed so that the <xref:System.Data.OracleClient.OracleDataReader> returns a **System.Decimal** or <xref:System.Data.OracleClient.OracleNumber> instead of an integer value.</span></span> <span data-ttu-id="acb8f-125">Použití datový typ rozhraní .NET Framework může způsobit přetečení.</span><span class="sxs-lookup"><span data-stu-id="acb8f-125">Using the .NET Framework data type can cause an overflow.</span></span>|  
|<span data-ttu-id="acb8f-126">**INTERVAL ROK, MĚSÍC**</span><span class="sxs-lookup"><span data-stu-id="acb8f-126">**INTERVAL YEAR TO MONTH**</span></span>|<span data-ttu-id="acb8f-127">**Int32**</span><span class="sxs-lookup"><span data-stu-id="acb8f-127">**Int32**</span></span>|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|<span data-ttu-id="acb8f-128">**DENNÍ INTERVAL SEKUNDY.**</span><span class="sxs-lookup"><span data-stu-id="acb8f-128">**INTERVAL DAY TO SECOND**</span></span>|<span data-ttu-id="acb8f-129">**Časový interval**</span><span class="sxs-lookup"><span data-stu-id="acb8f-129">**TimeSpan**</span></span>|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|<span data-ttu-id="acb8f-130">**DLOUHÁ**</span><span class="sxs-lookup"><span data-stu-id="acb8f-130">**LONG**</span></span>|<span data-ttu-id="acb8f-131">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-131">**String**</span></span>|<xref:System.Data.OracleClient.OracleString>||  
|<span data-ttu-id="acb8f-132">**DLOUHO NEZPRACOVANÁ**</span><span class="sxs-lookup"><span data-stu-id="acb8f-132">**LONG RAW**</span></span>|<span data-ttu-id="acb8f-133">**Byte]**</span><span class="sxs-lookup"><span data-stu-id="acb8f-133">**Byte[]**</span></span>|<xref:System.Data.OracleClient.OracleBinary>||  
|<span data-ttu-id="acb8f-134">**NCHAR**</span><span class="sxs-lookup"><span data-stu-id="acb8f-134">**NCHAR**</span></span>|<span data-ttu-id="acb8f-135">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-135">**String**</span></span>|<xref:System.Data.OracleClient.OracleString>||  
|<span data-ttu-id="acb8f-136">**NCLOB**</span><span class="sxs-lookup"><span data-stu-id="acb8f-136">**NCLOB**</span></span>|<span data-ttu-id="acb8f-137">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-137">**String**</span></span>|<xref:System.Data.OracleClient.OracleLob>||  
|<span data-ttu-id="acb8f-138">**ČÍSLO**</span><span class="sxs-lookup"><span data-stu-id="acb8f-138">**NUMBER**</span></span>|<span data-ttu-id="acb8f-139">**Decimal**</span><span class="sxs-lookup"><span data-stu-id="acb8f-139">**Decimal**</span></span>|<xref:System.Data.OracleClient.OracleNumber>|<span data-ttu-id="acb8f-140">Použití datový typ rozhraní .NET Framework může způsobit přetečení.</span><span class="sxs-lookup"><span data-stu-id="acb8f-140">Using the .NET Framework data type can cause an overflow.</span></span>|  
|<span data-ttu-id="acb8f-141">**NVARCHAR2**</span><span class="sxs-lookup"><span data-stu-id="acb8f-141">**NVARCHAR2**</span></span>|<span data-ttu-id="acb8f-142">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-142">**String**</span></span>|<xref:System.Data.OracleClient.OracleString>||  
|<span data-ttu-id="acb8f-143">**NEZPRACOVANÁ**</span><span class="sxs-lookup"><span data-stu-id="acb8f-143">**RAW**</span></span>|<span data-ttu-id="acb8f-144">**Byte]**</span><span class="sxs-lookup"><span data-stu-id="acb8f-144">**Byte[]**</span></span>|<xref:System.Data.OracleClient.OracleBinary>||  
|<span data-ttu-id="acb8f-145">**REF KURZORU**</span><span class="sxs-lookup"><span data-stu-id="acb8f-145">**REF CURSOR**</span></span>|||<span data-ttu-id="acb8f-146">Oracle **REF kurzor** datový typ není podporován <xref:System.Data.OracleClient.OracleDataReader> objektu.</span><span class="sxs-lookup"><span data-stu-id="acb8f-146">The Oracle **REF CURSOR** data type is not supported by the <xref:System.Data.OracleClient.OracleDataReader> object.</span></span>|  
|<span data-ttu-id="acb8f-147">**ID ŘÁDKU**</span><span class="sxs-lookup"><span data-stu-id="acb8f-147">**ROWID**</span></span>|<span data-ttu-id="acb8f-148">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-148">**String**</span></span>|<xref:System.Data.OracleClient.OracleString>||  
|<span data-ttu-id="acb8f-149">**ČASOVÉ RAZÍTKO**</span><span class="sxs-lookup"><span data-stu-id="acb8f-149">**TIMESTAMP**</span></span>|<span data-ttu-id="acb8f-150">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-150">**DateTime**</span></span>|<xref:System.Data.OracleClient.OracleDateTime>||  
|<span data-ttu-id="acb8f-151">**ČASOVÉ RAZÍTKO S MÍSTNÍM ČASOVÉM PÁSMU**</span><span class="sxs-lookup"><span data-stu-id="acb8f-151">**TIMESTAMP WITH LOCAL TIME ZONE**</span></span>|<span data-ttu-id="acb8f-152">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-152">**DateTime**</span></span>|<xref:System.Data.OracleClient.OracleDateTime>||  
|<span data-ttu-id="acb8f-153">**ČASOVÉ RAZÍTKO S ČASOVÝM PÁSMEM**</span><span class="sxs-lookup"><span data-stu-id="acb8f-153">**TIMESTAMP WITH TIME ZONE**</span></span>|<span data-ttu-id="acb8f-154">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-154">**DateTime**</span></span>|<xref:System.Data.OracleClient.OracleDateTime>||  
|<span data-ttu-id="acb8f-155">**CELÉ ČÍSLO BEZ ZNAMÉNKA**</span><span class="sxs-lookup"><span data-stu-id="acb8f-155">**UNSIGNED INTEGER**</span></span>|<span data-ttu-id="acb8f-156">**Číslo**</span><span class="sxs-lookup"><span data-stu-id="acb8f-156">**Number**</span></span>|<xref:System.Data.OracleClient.OracleNumber>|<span data-ttu-id="acb8f-157">Tento datový typ je alias **NUMBER(38)** datového typu a je navržený tak, tak, aby <xref:System.Data.OracleClient.OracleDataReader> vrátí **System.Decimal** nebo <xref:System.Data.OracleClient.OracleNumber> místo hodnoty celé číslo bez znaménka.</span><span class="sxs-lookup"><span data-stu-id="acb8f-157">This data type is an alias for the **NUMBER(38)** data type, and is designed so that the <xref:System.Data.OracleClient.OracleDataReader> returns a **System.Decimal** or <xref:System.Data.OracleClient.OracleNumber> instead of an unsigned integer value.</span></span> <span data-ttu-id="acb8f-158">Použití datový typ rozhraní .NET Framework může způsobit přetečení.</span><span class="sxs-lookup"><span data-stu-id="acb8f-158">Using the .NET Framework data type can cause an overflow.</span></span>|  
|<span data-ttu-id="acb8f-159">**VARCHAR2**</span><span class="sxs-lookup"><span data-stu-id="acb8f-159">**VARCHAR2**</span></span>|<span data-ttu-id="acb8f-160">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-160">**String**</span></span>|<xref:System.Data.OracleClient.OracleString>||  
  
 <span data-ttu-id="acb8f-161">Následující tabulka uvádí typy dat Oracle a datové typy rozhraní .NET Framework (**System.Data.DbType** a <xref:System.Data.OracleClient.OracleType>) chcete použít při vazbě je jako parametry.</span><span class="sxs-lookup"><span data-stu-id="acb8f-161">The following table lists Oracle data types and the .NET Framework data types (**System.Data.DbType** and <xref:System.Data.OracleClient.OracleType>) to use when binding them as parameters.</span></span>  
  
|<span data-ttu-id="acb8f-162">Oracle datový typ</span><span class="sxs-lookup"><span data-stu-id="acb8f-162">Oracle data type</span></span>|<span data-ttu-id="acb8f-163">Hodnota DbType výčtu pro vazbu jako parametr</span><span class="sxs-lookup"><span data-stu-id="acb8f-163">DbType enumeration to bind as a parameter</span></span>|<span data-ttu-id="acb8f-164">Výčet OracleType pro vazbu jako parametr</span><span class="sxs-lookup"><span data-stu-id="acb8f-164">OracleType enumeration to bind as a parameter</span></span>|<span data-ttu-id="acb8f-165">Poznámky</span><span class="sxs-lookup"><span data-stu-id="acb8f-165">Remarks</span></span>|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|<span data-ttu-id="acb8f-166">**BFILE**</span><span class="sxs-lookup"><span data-stu-id="acb8f-166">**BFILE**</span></span>||<span data-ttu-id="acb8f-167">**BFile**</span><span class="sxs-lookup"><span data-stu-id="acb8f-167">**BFile**</span></span>|<span data-ttu-id="acb8f-168">Oracle umožňuje pouze vazby **BFILE** jako **BFILE** parametr.</span><span class="sxs-lookup"><span data-stu-id="acb8f-168">Oracle only allows binding a **BFILE** as a **BFILE** parameter.</span></span> <span data-ttu-id="acb8f-169">Zprostředkovatel dat .NET pro Oracle není vytvořit automaticky za vás při pokusu vytvořit vazbu jinou hodnotu než**BFILE** hodnotu, jako například **byte []** nebo <xref:System.Data.OracleClient.OracleBinary>.</span><span class="sxs-lookup"><span data-stu-id="acb8f-169">The .NET Data Provider for Oracle does not automatically construct one for you if you attempt to bind a non-**BFILE** value, such as **byte[]** or <xref:System.Data.OracleClient.OracleBinary>.</span></span>|  
|<span data-ttu-id="acb8f-170">**OBJEKT BLOB**</span><span class="sxs-lookup"><span data-stu-id="acb8f-170">**BLOB**</span></span>||<span data-ttu-id="acb8f-171">**Objekt BLOB**</span><span class="sxs-lookup"><span data-stu-id="acb8f-171">**Blob**</span></span>|<span data-ttu-id="acb8f-172">Oracle umožňuje pouze vazby **BLOB** jako **BLOB** parametr.</span><span class="sxs-lookup"><span data-stu-id="acb8f-172">Oracle only allows binding a **BLOB** as a **BLOB** parameter.</span></span> <span data-ttu-id="acb8f-173">Zprostředkovatel dat .NET pro Oracle není vytvořit automaticky za vás při pokusu vytvořit vazbu jinou hodnotu než**BLOB** hodnotu, jako například **byte []** nebo <xref:System.Data.OracleClient.OracleBinary>.</span><span class="sxs-lookup"><span data-stu-id="acb8f-173">The .NET Data Provider for Oracle does not automatically construct one for you if you attempt to bind a non-**BLOB** value, such as **byte[]** or <xref:System.Data.OracleClient.OracleBinary>.</span></span>|  
|<span data-ttu-id="acb8f-174">**CHAR –**</span><span class="sxs-lookup"><span data-stu-id="acb8f-174">**CHAR**</span></span>|<span data-ttu-id="acb8f-175">**AnsiStringFixedLength**</span><span class="sxs-lookup"><span data-stu-id="acb8f-175">**AnsiStringFixedLength**</span></span>|<span data-ttu-id="acb8f-176">**Char –**</span><span class="sxs-lookup"><span data-stu-id="acb8f-176">**Char**</span></span>||  
|<span data-ttu-id="acb8f-177">**DATOVÝ TYP CLOB**</span><span class="sxs-lookup"><span data-stu-id="acb8f-177">**CLOB**</span></span>||<span data-ttu-id="acb8f-178">**Datový typ CLOB**</span><span class="sxs-lookup"><span data-stu-id="acb8f-178">**Clob**</span></span>|<span data-ttu-id="acb8f-179">Oracle umožňuje pouze vazby **datový typ CLOB** jako **datový typ CLOB** parametr.</span><span class="sxs-lookup"><span data-stu-id="acb8f-179">Oracle only allows binding a **CLOB** as a **CLOB** parameter.</span></span> <span data-ttu-id="acb8f-180">Zprostředkovatel dat .NET pro Oracle není vytvořit automaticky za vás při pokusu vytvořit vazbu jinou hodnotu než**datový typ CLOB** hodnotu, jako například **System.String** nebo <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="acb8f-180">The .NET Data Provider for Oracle does not automatically construct one for you if you attempt to bind a non-**CLOB** value, such as **System.String** or <xref:System.Data.OracleClient.OracleString>.</span></span>|  
|<span data-ttu-id="acb8f-181">**DATUM**</span><span class="sxs-lookup"><span data-stu-id="acb8f-181">**DATE**</span></span>|<span data-ttu-id="acb8f-182">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-182">**DateTime**</span></span>|<span data-ttu-id="acb8f-183">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-183">**DateTime**</span></span>||  
|<span data-ttu-id="acb8f-184">**PLOVOUCÍ DESETINNÁ ČÁRKA**</span><span class="sxs-lookup"><span data-stu-id="acb8f-184">**FLOAT**</span></span>|<span data-ttu-id="acb8f-185">**Jednoduché, Double, Decimal**</span><span class="sxs-lookup"><span data-stu-id="acb8f-185">**Single, Double, Decimal**</span></span>|<span data-ttu-id="acb8f-186">**Float, dvakrát, počet**</span><span class="sxs-lookup"><span data-stu-id="acb8f-186">**Float, Double, Number**</span></span>|<span data-ttu-id="acb8f-187"><xref:System.Data.OracleClient.OracleParameter.Size%2A>Určuje, **System.Data.DBType** a <xref:System.Data.OracleClient.OracleType>.</span><span class="sxs-lookup"><span data-stu-id="acb8f-187"><xref:System.Data.OracleClient.OracleParameter.Size%2A> determines the **System.Data.DBType** and <xref:System.Data.OracleClient.OracleType>.</span></span>|  
|<span data-ttu-id="acb8f-188">**CELÉ ČÍSLO**</span><span class="sxs-lookup"><span data-stu-id="acb8f-188">**INTEGER**</span></span>|<span data-ttu-id="acb8f-189">**SByte –, Int16, Int32, Int64, Decimal**</span><span class="sxs-lookup"><span data-stu-id="acb8f-189">**SByte, Int16, Int32, Int64, Decimal**</span></span>|<span data-ttu-id="acb8f-190">**SByte –, Int16, Int32, počet**</span><span class="sxs-lookup"><span data-stu-id="acb8f-190">**SByte, Int16, Int32, Number**</span></span>|<span data-ttu-id="acb8f-191"><xref:System.Data.OracleClient.OracleParameter.Size%2A>Určuje, **System.Data.DBType** a <xref:System.Data.OracleClient.OracleType>.</span><span class="sxs-lookup"><span data-stu-id="acb8f-191"><xref:System.Data.OracleClient.OracleParameter.Size%2A> determines the **System.Data.DBType** and <xref:System.Data.OracleClient.OracleType>.</span></span>|  
|<span data-ttu-id="acb8f-192">**INTERVAL ROK, MĚSÍC**</span><span class="sxs-lookup"><span data-stu-id="acb8f-192">**INTERVAL YEAR TO MONTH**</span></span>|<span data-ttu-id="acb8f-193">**Int32**</span><span class="sxs-lookup"><span data-stu-id="acb8f-193">**Int32**</span></span>|<span data-ttu-id="acb8f-194">**IntervalYearToMonth**</span><span class="sxs-lookup"><span data-stu-id="acb8f-194">**IntervalYearToMonth**</span></span>|<span data-ttu-id="acb8f-195"><xref:System.Data.OracleClient.OracleType>je k dispozici pouze v případě použití softwaru i Oracle 9i klienta a serveru.</span><span class="sxs-lookup"><span data-stu-id="acb8f-195"><xref:System.Data.OracleClient.OracleType> is only available when using both Oracle 9i client and server software.</span></span>|  
|<span data-ttu-id="acb8f-196">**DENNÍ INTERVAL SEKUNDY.**</span><span class="sxs-lookup"><span data-stu-id="acb8f-196">**INTERVAL DAY TO SECOND**</span></span>|<span data-ttu-id="acb8f-197">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="acb8f-197">**Object**</span></span>|<span data-ttu-id="acb8f-198">**IntervalDayToSecond**</span><span class="sxs-lookup"><span data-stu-id="acb8f-198">**IntervalDayToSecond**</span></span>|<span data-ttu-id="acb8f-199"><xref:System.Data.OracleClient.OracleType>je k dispozici pouze v případě použití softwaru i Oracle 9i klienta a serveru.</span><span class="sxs-lookup"><span data-stu-id="acb8f-199"><xref:System.Data.OracleClient.OracleType> is only available when using both Oracle 9i client and server software.</span></span>|  
|<span data-ttu-id="acb8f-200">**DLOUHÁ**</span><span class="sxs-lookup"><span data-stu-id="acb8f-200">**LONG**</span></span>|<span data-ttu-id="acb8f-201">**AnsiString**</span><span class="sxs-lookup"><span data-stu-id="acb8f-201">**AnsiString**</span></span>|<span data-ttu-id="acb8f-202">**LongVarChar**</span><span class="sxs-lookup"><span data-stu-id="acb8f-202">**LongVarChar**</span></span>||  
|<span data-ttu-id="acb8f-203">**DLOUHO NEZPRACOVANÁ**</span><span class="sxs-lookup"><span data-stu-id="acb8f-203">**LONG RAW**</span></span>|<span data-ttu-id="acb8f-204">**Binární**</span><span class="sxs-lookup"><span data-stu-id="acb8f-204">**Binary**</span></span>|<span data-ttu-id="acb8f-205">**LongRaw**</span><span class="sxs-lookup"><span data-stu-id="acb8f-205">**LongRaw**</span></span>||  
|<span data-ttu-id="acb8f-206">**NCHAR**</span><span class="sxs-lookup"><span data-stu-id="acb8f-206">**NCHAR**</span></span>|<span data-ttu-id="acb8f-207">**StringFixedLength**</span><span class="sxs-lookup"><span data-stu-id="acb8f-207">**StringFixedLength**</span></span>|<span data-ttu-id="acb8f-208">**NChar**</span><span class="sxs-lookup"><span data-stu-id="acb8f-208">**NChar**</span></span>||  
|<span data-ttu-id="acb8f-209">**NCLOB**</span><span class="sxs-lookup"><span data-stu-id="acb8f-209">**NCLOB**</span></span>||<span data-ttu-id="acb8f-210">**NClob**</span><span class="sxs-lookup"><span data-stu-id="acb8f-210">**NClob**</span></span>|<span data-ttu-id="acb8f-211">Oracle umožňuje pouze vazby **NCLOB** jako **NCLOB** parametr.</span><span class="sxs-lookup"><span data-stu-id="acb8f-211">Oracle only allows binding a **NCLOB** as a **NCLOB** parameter.</span></span> <span data-ttu-id="acb8f-212">Zprostředkovatel dat .NET pro Oracle není vytvořit automaticky za vás při pokusu vytvořit vazbu jinou hodnotu než**NCLOB** hodnotu, jako například **System.String** nebo <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="acb8f-212">The .NET Data Provider for Oracle does not automatically construct one for you if you attempt to bind a non-**NCLOB** value, such as **System.String** or <xref:System.Data.OracleClient.OracleString>.</span></span>|  
|<span data-ttu-id="acb8f-213">**ČÍSLO**</span><span class="sxs-lookup"><span data-stu-id="acb8f-213">**NUMBER**</span></span>|<span data-ttu-id="acb8f-214">**VarNumeric**</span><span class="sxs-lookup"><span data-stu-id="acb8f-214">**VarNumeric**</span></span>|<span data-ttu-id="acb8f-215">**Číslo**</span><span class="sxs-lookup"><span data-stu-id="acb8f-215">**Number**</span></span>||  
|<span data-ttu-id="acb8f-216">**NVARCHAR2**</span><span class="sxs-lookup"><span data-stu-id="acb8f-216">**NVARCHAR2**</span></span>|<span data-ttu-id="acb8f-217">**Řetězec**</span><span class="sxs-lookup"><span data-stu-id="acb8f-217">**String**</span></span>|<span data-ttu-id="acb8f-218">**NVarChar**</span><span class="sxs-lookup"><span data-stu-id="acb8f-218">**NVarChar**</span></span>||  
|<span data-ttu-id="acb8f-219">**NEZPRACOVANÁ**</span><span class="sxs-lookup"><span data-stu-id="acb8f-219">**RAW**</span></span>|<span data-ttu-id="acb8f-220">**Binární**</span><span class="sxs-lookup"><span data-stu-id="acb8f-220">**Binary**</span></span>|<span data-ttu-id="acb8f-221">**Nezpracovaná**</span><span class="sxs-lookup"><span data-stu-id="acb8f-221">**Raw**</span></span>||  
|<span data-ttu-id="acb8f-222">**REF KURZORU**</span><span class="sxs-lookup"><span data-stu-id="acb8f-222">**REF CURSOR**</span></span>||<span data-ttu-id="acb8f-223">**Kurzor**</span><span class="sxs-lookup"><span data-stu-id="acb8f-223">**Cursor**</span></span>|<span data-ttu-id="acb8f-224">Další informace najdete v tématu [Oracle REF kurzory](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).</span><span class="sxs-lookup"><span data-stu-id="acb8f-224">For more information, see [Oracle REF CURSORs](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).</span></span>|  
|<span data-ttu-id="acb8f-225">**ID ŘÁDKU**</span><span class="sxs-lookup"><span data-stu-id="acb8f-225">**ROWID**</span></span>|<span data-ttu-id="acb8f-226">**AnsiString**</span><span class="sxs-lookup"><span data-stu-id="acb8f-226">**AnsiString**</span></span>|<span data-ttu-id="acb8f-227">**ID řádku**</span><span class="sxs-lookup"><span data-stu-id="acb8f-227">**Rowid**</span></span>||  
|<span data-ttu-id="acb8f-228">**ČASOVÉ RAZÍTKO**</span><span class="sxs-lookup"><span data-stu-id="acb8f-228">**TIMESTAMP**</span></span>|<span data-ttu-id="acb8f-229">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-229">**DateTime**</span></span>|<span data-ttu-id="acb8f-230">**Časové razítko**</span><span class="sxs-lookup"><span data-stu-id="acb8f-230">**Timestamp**</span></span>|<span data-ttu-id="acb8f-231"><xref:System.Data.OracleClient.OracleType>je k dispozici pouze v případě použití softwaru i Oracle 9i klienta a serveru.</span><span class="sxs-lookup"><span data-stu-id="acb8f-231"><xref:System.Data.OracleClient.OracleType> is only available when using both Oracle 9i client and server software.</span></span>|  
|<span data-ttu-id="acb8f-232">**ČASOVÉ RAZÍTKO S MÍSTNÍM ČASOVÉM PÁSMU**</span><span class="sxs-lookup"><span data-stu-id="acb8f-232">**TIMESTAMP WITH LOCAL TIME ZONE**</span></span>|<span data-ttu-id="acb8f-233">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-233">**DateTime**</span></span>|<span data-ttu-id="acb8f-234">**TimestampLocal**</span><span class="sxs-lookup"><span data-stu-id="acb8f-234">**TimestampLocal**</span></span>|<span data-ttu-id="acb8f-235"><xref:System.Data.OracleClient.OracleType>je k dispozici pouze v případě použití softwaru i Oracle 9i klienta a serveru.</span><span class="sxs-lookup"><span data-stu-id="acb8f-235"><xref:System.Data.OracleClient.OracleType> is only available when using both Oracle 9i client and server software.</span></span>|  
|<span data-ttu-id="acb8f-236">**ČASOVÉ RAZÍTKO S ČASOVÝM PÁSMEM**</span><span class="sxs-lookup"><span data-stu-id="acb8f-236">**TIMESTAMP WITH TIME ZONE**</span></span>|<span data-ttu-id="acb8f-237">**Data a času**</span><span class="sxs-lookup"><span data-stu-id="acb8f-237">**DateTime**</span></span>|<span data-ttu-id="acb8f-238">**TimestampWithTz**</span><span class="sxs-lookup"><span data-stu-id="acb8f-238">**TimestampWithTz**</span></span>|<span data-ttu-id="acb8f-239"><xref:System.Data.OracleClient.OracleType>je k dispozici pouze v případě použití softwaru i Oracle 9i klienta a serveru.</span><span class="sxs-lookup"><span data-stu-id="acb8f-239"><xref:System.Data.OracleClient.OracleType> is only available when using both Oracle 9i client and server software.</span></span>|  
|<span data-ttu-id="acb8f-240">**CELÉ ČÍSLO BEZ ZNAMÉNKA**</span><span class="sxs-lookup"><span data-stu-id="acb8f-240">**UNSIGNED INTEGER**</span></span>|<span data-ttu-id="acb8f-241">**Byte, UInt16, UInt32, UInt64, Decimal**</span><span class="sxs-lookup"><span data-stu-id="acb8f-241">**Byte, UInt16, UInt32, UInt64, Decimal**</span></span>|<span data-ttu-id="acb8f-242">**Uint32 bajtů, UInt16, počet**</span><span class="sxs-lookup"><span data-stu-id="acb8f-242">**Byte, UInt16, Uint32, Number**</span></span>|<span data-ttu-id="acb8f-243"><xref:System.Data.OracleClient.OracleParameter.Size%2A>Určuje, **System.Data.DBType** a <xref:System.Data.OracleClient.OracleType>.</span><span class="sxs-lookup"><span data-stu-id="acb8f-243"><xref:System.Data.OracleClient.OracleParameter.Size%2A> determines the **System.Data.DBType** and <xref:System.Data.OracleClient.OracleType>.</span></span>|  
|<span data-ttu-id="acb8f-244">**VARCHAR2**</span><span class="sxs-lookup"><span data-stu-id="acb8f-244">**VARCHAR2**</span></span>|<span data-ttu-id="acb8f-245">**AnsiString**</span><span class="sxs-lookup"><span data-stu-id="acb8f-245">**AnsiString**</span></span>|<span data-ttu-id="acb8f-246">**VarChar**</span><span class="sxs-lookup"><span data-stu-id="acb8f-246">**VarChar**</span></span>||  
  
 <span data-ttu-id="acb8f-247">**Vstup/výstup**, **výstup**, a **ReturnValue** **ParameterDirection** hodnoty používané <xref:System.Data.OracleClient.OracleParameter.Value%2A> vlastnost <xref:System.Data.OracleClient.OracleParameter> objekt jsou datové typy rozhraní .NET Framework, pokud vstupní hodnota je datového typu Oracle (například <xref:System.Data.OracleClient.OracleNumber> nebo <xref:System.Data.OracleClient.OracleString>).</span><span class="sxs-lookup"><span data-stu-id="acb8f-247">The **InputOutput**, **Output**, and **ReturnValue** **ParameterDirection** values used by the <xref:System.Data.OracleClient.OracleParameter.Value%2A> property of the <xref:System.Data.OracleClient.OracleParameter> object are .NET Framework data types, unless the input value is an Oracle data type (for example, <xref:System.Data.OracleClient.OracleNumber> or <xref:System.Data.OracleClient.OracleString>).</span></span> <span data-ttu-id="acb8f-248">To neplatí pro **REF kurzor**, **BFILE**, nebo **obchodní** datové typy.</span><span class="sxs-lookup"><span data-stu-id="acb8f-248">This does not apply to **REF CURSOR**, **BFILE**, or **LOB** data types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb8f-249">Viz také</span><span class="sxs-lookup"><span data-stu-id="acb8f-249">See Also</span></span>  
 [<span data-ttu-id="acb8f-250">Oracle a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="acb8f-250">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="acb8f-251">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="acb8f-251">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)