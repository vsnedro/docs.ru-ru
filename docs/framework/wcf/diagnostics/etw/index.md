---
title: Аналитическое отслеживание ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 4bb31eeac7c5d3c8c30f66090b07de9f8af4d5a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274625"
---
# <a name="analytic-tracing-with-etw"></a>Аналитическое отслеживание ETW

Аналитическая трассировка Windows Communication Foundation (WCF) предоставляет способ сбора диагностических сведений во время выполнения службы WCF. События аналитической трассировки WCF создаются в ключевых точках стека WCF, чтобы разрешить устранение неполадок служб WCF в рабочей среде. Аналитическая трассировка служб WCF оказывает минимальное влияние на производительность сервера продукта, на котором размещены [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] службы WCF, так как эти события очень эффективны в сеансе трассировки событий для Windows (ETW).  
  
## <a name="in-this-section"></a>в этом разделе  

 [Общие сведения об аналитическом отслеживании](analytic-tracing-overview.md)  
 Описывает, как работает аналитическая трассировка WCF [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] .  
  
 [Динамическое включение аналитического отслеживания](dynamically-enabling-analytic-tracing.md)  
 Описывает, как динамически включить и отключить трассировку с помощью ETW.  
  
 [Настройка отслеживания потока сообщений](configuring-message-flow-tracing.md)  
 Описывает процесс настройки трассировки потока сообщений.  
  
 [Ссылка на событие аналитического отслеживания](analytic-trace-event-reference.md)  
 Содержит таблицу идентификаторов событий с уровнями событий, сообщениями событий и ключевыми словами.  
  
## <a name="see-also"></a>См. также

- [Службы WCF и средство отслеживания событий для Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [Отслеживание событий в системе трассировки событий Windows](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
