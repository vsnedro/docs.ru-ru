---
description: 'Дополнительные сведения: согласование безопасности и время ожидания'
title: Согласование безопасности и тайм-ауты
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 50055698f9a9946d0c0110a964cf9ce5b9f4fa28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632442"
---
# <a name="security-negotiation-and-timeouts"></a>Согласование безопасности и тайм-ауты

При проверке подлинности клиентов и служб Windows Communication Foundation (WCF) поддерживает режим, в котором учетные данные службы согласовываются как часть проверки подлинности. В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту. Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>. Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла "запрос-ответ". Если согласование завершается за один цикл, время ожидания не используется.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Практическое руководство. Установка максимальной разницы в показаниях часов](how-to-set-a-max-clock-skew.md)
