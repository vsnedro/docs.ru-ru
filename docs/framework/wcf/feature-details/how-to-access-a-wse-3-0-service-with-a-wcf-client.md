---
title: Практическое руководство. Обращение к службе WSE 3.0 с помощью клиента WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 847146c2025612689f0d69cc0c23d2be14018c0f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556841"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Практическое руководство. Обращение к службе WSE 3.0 с помощью клиента WCF
Клиенты Windows Communication Foundation (WCF) совместимы с расширениями веб-служб (WSE) 3,0 для служб Microsoft .NET, когда клиенты WCF настроены для использования версии WS-Addressing в августе 2004. Однако службы WSE 3,0 не поддерживают протокол обмена метаданными (MEX), поэтому при использовании [средства служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для создания клиентского класса WCF параметры безопасности не применяются к созданному клиенту WCF. Поэтому необходимо указать параметры безопасности, которые требуются службе WSE 3,0 после создания клиента WCF.  
  
 Эти параметры безопасности можно применить с помощью пользовательской привязки, чтобы учитывать требования службы WSE 3,0 и требования взаимодействия между службой WSE 3,0 и клиентом WCF. Требования в отношении взаимодействия включают использование упомянутой выше спецификации WS-Addressing от августа 2004 г. и предусмотренной в WSE 3.0 защиты сообщений по умолчанию с помощью поля <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. Защита сообщений по умолчанию для WCF — <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature> . В этом разделе подробно описано, как создать привязку WCF, взаимодействующую со службой WSE 3,0. WCF также предоставляет пример, включающий эту привязку. Дополнительные сведения об этом примере см. в разделе [взаимодействие с веб-СЛУЖБАМИ ASMX](../samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>Обращение к веб-службе WSE 3.0 с помощью клиента WCF  
  
1. Запустите [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать клиент WCF для веб-службы WSE 3,0.  
  
     Для веб-службы WSE 3,0 создается клиент WCF. Поскольку WSE 3.0 не поддерживает протокол MEX, использовать SvcUtil.exe для извлечения требований безопасности для веб-службы нельзя. Добавить параметры безопасности для клиента должен разработчик приложения.  
  
     Дополнительные сведения о создании клиента WCF см. в разделе [как создать клиент](../how-to-create-a-wcf-client.md).  
  
2. Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.  
  
     Следующий класс является частью [взаимодействия с примером с использованием WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) :  
  
    1. Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. Добавьте в класс свойства, задающие готовое к использованию утверждение WSE (используемое службой WSE), указывающие, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, а также задающие параметры защиты сообщений. В WSE 3,0 проверочное утверждение Указывает требования безопасности для клиента или веб-службы, аналогичные режиму проверки подлинности привязки в WCF.  
  
         В следующем примере кода определяются свойства `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` и `MessageProtectionOrder`, которые задают готовое к использованию утверждение WSE, указывают, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение сигнатур, и задают параметры защиты сообщений соответственно.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.  
  
         В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. В коде клиентского приложения добавьте код для задания свойств привязки.  
  
     В следующем примере кода указывается, что клиент WCF должен использовать защиту и проверку подлинности сообщений, как определено в утверждении безопасности для использования WSE 3,0 `AnonymousForCertificate` . Кроме того, требуются безопасные сеансы и производные ключи.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0. Эта пользовательская привязка, которая называется `WseHttpBinding` , затем используется для указания свойств привязки для клиента WCF, который взаимодействует с примером краткого руководства по ВССЕКУРИТЯНОНИМАУС WSE 3,0.  

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.Binding>
- [Взаимодействие с WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))
