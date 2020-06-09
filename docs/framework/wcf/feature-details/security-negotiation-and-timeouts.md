---
title: Согласование безопасности и тайм-ауты
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 1b5fb15b4ea00ba33b741c96bcb423aefe9890fa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601001"
---
# <a name="security-negotiation-and-timeouts"></a>Согласование безопасности и тайм-ауты
При проверке подлинности клиентов и служб Windows Communication Foundation (WCF) поддерживает режим, в котором учетные данные службы согласовываются как часть проверки подлинности. В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту. Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>. Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла "запрос-ответ". Если согласование завершается за один цикл, время ожидания не используется.  
  
## <a name="see-also"></a>Дополнительно

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Практическое руководство. Установка максимальной разницы в показаниях часов](how-to-set-a-max-clock-skew.md)
