---
description: 'Дополнительные сведения о: Пирсекуритисеттингс'
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: a8b5b8c88e71cb46110fa35186599c0f9c366d17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803013"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings

PeerSecuritySettings  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс PeerSecuritySettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс PeerSecuritySettings имеет следующие свойства.  
  
### <a name="mode"></a>Режим  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.  
  
### <a name="transport"></a>Транспорт  

 Тип данных: PeerTransportSecuritySettings  
  
 Тип доступа: только для чтения  
  
 Параметры безопасности транспорта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.PeerSecuritySettings>
