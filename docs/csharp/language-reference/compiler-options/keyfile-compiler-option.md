---
title: "-keyfile (možnosti kompilátoru C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d120b325f433108cd1b01dd1c25d2a0e55da401b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="keyfile-c-compiler-options"></a><span data-ttu-id="f9016-102">/keyfile (Možnosti kompilátoru C#)</span><span class="sxs-lookup"><span data-stu-id="f9016-102">/keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="f9016-103">Určuje název souboru obsahujícího kryptografický klíč.</span><span class="sxs-lookup"><span data-stu-id="f9016-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9016-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f9016-104">Syntax</span></span>  
  
```console  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9016-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="f9016-105">Arguments</span></span>  
  
|<span data-ttu-id="f9016-106">Termín</span><span class="sxs-lookup"><span data-stu-id="f9016-106">Term</span></span>|<span data-ttu-id="f9016-107">Definice</span><span class="sxs-lookup"><span data-stu-id="f9016-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="f9016-108">Název souboru, který obsahuje složitý název klíče.</span><span class="sxs-lookup"><span data-stu-id="f9016-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9016-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f9016-109">Remarks</span></span>  
 <span data-ttu-id="f9016-110">Pokud tato možnost se používá, kompilátor vloží veřejný klíč ze zadaného souboru do manifestu a následně podepíše konečné sestavení s privátním klíčem.</span><span class="sxs-lookup"><span data-stu-id="f9016-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="f9016-111">Chcete-li vygenerovat soubor klíče, zadejte sn -k `file` na příkazovém řádku.</span><span class="sxs-lookup"><span data-stu-id="f9016-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="f9016-112">Pokud je kompilovat s **/target: Module**, název souboru klíče je udržován v modulu a součástí sestavení, které se vytvoří při kompilaci sestavení s [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f9016-112">If you compile with **/target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="f9016-113">Vaše informace šifrování můžete předat také kompilátoru s [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f9016-113">You can also pass your encryption information to the compiler with [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span> <span data-ttu-id="f9016-114">Použití [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) Pokud chcete, aby částečně podepsané sestavení.</span><span class="sxs-lookup"><span data-stu-id="f9016-114">Use [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="f9016-115">V případě, že/keyfile i/keycontainer zadávají ve stejné kompilaci (pomocí parametru příkazového řádku nebo ve vlastních atributů), kompilátor se nejdřív pokusí použít kontejner klíčů.</span><span class="sxs-lookup"><span data-stu-id="f9016-115">In case both /keyfile and /keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="f9016-116">Pokud tato operace úspěšná, je podepsaný sestavení s informacemi v kontejneru klíčů.</span><span class="sxs-lookup"><span data-stu-id="f9016-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="f9016-117">Pokud kompilátor nenajde kontejner klíčů, pokusí se/keyfile zadaný soubor.</span><span class="sxs-lookup"><span data-stu-id="f9016-117">If the compiler does not find the key container, it will try the file specified with /keyfile.</span></span> <span data-ttu-id="f9016-118">Pokud tato operace úspěšná, sestavení je podepsaná pomocí informací v souboru klíče a informace o klíči budou nainstalováni v kontejneru klíčů (podobné sn -i), aby na další kompilace kontejner klíče budou platné.</span><span class="sxs-lookup"><span data-stu-id="f9016-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="f9016-119">Všimněte si, že soubor klíče může obsahovat pouze veřejný klíč.</span><span class="sxs-lookup"><span data-stu-id="f9016-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="f9016-120">Další informace najdete v tématu [vytvoření a použití sestavení](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) a [zpoždění podepsání sestavení](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="f9016-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f9016-121">Nastavení tohoto parametru kompilátoru ve vývojovém prostředí Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9016-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="f9016-122">Otevřete **vlastnosti** stránky pro projekt.</span><span class="sxs-lookup"><span data-stu-id="f9016-122">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="f9016-123">Klikněte **podpisování** stránku vlastností.</span><span class="sxs-lookup"><span data-stu-id="f9016-123">Click the **Signing** property page.</span></span>  
  
3.  <span data-ttu-id="f9016-124">Změnit **vyberte soubor klíče se silným názvem** vlastnost.</span><span class="sxs-lookup"><span data-stu-id="f9016-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="f9016-125">Prostřednictvím kódu programu přístup k této možnosti kompilátoru s <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9016-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9016-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="f9016-126">See Also</span></span>  
 [<span data-ttu-id="f9016-127">Možnosti kompilátoru C#</span><span class="sxs-lookup"><span data-stu-id="f9016-127">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="f9016-128">Správa vlastností projektů a řešení</span><span class="sxs-lookup"><span data-stu-id="f9016-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)