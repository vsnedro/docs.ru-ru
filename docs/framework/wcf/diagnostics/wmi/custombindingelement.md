---
description: 'Дополнительные сведения о: Кустомбиндинжелемент'
title: CustomBindingElement
ms.date: 03/30/2017
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
ms.openlocfilehash: fc3f1fcbfc54ff082f87e04a894226ff9ca996bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757518"
---
# <a name="custombindingelement"></a>CustomBindingElement

CustomBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class CustomBindingElement : BindingElement  
{  
  string Name;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс CustomBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс CustomBindingElement имеет следующее свойство:  
  
### <a name="name"></a>Имя  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Строка, содержащая имя конфигурации привязки. Это значение является определяемой пользователем строкой, которая используется как строка идентификации для пользовательской привязки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.CustomBinding>
