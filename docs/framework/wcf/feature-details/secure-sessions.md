---
title: Безопасные сеансы
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: fd8406af0c37981b2ddc7ab8ddb0c82c63cbc0b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288557"
---
# <a name="secure-sessions"></a>Безопасные сеансы

Компонент Windows Communication Foundation (WCF) — это надежные сеансы, которые гарантируют получение сообщений в том порядке, в котором они были отправлены. В этом разделе рассматриваются проблемы безопасности, которые необходимо учитывать при создании надежного сеанса. Дополнительные сведения о надежных сеансах см. [в разделе Использование сеансов](../using-sessions.md).  
  
> [!NOTE]
> Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера контекста безопасности с отслеживанием состояния (SCT). При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>. Дополнительные сведения см. в разделе [неподдерживаемые сценарии](unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>в этом разделе  
  
|||  
|-|-|  
|[Безопасные диалоги и безопасные сеансы](secure-conversations-and-secure-sessions.md)|Безопасные диалоги и безопасные сеансы - это синонимы. В этом разделе рассматривается, как работает безопасный диалог, а также когда и почему следует использовать шаблон.|  
|[Практическое руководство. Создание сеанса безопасности](how-to-create-a-secure-session.md)|Пошаговое руководство по основным этапам создания безопасного сеанса.|  
|[Практическое руководство. Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса](how-to-create-a-security-context-token-for-a-secure-session.md)|Пошаговое руководство по созданию веб-фермы, которая будет поддерживать состояние и сеансы с клиентами.|  
|[Соображения о защите безопасных сеансов](security-considerations-for-secure-sessions.md)|Описание некоторых особенностей безопасных сеансов.|  
  
## <a name="reference"></a>Справочник  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Связанные разделы  

 [Сеансы, экземпляры и параллелизм](sessions-instancing-and-concurrency.md)  
  
 [Проектирование и реализация служб](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Включение обнаружения повтора сообщений](how-to-enable-message-replay-detection.md)
- [Атаки с повторением](replay-attacks.md)
- [Практическое руководство. Создание службы, для которой требуются сеансы](how-to-create-a-service-that-requires-sessions.md)
