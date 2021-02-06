---
description: 'Дополнительные сведения: <bindingExtensions>'
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: e568c7dd2da509709e5c85d3181d1808b1c636df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639410"
---
# \<bindingExtensions>

В этом разделе описывается использование пользовательской привязки из файла конфигурации компьютера или приложения. Добавить пользовательскую привязку в эту коллекцию можно с помощью ключевого слова `add`, установив атрибут `type` элемента равным пользовательской привязке, а атрибут `name` равным имени пользовательской привязки.

Расширения привязки позволяют пользователю создавать привязки для использования в составе конфигурации конечной точки. Ну уровне программирования расширение привязки представляет собой тип, реализующий абстрактный класс <xref:System.ServiceModel.Channels.Binding>.

В следующем примере используется `add` элемент, а также `name` атрибут для добавления расширения привязки в `bindingExtensions` раздел файла конфигурации:

```xml
<system.serviceModel>
  <extensions>
    <bindingExtensions>
      <add name="MyBinding"
           type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingExtensions>
  </extensions>
</system.serviceModel>
```

Чтобы добавить в элемент возможность настройки, пользователю следует записать и зарегистрировать элемент `bindingSection`. Дополнительные сведения об этом см. в документации по <xref:System.Configuration>.

После определения элемента и его типа конфигурации расширение можно использовать как часть конечной точки, как показано в следующем примере:

```xml
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```

## <a name="see-also"></a>См. также

- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
