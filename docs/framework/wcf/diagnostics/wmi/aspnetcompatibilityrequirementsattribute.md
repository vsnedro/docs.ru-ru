---
title: AspNetCompatibilityRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 00908a39-a21b-4029-bbb9-33e5a6ed25a7
ms.openlocfilehash: 9cf7031b58fcf9a5d29761d9ffbdaee45d9ff3ff
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252001"
---
# <a name="aspnetcompatibilityrequirementsattribute"></a>AspNetCompatibilityRequirementsAttribute

AspNetCompatibilityRequirementsAttribute  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class AspNetCompatibilityRequirementsAttribute : Behavior  
{  
  string RequirementsMode;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс AspNetCompatibilityRequirementsAttribute не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс AspNetCompatibilityRequirementsAttribute имеет следующее свойство.  
  
### <a name="requirementsmode"></a>RequirementsMode  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Указывает, активен ли режим совместимости ASP.NET.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.ServiceHostingEnvironment.AspNetCompatibilityEnabled%2A>
