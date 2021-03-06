---
title: Orchestrace mikroslužeb a vícekontejnerových aplikací pro vysokou škálovatelnost a dostupnost
description: Zjistěte, jak nasadit aplikaci pomocí služby Azure Kubernetes Service.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 82a1cf7f3cc367bfb8b8f67a130600815f2a21c4
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664962"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Nasazení do služby Azure Kubernetes Service (AKS)

Budete moct setkat s AKS pomocí upřednostňované klientské operační systémy, tady vám ukážeme, jak dělat s Microsoft Windows a vložené verzi ve Windows, Ubuntu Linux pomocí příkazů prostředí Bash.

Jsou požadavky, aby před použitím AKS:

- Linux nebo Mac vývojovém počítači
- Vývojovém počítači s Windows
  - Vývojářský režim povolen ve Windows
  - Subsystém Windows pro Linux
- Nainstalované v Azure CLI [Windows, Mac nebo Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)

> [!NOTE]
> Chcete-li si projít kompletní informace o:
>
> Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest>
>
> Subsystém Windows pro Linux: <https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>Vytvoření prostředí AKS v Azure

Existuje několik způsobů, jak vytvořit prostředí AKS. To lze provést pomocí příkazů rozhraní příkazového řádku Azure nebo pomocí webu Azure portal.

Tady si můžete projít některé příklady použití Azure CLI k vytvoření clusteru a na webu Azure portal zkontrolujte výsledky. Také musíte mít Kubectl a Dockeru ve vývojovém počítači.  

## <a name="create-the-aks-cluster"></a>Vytvoření clusteru AKS

Vytvoření clusteru AKS pomocí tohoto příkazu:

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

Po dokončení úlohy vytvoření se zobrazí AKS vytvořili na webu Azure Portal:

Skupina prostředků:

![Zobrazit v prohlížeči skupiny prostředků pro Azure AKS.](media/aks-resource-group-view.png)

**Obrázek 4-17**. Zobrazení skupiny prostředků pro AKS z Azure.

AKS cluster:

![Zobrazení prohlížeče s skupinu prostředků pro AKS.](media/aks-cluster-view.png)

**Obrázek 4 – 18**. AKS zobrazení z Azure.

Můžete také zobrazit uzel vytvořené pomocí `Azure-CLI` a `Kubectl`.

Nejprve získání přihlašovacích údajů:

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![Výstup z výše uvedeného příkazu konzoly: Sloučené "MsSampleK8Cluster jako aktuální kontext v /root/.kube/config.](media/get-credentials-command-result.png)

**Obrázek 4-19**. `aks get-credentials` výsledek příkazu.

A pak získávání uzly z Kubectl:

```console
kubectl get nodes
```

![Výstup uvedeného příkazu konzoly: Seznam uzlů se stavem, stáří (čas spuštění) a verze](media/kubectl-get-nodes-command-result.png)

**Obrázek 4-20**. `kubectl get nodes` výsledek příkazu.

>[!div class="step-by-step"]
>[Předchozí](orchestrate-high-scalability-availability.md)
>[další](docker-apps-development-environment.md)
