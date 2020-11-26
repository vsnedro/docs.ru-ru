---
title: Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 8f8baf345059c01b0fef3b61ef85556151269118
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246424"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений

Можно интегрировать существующие приложения очереди сообщений (MSMQ) с приложениями Windows Communication Foundation (WCF) с помощью привязки интеграции MSMQ для преобразования сообщений MSMQ в сообщения WCF и из них. Это позволяет вызывать приложения для приемника MSMQ из клиентов WCF, а также вызывать службы WCF из приложений отправителя MSMQ.  
  
 В этом разделе объясняется, как использовать <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> для связи в очереди между (1) клиентом WCF и службой приложений MSMQ, написанной с помощью System. Messaging и (2) клиента приложения MSMQ и службы WCF.  
  
 Полный пример, демонстрирующий вызов приложения-получателя MSMQ из клиента WCF, см. в разделе [Windows Communication Foundation к примеру очереди сообщений](../samples/wcf-to-message-queuing.md) .  
  
 Полный пример, демонстрирующий способ вызова службы WCF из клиента MSMQ, см. в статье [очередь сообщений для Windows Communication Foundation](../samples/message-queuing-to-wcf.md) образца.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Создание службы WCF, получающей сообщения от клиента MSMQ  
  
1. Определите интерфейс, определяющий контракт службы для службы WCF, которая получает сообщения в очереди от приложения отправителя MSMQ, как показано в следующем примере кода.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. Реализуйте интерфейс и примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу, как показано в следующем примере кода.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. Создайте файл конфигурации, задающий привязку <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  

4. Создайте экземпляр объекта <xref:System.ServiceModel.ServiceHost>, использующий настроенную привязку.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>Создание клиента WCF, передающего сообщения в принимающее приложение MSMQ  
  
1. Определите интерфейс, определяющий контракт службы для клиента WCF, который отправляет сообщения в очереди получателю MSMQ, как показано в следующем примере кода.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. Определите клиентский класс, используемый клиентом WCF для вызова получателя MSMQ.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. Создайте конфигурацию, которая задает использование привязки MsmqIntegrationBinding.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. Создайте экземпляр класса клиента и вызовите метод, определенный службой приема сообщений.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения об очередях](queues-overview.md)
- [Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ](../samples/wcf-to-message-queuing.md)
- [Установка системы очередей сообщений (MSMQ)](../samples/installing-message-queuing-msmq.md)
- [Передача сообщений из приложения MSMQ в приложение Windows Communication Foundation](../samples/message-queuing-to-wcf.md)
- [Безопасность сообщений при использовании очереди сообщений](../samples/message-security-over-message-queuing.md)
