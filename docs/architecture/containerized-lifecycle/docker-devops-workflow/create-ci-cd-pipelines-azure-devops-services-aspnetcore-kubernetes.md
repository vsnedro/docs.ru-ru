---
title: Создание конвейеров CI/CD в службах Azure DevOps для приложения .NET в контейнерах и развертывание в кластер Kubernetes
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.date: 01/06/2021
ms.openlocfilehash: ef994f132716547ee402237016ee71013528d779
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970490"
---
# <a name="create-cicd-pipelines-in-azure-devops-services-for-a-net-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Создание конвейеров CI/CD в службах Azure DevOps для приложения .NET в контейнерах и развертывание в кластер Kubernetes

На рисунке 5-12 показан комплексный сценарий DevOps, охватывающий управление кодом, компиляцию кода, создание образов Docker, отправку образы Docker в реестр Docker и, наконец, развертывание в кластере Kubernetes в Azure.

![Рабочий процесс: начинается с компьютера разработки. Отправка в репозиторий начинает задачу сборки/непрерывной интеграции (CI) с помощью пользовательского образа, который отправляется в реестр Docker, а затем используется задачей непрерывного развертывания (CD)/развертывания, после чего выполняется отправка в AKS.](media/docker-workflow-ci-cd-aks.png)

**Рис. 5-12**. Сценарии CI/CD для создания образов Docker и развертывания в кластере Kubernetes в Azure

Важно отметить, что два конвейера — сборки/CI и выпуска/CD — подключены через реестр Docker (например, Docker Hub или Реестр контейнеров Azure). Реестр Docker является одним из основных отличий по сравнению с традиционным процессом CI/CD без Docker.

Как показано на рисунке 5-13, первым этапом является конвейер сборки/CI. В Azure DevOps Services можно создать конвейеры сборки/CI, которые будут компилировать код, создавать образы Docker и отправлять их в реестр Docker, например Docker Hub или Реестр контейнеров Azure.

![Браузерное представление Azure DevOps с определением задачи создания процесса.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**Рис. 5-13**. Конвейер сборки/CI в Azure DevOps, создающий образы Docker и отправляющий их в реестр Docker

Второй этап заключается в создании конвейера развертывания/выпуска. В Azure DevOps Services можно легко создать конвейер развертывания, ориентированный на кластер Kubernetes, с помощью задач Kubernetes для Azure DevOps Services, как показано на рисунке 5-14.

![Браузерное представление Azure DevOps с определением задачи развертывания в Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**Рис. 5-14**. Конвейер выпуска/CD в Azure DevOps Services, осуществляющий развертывание в кластере Kubernetes

> [!Пошаговое руководство] Развертывание eShopModernized в Kubernetes:
>
> Подробное пошаговое руководство для конвейеров CI/CD Azure DevOps, осуществляющих развертывание в Kubernetes, см. в этой записи: \
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
>[Назад](docker-application-outer-loop-devops-workflow.md)
>[Вперед](../run-manage-monitor-docker-environments/index.md)
