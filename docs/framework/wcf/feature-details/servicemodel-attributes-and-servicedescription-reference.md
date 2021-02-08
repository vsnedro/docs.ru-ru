---
description: 'Дополнительные сведения о: атрибуты ServiceModel и ссылка ServiceDescription'
title: Атрибуты ServiceModel и справочная информация ServiceDescription
ms.date: 03/30/2017
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
ms.openlocfilehash: 52d800d1aab7fc7d60f0b1234065aa876944ea3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793510"
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a>Атрибуты ServiceModel и справочная информация ServiceDescription

*Дерево описания* — это иерархия типов (начиная с <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> класса), которые вместе описывают каждый аспект службы. Windows Communication Foundation (WCF) использует дерево описания для создания допустимой среды выполнения службы, публикации языка описания веб-служб (WSDL), языка определения схемы XML (XSD) и утверждений политики (метаданных) о службе, которую клиенты могут использовать для подключения к службе и ее использования, а также для создания различных представлений кода и файлов конфигурации для значений дерева описания.  
  
 В этом разделе описывается получение свойств, относящихся к контракту, из контракта службы, а также их реализация и добавление в дерево описания. В некоторых случаях значения атрибутов преобразуются в свойства поведения, затем поведение вставляется в дерево описания. Дополнительные сведения о преобразовании значений дерева описания в метаданные см. в разделе [ServiceDescription и Справочник по WSDL](servicedescription-and-wsdl-reference.md).  
  
## <a name="mapping-operations-to-the-description-tree"></a>Сопоставление операций дереву описания  

 В приложениях WCF контракты служб моделируются по интерфейсам (или классам), которые используют атрибуты для пометки интерфейса или класса и его методов как группирования операций. При открытии класса <xref:System.ServiceModel.ServiceHost> все контракты и реализации службы отражаются и объединяются с информацией о конфигурации в дереве описания.  
  
 Существует два типа моделей операций: модель *параметров* и модель *контрактов сообщений* . В модели параметров используются управляемые методы, не имеющие типа параметра или возвращаемого значения, помеченного классом <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>. В этой модели разработчики управляют сериализацией параметров и возвращаемых значений, но WCF создает значения, которые используются для заполнения дерева описания для службы и ее контракта.  
  
 Привязки, указанные в файлах конфигурации, загружаются непосредственно в свойство <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType>.  
  
|Свойство ServiceBehaviorAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-------------------------------------|  
|Имя|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Задает свойство <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> для всех операций.|  
|MaxItemsInObjectGraph|Задает свойство <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> для всех операций.|  
  
|Свойство ServiceContractAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription>, добавленные к <xref:System.ServiceModel.Description.OperationDescription.Messages%2A> всех операций.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> и, возможно, дочерние уровни защиты. Дополнительные сведения об иерархии уровня защиты см. в разделе [Основные сведения о уровне защиты](../understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|Значение ServiceKnownTypesAttribute|Изменяемое значение дерева описания|  
|--------------------------------------|-------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|Значение OperationContractAttribute|Изменяемое значение дерева описания|  
|--------------------------------------|-------------------------------------|  
|Действие|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> для исходящего или входящего сообщения, в зависимости от контракта/контракта обратного вызова.|  
|AsyncPattern|Если имеет значение "True", <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> и <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Сопоставляется одному описанию <xref:System.ServiceModel.Description.MessageDescription> в <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|Имя|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> и, возможно, дочерние уровни защиты. Дополнительные сведения об иерархии уровня защиты см. в разделе [Основные сведения о уровне защиты](../understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> для исходящего или входящего сообщения, в зависимости от контракта/контракта обратного вызова.|  
  
|Значение FaultContractAttribute|Изменяемое значение дерева описания|  
|----------------------------------|-------------------------------------|  
|Действие|<xref:System.ServiceModel.Description.FaultDescription.Action%2A>, в зависимости от контракта/контракта обратного вызова.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|Имя|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|Значение DataContractFormatAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-------------------------------------|  
|Использовать|Задается значение <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> в <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> для операции.|  
  
|Значение XmlSerializerFormatAttribute|Изменяемое значение дерева описания|  
|----------------------------------------|-------------------------------------|  
|Стиль|Это свойство <xref:System.ServiceModel.XmlSerializerFormatAttribute> задается в <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> для операции.|  
|Использовать|<xref:System.ServiceModel.XmlSerializerFormatAttribute> задается в <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> для операции.|  
  
|Значение TransactionFlowAttribute|Изменяемое значение дерева описания|  
|------------------------------------|-------------------------------------|  
|TransactionFlowOption|<xref:System.ServiceModel.TransactionFlowAttribute> добавляется в виде расширения функциональности в свойство <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A>.|  
  
|Значение MessageContractAttribute|Изменяемое значение дерева описания|  
|------------------------------------|-------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|Значение MessageHeaderAttribute|Изменяемое значение дерева описания|  
|----------------------------------|-------------------------------------|  
|Субъект|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Имя|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Ретрансляция|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|Значение MessageBodyMemberAttribute|Изменяемое значение дерева описания|  
|--------------------------------------|-------------------------------------|  
|Имя|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Порядок|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|Значение MessageHeaderArrayAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-------------------------------------|  
|Субъект|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|Имя|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Ретрансляция|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|Значение MessagePropertyAttribute|Изменяемое значение дерева описания|  
|------------------------------------|-------------------------------------|  
|Имя|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|Значение MessageParameterAttribute|Изменяемое значение дерева описания|  
|-------------------------------------|-------------------------------------|  
|Имя|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 Дополнительные сведения о преобразовании значений дерева описания в метаданные см. в разделе [ServiceDescription и Справочник по WSDL](servicedescription-and-wsdl-reference.md).  
  
## <a name="see-also"></a>См. также

- [ServiceDescription и справочная информация о WSDL](servicedescription-and-wsdl-reference.md)
