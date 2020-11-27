---
title: Подделка
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: c2b0cae1dc57fac486122ca17fc8109ffe62f77d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249804"
---
# <a name="tampering"></a>Подделка

*Незаконное* изменение — это процесс изменения сообщения или доставки сообщения, а также использование измененного сообщения для назначения, отличного от того, для чего оно предназначено.  
  
## <a name="do-not-disable-ws-addressing"></a>Не отключайте WS-Addressing  

 Спецификация WS-Addressing расставляет заголовки адресов на каждом сообщении, по которым получатель сообщения проверяет отправителя сообщения. Чтобы отключить эту возможность, необходимо задать для свойства <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Если для режима безопасности задано значение Message и WS-Addressing отключена, злоумышленник сможет отправить запрос клиента другой службе, при этом вторая служба не сможет определить, что сообщение поступило от исходного клиента. Фактически, первая служба при взаимодействии со второй может выдавать себя за клиента.  
  
 Во избежание этого никогда не задавайте свойству <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> и старайтесь не использовать <xref:System.ServiceModel.Channels.MessageVersion>, например статическое свойство <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>, задающее свойству <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## <a name="see-also"></a>См. также

- [Вопросы безопасности](security-considerations-in-wcf.md)
- [Раскрытие информации](information-disclosure.md)
- [Несанкционированное получение привилегий](elevation-of-privilege.md)
- [Отказ в обслуживании](denial-of-service.md)
- [Неподдерживаемые сценарии](unsupported-scenarios.md)
- [Атаки с повторением](replay-attacks.md)
