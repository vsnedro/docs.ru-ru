---
title: Конечная точка
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: ceb4e4b41502b00d7bb21f1ecbd8249fccf1ce3b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288818"
---
# <a name="endpoint"></a>Конечная точка

Конечная точка  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс Endpoint определяет следующий метод.  
  
|Метод|Описание|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](getoperationcounterinstancename.md)|Извлекает имя экземпляра счетчика производительности операций|  
  
## <a name="properties"></a>Свойства  

 Класс Endpoint имеет следующие свойства.  
  
### <a name="address"></a>Адрес  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса (URI), содержащий адрес конечной точки.  
  
### <a name="addressheaders"></a>AddressHeaders  

 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Коллекция заголовков адреса, прикрепленных к этой конечной точке.  
  
### <a name="addressidentity"></a>AddressIdentity  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Удостоверение конечной точки.  
  
### <a name="appdomainid"></a>AppDomainId  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор домена приложения, который размещает конечную точку.  
  
### <a name="behaviors"></a>Расширения функциональности  

 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Коллекция поведений, реализуемых этой конечной точкой.  
  
### <a name="binding"></a>Привязка  

 Тип данных: Binding  
  
 Тип доступа: только для чтения  
  
 Привязка, используемая этой конечной точкой.  
  
### <a name="contractname"></a>ContractName  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Строка, в которой указывается, какой контракт предоставляется этой конечной точкой.  
  
### <a name="counterinstancename"></a>CounterInstanceName  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Имя экземпляра счетчиков производительности конечной точки.  
  
### <a name="listenuri"></a>ListenUri  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса (URI), от которого данная конечная точка ожидает передачи данных.  
  
### <a name="name"></a>name  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Уникальное имя конечной точки.  
  
### <a name="processid"></a>ProcessId  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Возвращает идентификатор процесса, который размещает конечную точку.  
  
### <a name="ref"></a>ref  

 Тип данных: Contract  
  
 Тип доступа: только для чтения  
  
 Контракт, предоставляемый этой конечной точкой.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
