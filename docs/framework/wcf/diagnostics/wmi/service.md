---
title: Служба
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: aa4eecbcc8a2ef818cd99d777b0e3c2f1f222e46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273286"
---
# <a name="service"></a>Служба

Служба  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс Service не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс Service имеет следующие свойства.  
  
### <a name="baseaddresses"></a>BaseAddresses  

 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Базовые адреса, используемые службой.  
  
### <a name="behaviors"></a>Расширения функциональности  

 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Поведения, связанные с этой службой.  
  
### <a name="configurationname"></a>ConfigurationName  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 ServiceElement_BehaviorConfiguration  
  
### <a name="counterinstancename"></a>CounterInstanceName  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Имя экземпляра счетчиков производительности службы.  
  
### <a name="distinguishedname"></a>Различающееся имя.  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Имя службы по адресу.  
  
### <a name="extensions"></a>Расширения  

 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Контексты экземпляра для расширений экземпляра службы.  
  
### <a name="metadata"></a>Метаданные  

 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Параметры метаданных службы.  
  
### <a name="name"></a>name  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Уникальное имя службы.  
  
### <a name="namespace"></a>Пространство имен  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Пространство имен службы.  
  
### <a name="opened"></a>Opened (Открыто)  

 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Время открытия службы.  
  
### <a name="outgoingchannels"></a>OutgoingChannels  

 Тип данных: массив Channel  
  
 Тип доступа: только для чтения  
  
 Каналы, исходящие из экземпляра службы.  
  
### <a name="processid"></a>ProcessId  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Возвращает ИД процесса, который размещает службу.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
