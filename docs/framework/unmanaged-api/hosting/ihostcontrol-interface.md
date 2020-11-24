---
title: Интерфейс IHostControl
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 1bffef31702aa051d9ca865b18a67ac90c00cd00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680666"
---
# <a name="ihostcontrol-interface"></a>Интерфейс IHostControl

Предоставляет методы для настройки загрузки сборок и для определения того, какие интерфейсы размещения поддерживает узел.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetHostManager](ihostcontrol-gethostmanager-method.md)|Возвращает указатель интерфейса на реализацию интерфейса узла с указанным `IID` .|  
|[Метод SetAppDomainManager](ihostcontrol-setappdomainmanager-method.md)|Уведомляет узел о том, что домен приложения создан.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.AppDomainManager>
- [Интерфейс ICLRRuntimeHost](iclrruntimehost-interface.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
