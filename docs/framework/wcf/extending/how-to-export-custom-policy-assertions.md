---
description: Дополнительные сведения см. в статье как экспортировать утверждения настраиваемой политики.
title: Практическое руководство. Экспорт проверочных утверждений пользовательской политики
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
ms.openlocfilehash: b49d5a88809039f59537d79f92e31711085e580a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668934"
---
# <a name="how-to-export-custom-policy-assertions"></a>Практическое руководство. Экспорт проверочных утверждений пользовательской политики

В утверждениях политики описываются возможности и требования конечной точки службы. Приложения-службы могут использовать проверочные утверждения пользовательской политики в метаданных службы для передачи конечной точки, привязки или информации о настройке контракта клиентскому приложению. Windows Communication Foundation (WCF) можно использовать для экспорта утверждений в выражениях политик, присоединенных в привязках WSDL, на конечных точках, операциях или сообщениях в зависимости от возможностей или требований, которые вы обмениваетесь.  
  
 Специальные проверочные утверждения политики экспортируются путем реализации интерфейса <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> на <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> и либо вставки элемента привязки непосредственно в привязку конечной точки службы, либо регистрации элемента привязки в файле конфигурации приложения. Реализация экспорта политики добавляет проверочное утверждение пользовательской политики как экземпляр <xref:System.Xml.XmlElement?displayProperty=nameWithType> в соответствующую коллекцию <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType> в контексте <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType>, переданный методу <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>.  
  
 Кроме этого, необходимо проверить свойство <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> класса <xref:System.ServiceModel.Description.WsdlExporter> и экспортировать вложенные выражения и политики и атрибуты инфраструктуры политики в соответствующее пространство имен в зависимости от указанной версии политики.  
  
 Сведения об импорте утверждений пользовательской политики см. в разделе <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> и [как импортировать утверждения пользовательской политики](how-to-import-custom-policy-assertions.md).  
  
### <a name="to-export-custom-policy-assertions"></a>Экспорт проверочных утверждений пользовательской политики  
  
1. Реализация интерфейса <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> в <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>. В следующем коде показана реализация проверочного утверждения пользовательской политики на уровне привязки.  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2. Элемент привязки вставляется в привязку конечной точки либо программно, либо при помощи файла конфигурации приложения. См. описанные ниже действия.  
  
### <a name="to-insert-a-binding-element-using-an-application-configuration-file"></a>Вставка элемента привязки при помощи файла конфигурации приложения  
  
1. Реализуйте <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> для элемента привязки проверочного утверждения пользовательской политики.  
  
2. Добавьте расширение элемента привязки в файл конфигурации с помощью [\<bindingElementExtensions>](../../configure-apps/file-schema/wcf/bindingelementextensions.md) элемента.  
  
3. Создайте специальную привязку с помощью <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.  
  
### <a name="to-insert-a-binding-element-programmatically"></a>Вставка элемента привязки программными средствами  
  
1. Создайте новый элемент <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> и добавьте его в <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.  
  
2. Добавьте пользовательскую привязку, описанную на шаге 1, в новую конечную точку и добавьте эту новую конечную точку службы в <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, вызвав метод <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
3. Откройте <xref:System.ServiceModel.ServiceHost>. В следующем коде показан пример создания специальной привязки и вставки элементов привязки программными средствами.  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.IPolicyImportExtension>
- <xref:System.ServiceModel.Description.IPolicyExportExtension>
- [Практическое руководство. Импорт проверочных утверждений пользовательской политики](how-to-import-custom-policy-assertions.md)
