---
description: 'Дополнительные сведения о: AsymmetricSecurityBindingElement'
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 25d0ac205491e9ce27c59d3a0670d1e4a3150e21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757947"
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement

AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс AsymmetricSecurityBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс AsymmetricSecurityBindingElement имеет следующие свойства.  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Порядок шифрования и подписывания сообщений для данной привязки.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, требует ли привязка подтверждения подписи.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
