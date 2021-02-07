---
description: 'Дополнительные сведения о: Привацинотицебиндинжелемент'
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: ece6687f12c4ece45254b1acddb9598e4a10cbb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743886"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement

PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс PrivacyNoticeBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс PrivacyNoticeBindingElement имеет следующие свойства.  
  
### <a name="privacynoticeversion"></a>PrivacyNoticeVersion  

 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Версия уведомления о конфиденциальности.  
  
### <a name="url"></a>Url  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 URL-адрес, по которому расположено уведомление о конфиденциальности.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
