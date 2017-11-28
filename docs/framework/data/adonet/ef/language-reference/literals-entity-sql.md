---
title: "Literály (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092ef693-6e5f-41b4-b868-5b9e82928abf
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 50edfb344177dbec8cff9609aeab56d1db762eb7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="literals-entity-sql"></a><span data-ttu-id="a114f-102">Literály (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="a114f-102">Literals (Entity SQL)</span></span>
<span data-ttu-id="a114f-103">Toto téma popisuje [!INCLUDE[esql](../../../../../../includes/esql-md.md)] podporu pro literály.</span><span class="sxs-lookup"><span data-stu-id="a114f-103">This topic describes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] support for literals.</span></span>  
  
## <a name="null"></a><span data-ttu-id="a114f-104">Null</span><span class="sxs-lookup"><span data-stu-id="a114f-104">Null</span></span>  
 <span data-ttu-id="a114f-105">Literál null se používá k reprezentování hodnota null pro libovolného typu.</span><span class="sxs-lookup"><span data-stu-id="a114f-105">The null literal is used to represent the value null for any type.</span></span> <span data-ttu-id="a114f-106">Literál null je kompatibilní s žádným typem.</span><span class="sxs-lookup"><span data-stu-id="a114f-106">A null literal is compatible with any type.</span></span>  
  
 <span data-ttu-id="a114f-107">Hodnotou Null lze vytvořit pomocí přetypování prostřednictvím literálu s hodnotou null.</span><span class="sxs-lookup"><span data-stu-id="a114f-107">Typed nulls can be created by a cast over a null literal.</span></span> <span data-ttu-id="a114f-108">Další informace najdete v tématu [PŘETYPOVÁNÍ](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a114f-108">For more information, see [CAST](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md).</span></span>  
  
 <span data-ttu-id="a114f-109">Pro pravidla o tom, kde volné plovoucí null literály lze použít, najdete v části [Null literály a odvození typu](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a114f-109">For rules about where free floating null literals can be used, see [Null Literals and Type Inference](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md).</span></span>  
  
## <a name="boolean"></a><span data-ttu-id="a114f-110">Boolean</span><span class="sxs-lookup"><span data-stu-id="a114f-110">Boolean</span></span>  
 <span data-ttu-id="a114f-111">Logická hodnota literály jsou reprezentované pomocí klíčová slova `true` a `false`.</span><span class="sxs-lookup"><span data-stu-id="a114f-111">Boolean literals are represented by the keywords `true` and `false`.</span></span>  
  
## <a name="integer"></a><span data-ttu-id="a114f-112">Integer</span><span class="sxs-lookup"><span data-stu-id="a114f-112">Integer</span></span>  
 <span data-ttu-id="a114f-113">Můžou být celé číslo literály typu <xref:System.Int32> nebo <xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="a114f-113">Integer literals can be of type <xref:System.Int32> or <xref:System.Int64>.</span></span> <span data-ttu-id="a114f-114"><xref:System.Int32> Literálu je řada číselné znaky.</span><span class="sxs-lookup"><span data-stu-id="a114f-114">An <xref:System.Int32> literal is a series of numeric characters.</span></span> <span data-ttu-id="a114f-115"><xref:System.Int64> Literálu je řadu znaky následované velká L.</span><span class="sxs-lookup"><span data-stu-id="a114f-115">An <xref:System.Int64> literal is series of numeric characters followed by an uppercase L.</span></span>  
  
## <a name="decimal"></a><span data-ttu-id="a114f-116">Desetinné číslo</span><span class="sxs-lookup"><span data-stu-id="a114f-116">Decimal</span></span>  
 <span data-ttu-id="a114f-117">Číslo s pevnou desetinnou čárkou (decimální) je řadu číselné znaky, tečky (.) a další řadu znaky následované velká písmena "M".</span><span class="sxs-lookup"><span data-stu-id="a114f-117">A fixed-point number (decimal) is a series of numeric characters, a dot (.) and another series of numeric characters followed by an uppercase "M".</span></span>  
  
## <a name="float-double"></a><span data-ttu-id="a114f-118">Float Double</span><span class="sxs-lookup"><span data-stu-id="a114f-118">Float, Double</span></span>  
 <span data-ttu-id="a114f-119">Číslo s plovoucí desetinnou Dvojitá přesnost je řada číselné znaky, tečky (.) a další řadu znaky pravděpodobně následuje exponentem.</span><span class="sxs-lookup"><span data-stu-id="a114f-119">A double-precision floating point number is a series of numeric characters, a dot (.) and another series of numeric characters possibly followed by an exponent.</span></span> <span data-ttu-id="a114f-120">Single přesnosti plovoucí číslo (nebo float) je Dvojitá přesnost plovoucí desetinnou čárkou bodu číslo syntaxe následuje f malá písmena.</span><span class="sxs-lookup"><span data-stu-id="a114f-120">A single-precisions floating point number (or float) is a double-precision floating point number syntax followed by the lowercase f.</span></span>  
  
## <a name="string"></a><span data-ttu-id="a114f-121">String</span><span class="sxs-lookup"><span data-stu-id="a114f-121">String</span></span>  
 <span data-ttu-id="a114f-122">Řetězec je posloupnost znaků uzavřít do uvozovek nahoře.</span><span class="sxs-lookup"><span data-stu-id="a114f-122">A string is a series of characters enclosed in quote marks.</span></span> <span data-ttu-id="a114f-123">Uvozovky může být buď oba single uvozovky (`'`) nebo obě dvojité uvozovky (").</span><span class="sxs-lookup"><span data-stu-id="a114f-123">Quotes can be either both single-quotes (`'`) or both double-quotes (").</span></span> <span data-ttu-id="a114f-124">Textové literály znak může být ve formátu Unicode nebo kódování Unicode.</span><span class="sxs-lookup"><span data-stu-id="a114f-124">Character string literals can be either Unicode or non-Unicode.</span></span> <span data-ttu-id="a114f-125">Deklarovat řetězec znaků literálu jako Unicode, předpony literál s velká písmena "N".</span><span class="sxs-lookup"><span data-stu-id="a114f-125">To declare a character string literal as Unicode, prefix the literal with an uppercase "N".</span></span> <span data-ttu-id="a114f-126">Výchozí hodnota je kódování Unicode znak textové literály.</span><span class="sxs-lookup"><span data-stu-id="a114f-126">The default is non-Unicode character string literals.</span></span> <span data-ttu-id="a114f-127">Může být žádné mezery mezi z N a řetězcovém literálu a z N musí být velkými písmeny.</span><span class="sxs-lookup"><span data-stu-id="a114f-127">There can be no spaces between the N and the string literal payload, and the N must be uppercase.</span></span>  
  
```  
'hello' -- non-Unicode character string literal  
N'hello' -- Unicode character string literal  
"x"  
N"This is a string!"  
'so is THIS'  
```  
  
## <a name="datetime"></a><span data-ttu-id="a114f-128">DateTime</span><span class="sxs-lookup"><span data-stu-id="a114f-128">DateTime</span></span>  
 <span data-ttu-id="a114f-129">Hodnota literálu datetime je nezávislý na národní prostředí a se skládá z část data a času část.</span><span class="sxs-lookup"><span data-stu-id="a114f-129">A datetime literal is independent of locale and is composed of a date part and a time part.</span></span> <span data-ttu-id="a114f-130">Datum a čas části jsou povinné a neexistují žádné výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="a114f-130">Both date and time parts are mandatory and there are no default values.</span></span>  
  
 <span data-ttu-id="a114f-131">Část data musí mít formát: `YYYY` - `MM` - `DD`, kde `YYYY` je hodnota čtyřmístné roku rozsahu 0001 až 9999, `MM` je od 1 do 12 měsíce a `DD` je den hodnotu, která je platná pro daný měsíc `MM`.</span><span class="sxs-lookup"><span data-stu-id="a114f-131">The date part must have the format: `YYYY`-`MM`-`DD`, where `YYYY` is a four digit year value between 0001 and 9999, `MM` is the month between 1 and 12 and `DD` is the day value that is valid for the given month `MM`.</span></span>  
  
 <span data-ttu-id="a114f-132">Časovou část musí mít formát: `HH`:`MM`[:`SS`[.fffffff]], kde `HH` je hodinu hodnota mezi 0 a 23, `MM` je minut hodnota mezi 0 a 59, `SS` je druhá hodnota mezi 0 a 59 a fffffff je zlomkové druhá hodnota mezi 0 a 9999999 tak.</span><span class="sxs-lookup"><span data-stu-id="a114f-132">The time part must have the format: `HH`:`MM`[:`SS`[.fffffff]], where `HH` is the hour value between 0 and 23, `MM` is the minute value between 0 and 59, `SS` is the second value between 0 and 59 and fffffff is the fractional second value between 0 and 9999999.</span></span> <span data-ttu-id="a114f-133">Všechny hodnoty rozsahy jsou inkluzivní.</span><span class="sxs-lookup"><span data-stu-id="a114f-133">All value ranges are inclusive.</span></span> <span data-ttu-id="a114f-134">Zlomky sekund jsou volitelné.</span><span class="sxs-lookup"><span data-stu-id="a114f-134">Fractional seconds are optional.</span></span> <span data-ttu-id="a114f-135">Sekund jsou volitelné, pokud jsou zadány zlomků sekund; v takovém případě se vyžadují sekund.</span><span class="sxs-lookup"><span data-stu-id="a114f-135">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="a114f-136">Pokud nejsou zadané sekund nebo zlomků sekund, použije se místo toho výchozí hodnota nula.</span><span class="sxs-lookup"><span data-stu-id="a114f-136">When seconds or fractional seconds are not specified, the default value of zero will be used instead.</span></span>  
  
 <span data-ttu-id="a114f-137">Může existovat libovolný počet mezery mezi symbol data a času a literálu datové části, ale žádné nové řádky.</span><span class="sxs-lookup"><span data-stu-id="a114f-137">There can be any number of spaces between the DATETIME symbol and the literal payload, but no new lines.</span></span>  
  
```  
DATETIME'2006-10-1 23:11'  
DATETIME'2006-12-25 01:01:00.0000000' -- same as DATETIME'2006-12-25 01:01'  
```  
  
## <a name="time"></a><span data-ttu-id="a114f-138">Čas</span><span class="sxs-lookup"><span data-stu-id="a114f-138">Time</span></span>  
 <span data-ttu-id="a114f-139">Časový literál je nezávislé na národní prostředí a složený z jenom část času.</span><span class="sxs-lookup"><span data-stu-id="a114f-139">A time literal is independent of locale and composed of a time part only.</span></span> <span data-ttu-id="a114f-140">Časovou část je povinná a neexistuje žádná výchozí hodnota.</span><span class="sxs-lookup"><span data-stu-id="a114f-140">The time part is mandatory and there is no default value.</span></span> <span data-ttu-id="a114f-141">Musí mít ve formátu hh: mm [: SS [.fffffff]], kde HH je hodina hodnotu mezi 0 a 23, MM je minut hodnotu mezi 0 a 59, SS je druhá hodnota mezi 0 a 59 a fffffff je druhý podílem hodnotu mezi 0 a 9999999 tak.</span><span class="sxs-lookup"><span data-stu-id="a114f-141">It must have the format HH:MM[:SS[.fffffff]], where HH is the hour value between 0 and 23, MM is the minute value between 0 and 59, SS is the second value between 0 and 59, and fffffff is the second fraction value between 0 and 9999999.</span></span> <span data-ttu-id="a114f-142">Všechny hodnoty rozsahy jsou inkluzivní.</span><span class="sxs-lookup"><span data-stu-id="a114f-142">All value ranges are inclusive.</span></span> <span data-ttu-id="a114f-143">Zlomky sekund jsou volitelné.</span><span class="sxs-lookup"><span data-stu-id="a114f-143">Fractional seconds are optional.</span></span> <span data-ttu-id="a114f-144">Sekund jsou volitelné, pokud jsou zadány zlomků sekund; v takovém případě se vyžadují sekund.</span><span class="sxs-lookup"><span data-stu-id="a114f-144">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="a114f-145">Při sekund nebo zlomků nejsou zadané, použije se místo toho výchozí hodnota nula.</span><span class="sxs-lookup"><span data-stu-id="a114f-145">When seconds or fractions are not specified, the default value of zero will be used instead.</span></span>  
  
 <span data-ttu-id="a114f-146">Může existovat libovolný počet mezery mezi symbol čas a literálu datové části, ale žádné nové řádky.</span><span class="sxs-lookup"><span data-stu-id="a114f-146">There can be any number of spaces between the TIME symbol and the literal payload, but no new lines.</span></span>  
  
```  
TIME‘23:11’  
TIME‘01:01:00.1234567’  
```  
  
## <a name="datetimeoffset"></a><span data-ttu-id="a114f-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a114f-147">DateTimeOffset</span></span>  
 <span data-ttu-id="a114f-148">Datetimeoffset literálu je nezávislé na národní prostředí a složený z část data, času součástí a posunutí část.</span><span class="sxs-lookup"><span data-stu-id="a114f-148">A datetimeoffset literal is independent of locale and composed of a date part, a time part, and an offset part.</span></span> <span data-ttu-id="a114f-149">Datum, čas a posunutí částí, které jsou povinné a neexistují žádné výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="a114f-149">All date, time, and offset parts are mandatory and there are no default values.</span></span> <span data-ttu-id="a114f-150">Datum část musí mít formát rrrr-MM-DD, kde je rrrr hodnotu roku čtyřmístné rozsahu 0001 až 9999, MM je od 1 do 12 měsíce a DD den hodnotu, která je platná pro daný měsíc.</span><span class="sxs-lookup"><span data-stu-id="a114f-150">The date part must have the format YYYY-MM-DD, where YYYY is a four digit year value between 0001 and 9999, MM is the month between 1 and 12, and DD is the day value that is valid for the given month.</span></span> <span data-ttu-id="a114f-151">Časovou část musí mít formát hh: mm [: SS [.fffffff]], kde HH jsou hodiny hodnota mezi 0 a 23, MM je minut hodnotu mezi 0 a 59, SS je druhá hodnota mezi 0 a 59 a fffffff je zlomkové druhá hodnota mezi 0 a 9999999 tak.</span><span class="sxs-lookup"><span data-stu-id="a114f-151">The time part must have the format HH:MM[:SS[.fffffff]], where HH is the hour value between 0 and 23, MM is the minute value between 0 and 59, SS is the second value between 0 and 59, and fffffff is the fractional second value between 0 and 9999999.</span></span> <span data-ttu-id="a114f-152">Všechny hodnoty rozsahy jsou inkluzivní.</span><span class="sxs-lookup"><span data-stu-id="a114f-152">All value ranges are inclusive.</span></span> <span data-ttu-id="a114f-153">Zlomky sekund jsou volitelné.</span><span class="sxs-lookup"><span data-stu-id="a114f-153">Fractional seconds are optional.</span></span> <span data-ttu-id="a114f-154">Sekund jsou volitelné, pokud jsou zadány zlomků sekund; v takovém případě se vyžadují sekund.</span><span class="sxs-lookup"><span data-stu-id="a114f-154">Seconds are optional unless fractional seconds are specified; in this case, seconds are required.</span></span> <span data-ttu-id="a114f-155">Při sekund nebo zlomků nejsou zadané, použije se místo toho výchozí hodnota nula.</span><span class="sxs-lookup"><span data-stu-id="a114f-155">When seconds or fractions are not specified, the default value of zero will be used instead.</span></span> <span data-ttu-id="a114f-156">Posunutí část musí mít formát {+ &#124;-} hh: mm, kde HH a MM mají stejný význam jako část času.</span><span class="sxs-lookup"><span data-stu-id="a114f-156">The offset part must have the format {+&#124;-}HH:MM, where HH and MM have the same meaning as in the time part.</span></span> <span data-ttu-id="a114f-157">Rozsah posun, ale musí být mezi-14: 00 a + 14:00</span><span class="sxs-lookup"><span data-stu-id="a114f-157">The range of the offset, however, must be between -14:00 and + 14:00</span></span>  
  
 <span data-ttu-id="a114f-158">Může existovat libovolný počet mezery mezi DATETIMEOFFSET symbol a literálu datové části, ale žádné nové řádky.</span><span class="sxs-lookup"><span data-stu-id="a114f-158">There can be any number of spaces between the DATETIMEOFFSET symbol and the literal payload, but no new lines.</span></span>  
  
```  
DATETIMEOFFSET‘2006-10-1 23:11 +02:00’  
DATETIMEOFFSET‘2006-12-25 01:01:00.0000000 -08:30’  
```  
  
> [!NOTE]
>  <span data-ttu-id="a114f-159">Platná hodnota literálu Entity SQL můžete spadal mimo podporované oblasti pro CLR nebo zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="a114f-159">A valid Entity SQL literal value can fall outside the supported ranges for CLR or the data source.</span></span> <span data-ttu-id="a114f-160">To může mít za následek výjimku</span><span class="sxs-lookup"><span data-stu-id="a114f-160">This might result in an exception</span></span>  
  
## <a name="binary"></a><span data-ttu-id="a114f-161">binární</span><span class="sxs-lookup"><span data-stu-id="a114f-161">Binary</span></span>  
 <span data-ttu-id="a114f-162">Binární řetězcový literál je sekvenci hexadecimálních číslic jednoduchých uvozovek a být následující klíčové slovo binární nebo symbol zástupce `X` nebo `x`.</span><span class="sxs-lookup"><span data-stu-id="a114f-162">A binary string literal is a sequence of hexadecimal digits delimited by single quotes following the keyword binary or the shortcut symbol `X` or `x`.</span></span> <span data-ttu-id="a114f-163">Symbol zástupce `X` malá a velká písmena.</span><span class="sxs-lookup"><span data-stu-id="a114f-163">The shortcut symbol `X` is case insensitive.</span></span> <span data-ttu-id="a114f-164">Počtu nula či více mezery mezi klíčové slovo `binary` a hodnota binárního řetězce.</span><span class="sxs-lookup"><span data-stu-id="a114f-164">A zero or more spaces are allowed between the keyword `binary` and the binary string value.</span></span>  
  
 <span data-ttu-id="a114f-165">Hexadecimální znaky jsou také malá a velká písmena.</span><span class="sxs-lookup"><span data-stu-id="a114f-165">Hexadecimal characters are also case insensitive.</span></span> <span data-ttu-id="a114f-166">Pokud je literál se skládá z lichý počet šestnáctkových číslic, literálové bude zarovnání na další i šestnáctková číslice pomocí prefixu literál s hexadecimální nulový počet číslic.</span><span class="sxs-lookup"><span data-stu-id="a114f-166">If the literal is composed of an odd number of hexadecimal digits, the literal will be aligned to the next even hexadecimal digit by prefixing the literal with a hexadecimal zero digit.</span></span> <span data-ttu-id="a114f-167">Neexistuje žádné formální omezení velikosti binárního řetězce.</span><span class="sxs-lookup"><span data-stu-id="a114f-167">There is no formal limit on the size of the binary string.</span></span>  
  
```  
Binary'00ffaabb'  
X'ABCabc'  
BINARY    '0f0f0f0F0F0F0F0F0F0F'  
X'' –- empty binary string  
```  
  
## <a name="guid"></a><span data-ttu-id="a114f-168">Identifikátor GUID</span><span class="sxs-lookup"><span data-stu-id="a114f-168">Guid</span></span>  
 <span data-ttu-id="a114f-169">A `GUID` literál představuje globálně jedinečný identifikátor.</span><span class="sxs-lookup"><span data-stu-id="a114f-169">A `GUID` literal represents a globally unique identifier.</span></span> <span data-ttu-id="a114f-170">Je posloupnost vytvořen tak klíčové slovo `GUID` následuje šestnáctkových číslic ve formátu známé jako *registru* formátu: 8-4-4-4-12 uzavřená do jednoduchých uvozovek.</span><span class="sxs-lookup"><span data-stu-id="a114f-170">It is a sequence formed by the keyword `GUID` followed by hexadecimal digits in the form known as *registry* format: 8-4-4-4-12 enclosed in single quotes.</span></span> <span data-ttu-id="a114f-171">Hexadecimální číslice jsou malá a velká písmena.</span><span class="sxs-lookup"><span data-stu-id="a114f-171">Hexadecimal digits are case insensitive.</span></span>  
  
 <span data-ttu-id="a114f-172">Může existovat libovolný počet mezery mezi GUID symbol a literálu datové části, ale žádné nové řádky.</span><span class="sxs-lookup"><span data-stu-id="a114f-172">There can be any number of spaces between the GUID symbol and the literal payload, but no new lines.</span></span>  
  
```  
Guid'1afc7f5c-ffa0-4741-81cf-f12eAAb822bf'  
GUID  '1AFC7F5C-FFA0-4741-81CF-F12EAAB822BF'  
```  
  
## <a name="see-also"></a><span data-ttu-id="a114f-173">Viz také</span><span class="sxs-lookup"><span data-stu-id="a114f-173">See Also</span></span>  
 [<span data-ttu-id="a114f-174">Přehled SQL entity</span><span class="sxs-lookup"><span data-stu-id="a114f-174">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)