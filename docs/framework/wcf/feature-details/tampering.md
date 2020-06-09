---
title: незаконное изменение;
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: e618ab369a46d403aa8db26c4b472e2be3634785
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600715"
---
# <a name="tampering"></a>незаконное изменение;
*Незаконное* изменение — это процесс изменения сообщения или доставки сообщения, а также использование измененного сообщения для назначения, отличного от того, для чего оно предназначено.  
  
## <a name="do-not-disable-ws-addressing"></a>Не отключайте WS-Addressing  
 Спецификация WS-Addressing расставляет заголовки адресов на каждом сообщении, по которым получатель сообщения проверяет отправителя сообщения. Чтобы отключить эту возможность, необходимо задать для свойства <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Если для режима безопасности задано значение Message и WS-Addressing отключена, злоумышленник сможет отправить запрос клиента другой службе, при этом вторая служба не сможет определить, что сообщение поступило от исходного клиента. Фактически, первая служба при взаимодействии со второй может выдавать себя за клиента.  
  
 Во избежание этого никогда не задавайте свойству <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> и старайтесь не использовать <xref:System.ServiceModel.Channels.MessageVersion>, например статическое свойство <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>, задающее свойству <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## <a name="see-also"></a>Дополнительно

- [Вопросы безопасности](security-considerations-in-wcf.md)
- [Раскрытие информации](information-disclosure.md)
- [Повышение привилегий](elevation-of-privilege.md)
- [Отказ в обслуживании](denial-of-service.md)
- [Неподдерживаемые сценарии](unsupported-scenarios.md)
- [Атаки с повторением](replay-attacks.md)
