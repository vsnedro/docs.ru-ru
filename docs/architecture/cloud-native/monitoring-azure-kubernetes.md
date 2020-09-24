---
title: Мониторинг в Службах Azure Kubernetes
description: Мониторинг в Службах Azure Kubernetes
ms.date: 05/13/2020
ms.openlocfilehash: 3900f169b9be4f807e72392da38a1224d6ce28e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163704"
---
# <a name="monitoring-in-azure-kubernetes-services"></a>Мониторинг в Службах Azure Kubernetes

Встроенным ведением журнала в Kubernetes является примитив. Однако существуют некоторые отличные варианты извлечения журналов из Kubernetes и в место, где их можно анализировать надлежащим образом. Если вам нужно отслеживать кластеры AKS, Настройка эластичного стека для Kubernetes является отличным решением.

## <a name="azure-monitor-for-containers"></a>Azure Monitor для контейнеров

[Azure Monitor для контейнеров](/azure/azure-monitor/insights/container-insights-overview) поддерживает использование журналов не только из Kubernetes, но и из других механизмов оркестрации, таких как DC/OS, Docker Swarm и Red Hat OpenShift.

![Использование журналов из различных контейнеров ](./media/containers-diagram.png)
 **рис. 7-10**. Использование журналов из различных контейнеров

[Prometheus](https://prometheus.io/) — это популярное решение для мониторинга метрик с открытым исходным кодом. Она является частью облачной среды вычислений для машинного кода. Как правило, для использования Prometheus требуется управление сервером Prometheus с собственным хранилищем. Однако [Azure Monitor для контейнеров обеспечивает прямую интеграцию с конечными точками метрик Prometheus](/azure/azure-monitor/insights/container-insights-prometheus-integration), поэтому отдельный сервер не требуется.

Сведения о журналах и метриках собираются не только из контейнеров, запущенных в кластере, но и с самих узлов кластера. Это позволяет сопоставлять данные журнала из двух способов, что значительно упрощает отслеживание ошибки.

Установка регистраторов различается в кластерах [Windows](/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) и [Linux](/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) . Но в обоих случаях сбор журналов реализуется как набор [управляющих](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)программ Kubernetes, что означает, что сборщик журналов выполняется как контейнер на каждом узле.

Независимо от того, в какой Orchestrator или операционной системе работает управляющая программа Azure Monitor, данные журнала перенаправляются в те же Azure Monitor средства, с которыми пользователи знакомы. Это обеспечивает параллельное взаимодействие в средах, в которых сочетаются различные источники журналов, такие как гибридная среда Kubernetes/функции Azure.

![Пример панели мониторинга, в которой показаны данные журнала и метрики из нескольких работающих контейнеров. ](./media/containers-dashboard.png)
 **Рис. 7-11**. Пример панели мониторинга, в которой показаны данные журнала и метрики из нескольких работающих контейнеров.

## <a name="logfinalize"></a>Log. Finalize ()

Ведение журнала является одним из наиболее подвернутых и, однако, наиболее важных частей развертывания любого приложения в масштабе. По мере увеличения размера и сложности приложений это усложняет их отладку. Наличие высококачественных журналов значительно упрощает отладку и перемещает их из области "почти невозможной" в "приятный".

>[!div class="step-by-step"]
>[Назад](logging-with-elastic-stack.md)
>[Вперед](azure-monitor.md)
