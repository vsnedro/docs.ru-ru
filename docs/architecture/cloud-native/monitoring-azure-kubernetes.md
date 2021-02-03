---
title: Мониторинг в Службах Azure Kubernetes
description: Мониторинг в Службах Azure Kubernetes
ms.date: 01/19/2021
ms.openlocfilehash: d044337150edddac9e24218ccaeaace1f413e654
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506036"
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

Независимо от того, в какой Orchestrator или операционной системе работает управляющая программа Azure Monitor, данные журнала перенаправляются в те же Azure Monitor средства, с которыми пользователи знакомы. Такой подход обеспечивает параллельное взаимодействие в средах, в которых сочетаются различные источники журналов, например гибридная среда Kubernetes/функции Azure.

![Пример панели мониторинга, в которой показаны данные журнала и метрики из нескольких работающих контейнеров. ](./media/containers-dashboard.png)
 **Рис. 7-11**. Пример панели мониторинга, в которой показаны журналы и сведения о метриках из многих работающих контейнеров.

## <a name="logfinalize"></a>Log. Finalize ()

Ведение журнала является одним из наиболее подвернутых и, однако, наиболее важных частей развертывания любого приложения в масштабе. По мере увеличения размера и сложности приложений это усложняет их отладку. Наличие высококачественных журналов значительно упрощает отладку и перемещает их из области "почти невозможной" в "приятный".

>[!div class="step-by-step"]
>[Назад](logging-with-elastic-stack.md)
>[Вперед](azure-monitor.md)
