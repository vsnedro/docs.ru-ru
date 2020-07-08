---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: cb425d9f4dadd97e93946a2b4cd9d059ea8504ce
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051367"
---
# <a name="servicehost"></a>\@ServiceHost

Связывает фабрику, используемую для создания узла службы, с размещаемой службой и другими элементами программирования, необходимыми для доступа или компиляции кода размещения, представленного в SVC-файле.

## <a name="syntax"></a>Синтаксис

```aspx-csharp
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```

## <a name="attributes"></a>Атрибуты

### <a name="service"></a>Служба

Имя типа CLR размещенной службы. Это должно быть полное имя типа, который реализует один или несколько контактов службы.

### <a name="factory"></a>Factory

Имя типа CLR фабрики узла службы, используемой для создания узла службы. Этот атрибут является необязательным. Если данный атрибут не задан, по умолчанию используется значение <xref:System.ServiceModel.Activation.ServiceHostFactory>, которое возвращает экземпляр <xref:System.ServiceModel.ServiceHost>.

### <a name="debug"></a>Отладка

Указывает, должна ли служба Windows Communication Foundation (WCF) компилироваться с отладочными символами. `true`значение, если служба WCF должна быть скомпилирована с отладочными символами; в противном случае — `false` .

### <a name="language"></a>Язык

Задает язык, используемый при компиляции всего встроенного кода в файле (SVC). Значения могут представлять любые. NET — поддерживаемый язык, включая `C#` , `VB` и `JS` , которые ссылаются на C#, Visual Basic и JScript .NET соответственно. Этот атрибут является необязательным.

### <a name="codebehind"></a>CodeBehind

Указывает исходный файл, который реализует веб-службу XML, если класс, реализующий веб-службу XML, не находится в том же файле и не был скомпилирован в сборку и помещен в каталог *\bin* .

## <a name="remarks"></a>Комментарии

Объект, <xref:System.ServiceModel.ServiceHost> используемый для размещения службы, является точкой расширения в модели программирования Windows Communication Foundation (WCF). Для создания узла службы <xref:System.ServiceModel.ServiceHost> используется шаблон фабрики, поскольку он, возможно, имеет полиморфный тип, экземпляр которого среда размещения не должна создавать явно.

В реализации по умолчанию используется фабрика <xref:System.ServiceModel.Activation.ServiceHostFactory> для создания экземпляра узла службы <xref:System.ServiceModel.ServiceHost>. Но вы можете предоставить собственную фабрику (которая возвращает производный узел), указав имя типа CLR для реализации фабрики в `@ServiceHost` директиве.

Чтобы использовать собственную фабрику узла службы вместо фабрики по умолчанию, просто укажите имя типа в `@ServiceHost` директиве следующим образом.

```xml
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>
```

Создавайте реализацию фабрики в наиболее простом виде. Если имеется значительный объем пользовательской логики, то можно увеличить возможность повторного использования кода, если разместить эту логику на узле, а не в фабрике.

Например, чтобы включить конечную точку с поддержкой AJAX для `MyService` , укажите <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> для значения `Factory` атрибута, а не по умолчанию <xref:System.ServiceModel.Activation.ServiceHostFactory> в `@ServiceHost` директиве, как показано в следующем примере:

```aspx-csharp
<% @ServiceHost
Service="MyService"
Language="C#"
Debug="true"
Factory="WebScriptServiceHostFactory"
%>
```

## <a name="see-also"></a>См. также

- [Пользовательский узел службы](../../../wcf/samples/custom-service-host.md)
