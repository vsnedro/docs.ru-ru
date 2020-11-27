---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: c618b5b41790b04a84b4c50fe47baa2c0cb05ab2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274105"
---
# <a name="symmetricsecuritybindingelement"></a>SymmetricSecurityBindingElement

SymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс SymmetricSecurityBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс SymmetricSecurityBindingElement имеет следующие свойства.  
  
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

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
