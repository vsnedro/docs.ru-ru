---
title: Транспорты в Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 8623b788b848867f25836a657b07349dd50c2780
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251689"
---
# <a name="transports-in-windows-communication-foundation"></a>Транспорты в Windows Communication Foundation

Транспортный уровень является самым нижним уровнем стека каналов. Основными транспортами, используемыми в Windows Communication Foundation (WCF), являются HTTP, HTTPS, TCP и именованные каналы. В подразделах данного раздела рассматриваются выбор типа транспорта среди названных выше типов, настройка транспорта и задание свойств настройки.  
  
 В состав WCF входят дополнительные транспорты. Дополнительные сведения о службе очередей сообщений (MSMQ) см. в статье [очереди и надежные сеансы](queues-and-reliable-sessions.md). Дополнительные сведения о одноранговом транспорте см. в разделе одноранговая [сеть](peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>в этом разделе  

 [Выбор транспортов](choosing-a-transport.md)  
 Описываются три основных типа транспорта и рассматриваются вопросы выбора транспорта.  
  
 [Выбор кодировщика сообщений](choosing-a-message-encoder.md)  
 Описываются факторы, которые необходимо принять во внимание при выборе элемента привязки для кодирования сообщений.  
  
 [Потоковая передача сообщений](streaming-message-transfer.md)  
 Описывается настройка транспортного уровня для выполнения потоковой передачи.  
  
 [Настройка HTTP и HTTPS](configuring-http-and-https.md)  
 Описывается настройка элементов привязки транспорта HTTP и HTTPS.  
  
 [Практическое руководство. Как заменить URL-резервирование WCF на ограниченное резервирование](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Описывает, как использовать ограниченные резервирования ВКФУРЛ.  
  
 [Квоты транспорта](transport-quotas.md)  
 Рассматриваются вопросы задания квот, доступных на транспортном уровне.  
  
 [Работа со средствами NAT и брандмауэрами](working-with-nats-and-firewalls.md)  
 Описывается настройка транспортного уровня при отправке или получении сообщений за брандмауэром или при использовании преобразования сетевых адресов (NAT).  
  
 [Совместное использование портов Net.TCP](net-tcp-port-sharing.md)  
 Описывает, как использовать компонент совместного использования портов net. TCP в WCF.  
  
## <a name="reference"></a>Справочник  

 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Связанные разделы  

 [Привязки](bindings.md)  
  
 [Расширение привязок](../extending/extending-bindings.md)
