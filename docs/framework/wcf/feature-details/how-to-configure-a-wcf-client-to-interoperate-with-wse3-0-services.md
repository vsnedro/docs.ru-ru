---
description: См. Дополнительные сведения о настройке клиента WCF для взаимодействия со службами WSE 3.0.
title: Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 97de90c491a29cdacf881a92013a11db6aea416f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780132"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a>Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0

Клиенты Windows Communication Foundation (WCF) совместимы с расширениями веб-служб 3,0 для служб Microsoft .NET (WSE), когда клиенты WCF настроены для использования спецификации WS-Addressing в августе 2004.  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a>Настройка клиента WCF для взаимодействия с веб-службой WSE 3.0  
  
1. Запустите [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать клиент WCF для веб-службы WSE 3,0.  
  
     Для веб-службы WSE создается клиентский класс WCF.  
  
     Дополнительные сведения о создании клиента WCF см. в разделе [инструкции. Создание клиента](../how-to-create-a-wcf-client.md).  
  
2. Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.  
  
     Следующий класс является частью примера [взаимодействия с WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) .  
  
    1. Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. Добавьте в класс свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, и параметры защиты сообщений.  
  
         В следующем примере кода определяются `SecurityAssertion` `RequireDerivedKeys` свойства,, `EstablishSecurityContext` и `MessageProtectionOrder` . Они указывают на использование утверждений WSE, являются ли производные ключи обязательными, используются ли безопасные сеансы, требуются ли подтверждения подписей и параметры защиты сообщений соответственно.  
  
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

 В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0. Пользовательская привязка, которая называется `WseHttpBinding` , затем используется для указания свойств привязки для клиента WCF.  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.Binding>
- [Взаимодействие с WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))
