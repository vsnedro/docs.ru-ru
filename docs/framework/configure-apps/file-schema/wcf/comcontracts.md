---
description: 'Дополнительные сведения: <comContracts>'
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 263210b4499274fe009a6b1b1e46c1f09dd007ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638656"
---
# \<comContracts>

Раздел конфигурации `comContracts` содержит элементы, которые позволяют задавать различные свойства контракта службы интеграции COM+.  
  
## <a name="specifying-namespace-and-contract"></a>Задание пространства имен и контракта  

 Контракты службы интеграции COM+ в настоящее время ограничены `http://tempuri.org` пространством имен, а имя контракта является производным от поддерживающего COM-интерфейса. Однако можно указать альтернативы, используя раздел `comContracts` в файле конфигурации.  
  
 Например, для указания пространства имен, имени контракта службы и параметра для принудительного использования сеансовых привязок можно использовать следующую конфигурацию.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 После инициализации службы указанные пространства имен и имена контрактов применяются к созданным описаниям служб.  
  
 Если раздел пуст, при инициализации службы применяется пространство имен по умолчанию и имя контракта, взятое из идентификатора поддерживающего COM-интерфейса.  
  
 Кроме того, элемент можно использовать [\<exposedMethod>](exposedmethod.md) для указания методов COM+, предоставляемых, когда интерфейс в компоненте com+ предоставляется как веб-служба. Можно также использовать [\<persistableTypes>](persistabletypes.md) для указания сохраняемых типов, используемых при интеграции. Наконец, можно использовать [\<userDefinedType>](userdefinedtype.md) элемент для включения определяемых пользователем типов (UDT), которые должны быть включены в контракт службы.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [Интеграция с приложениями COM+](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Практическое руководство. Настройка параметров службы COM+](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
