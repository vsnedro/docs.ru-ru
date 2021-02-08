---
description: 'Дополнительные сведения о: WebContentTypeMapper Sample'
title: Пример WebContentTypeMapper
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: 274672bb8db1dc845b1cc1ced58b4c4a92232e9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798151"
---
# <a name="webcontenttypemapper-sample"></a>Пример WebContentTypeMapper

В этом примере показано, как сопоставлять новые типы содержимого с форматами текста сообщений Windows Communication Foundation (WCF).  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>Элемент подключается к кодировщику веб-сообщений, который позволяет WCF принимать сообщения JSON, XML или необработанные двоичные данные в той же конечной точке. Кодировщик определяет формат тела сообщения, просмотрев тип содержимого HTTP запроса. В этом примере показан класс <xref:System.ServiceModel.Channels.WebContentTypeMapper>, который позволяет пользователю управлять сопоставлением типа содержимого и формата тела.  
  
 WCF предоставляет набор сопоставлений по умолчанию для типов содержимого. Например, `application/json` сопоставляется с JSON, а `text/xml` сопоставляет с XML. Любой тип содержимого, который не сопоставляется с JSON или XML, сопоставляется с необработанным двоичным форматом.  
  
 В некоторых сценариях (например, интерфейсы API внедрения) разработчик службы не управляет типом содержимого, возвращаемым клиентом. Например, клиенты могут возвращать JSON как `text/javascript`, а не `application/json`. В этом случае разработчик службы должен предоставить тип, унаследованный от <xref:System.ServiceModel.Channels.WebContentTypeMapper>, для правильной обработки данного типа содержимого, как показано в следующем образце кода.  
  
```csharp  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 Тип должен переопределить метод <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>. Метод должен оценить аргумент `contentType` и возвратить одно из следующих значений: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw> или <xref:System.ServiceModel.Channels.WebContentFormat.Default>. Возврат <xref:System.ServiceModel.Channels.WebContentFormat.Default> следует сопоставлениям кодировщика веб-сообщений по умолчанию. В предыдущем примере кода тип содержимого `text/javascript` сопоставляется с JSON, а все другие сопоставления остаются неизменными.  
  
 Для использования класса `JsonContentTypeMapper` воспользуйтесь следующими элементами Web.config:  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Чтобы проверить требование к использованию JsonContentTypeMapper, удалите атрибут contentTypeMapper из указанного выше файла конфигурации. Не удается загрузить страницу клиента при попытке использования `text/javascript` для отправки содержимого JSON.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Создайте решение Вебконтенттипемапперсампле. sln, как описано в разделе [Создание примеров Windows Communication Foundation](building-the-samples.md).  
  
3. Перейдите к `http://localhost/ServiceModelSamples/JCTMClientPage.htm` (не открывайте JCTMClientPage.htm в браузере в каталоге проекта).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для платформа .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
