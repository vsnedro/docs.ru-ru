---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273260"
---
# <a name="serviceappdomain"></a>ServiceAppDomain

Сопоставляет службу с доменом приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс ServiceAppDomain не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс ServiceAppDomain имеет следующие свойства.  
  
### <a name="ref"></a>ref  

 Тип данных: Service  
Квалификаторы: ключ  
  
 Тип доступа: только для чтения  
  
 Служба этого домена приложения.  
  
### <a name="ref"></a>ref  

 Тип данных: AppDomainInfo  
Квалификаторы: ключ  
  
 Тип доступа: только для чтения  
  
 Содержит свойства домена приложения.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
