---
title: Управление микрослужбами и многоконтейнерными приложениями для обеспечения высокого уровня масштабируемости и доступности
description: Сведения о развертывании приложения с помощью службы Azure Kubernetes.
ms.date: 08/06/2020
ms.openlocfilehash: ba9887c0a4837c16a60ebeb006416c0fa8c105e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163600"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>Развертывание в службе Azure Kubernetes (AKS)

Вы можете взаимодействовать с AKS, используя предпочитаемую клиентскую операционную систему (Windows, macOS или Linux) с установленным интерфейсом командной строки Azure (Azure CLI). Дополнительные сведения см. в разделах [Документация по Azure CLI](/cli/azure/?view=azure-cli-latest) и [Руководство по установке](/cli/azure/install-azure-cli?view=azure-cli-latest) для доступных сред.

## <a name="create-the-aks-environment-in-azure"></a>Создание среды AKS в Azure

Создать среду AKS можно несколькими способами. Это можно сделать с помощью команд Azure CLI или портала Azure.

Здесь можно ознакомиться с рядом примеров использования Azure CLI для создания кластера и просмотра результатов на портале Azure. На компьютере разработки также должны быть установлены Kubectl и Docker.

## <a name="create-the-aks-cluster"></a>Создание кластера AKS

Создайте кластер AKS с помощью этой команды (должна существовать группа ресурсов):

```console
az aks create --resource-group explore-docker-aks-rg --name explore-docker-aks --node-vm-size Standard_B2s --node-count 1 --generate-ssh-keys --location westeurope
```

> [!NOTE]
> Значений параметров `--node-vm-size` и `--node-count` достаточно для примера приложения или приложения-разработчика.

По завершении задания по созданию отобразится следующее:

- Кластер AKS, созданный в начальной группе ресурсов
- Новая связанная группа ресурсов, содержащая ресурсы, связанные с кластером AKS, как показано на следующих изображениях.

Исходная группа ресурсов с кластером AKS:

![Группа ресурсов AKS в браузере.](media/deploy-azure-kubernetes-service/aks-cluster-view.png)

**Рис. 4-17**. Группа ресурсов AKS в Azure.

Группа ресурсов кластера AKS:

![Группа ресурсов Azure AKS в браузере.](media/deploy-azure-kubernetes-service/aks-resource-group-view.png)

**Рис. 4-18**. Служба AKS в Azure.

> [!IMPORTANT]
> Как правило, изменять ресурсы в группе ресурсов кластера AKS не требуется. Например, при удалении кластера AKS также удаляется и группа ресурсов.

Созданный узел можно также просмотреть с помощью `Azure CLI` и `Kubectl`.

Сначала получите учетные данные:

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Выходные данные указанной выше команды в консоли: Объединено "explore-docker-aks" в качестве текущего контекста в /home/miguel/.kube/config.](media/deploy-azure-kubernetes-service/get-credentials-command-result.png)

**Рис. 4-19**. Результат команды `aks get-credentials`.

Затем получите узлы из Kubectl:

```console
kubectl get nodes
```

![Выходные данные указанной выше команды в консоли: Список узлов с состоянием, возрастом (временем выполнения) и версией](media/deploy-azure-kubernetes-service/kubectl-get-nodes-command-result.png)

**Рис. 4-20**. Результат команды `kubectl get nodes`.

> [!div class="step-by-step"]
> [Назад](orchestrate-high-scalability-availability.md)
> [Вперед](docker-apps-development-environment.md)
