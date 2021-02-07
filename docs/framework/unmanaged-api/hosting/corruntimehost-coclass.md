---
description: 'Подробнее о: Коррунтимехост coclass'
title: Компонентный класс CorRuntimeHost
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: cd2d01075e5c8264337e1e989b3d9fdc6bf68962
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760645"
---
# <a name="corruntimehost-coclass"></a>Компонентный класс CorRuntimeHost

Предоставляет интерфейсы для управления приложениями, которые выполняются средой CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Интерфейс ICorConfiguration](icorconfiguration-interface.md)|Предоставляет методы для настройки среды CLR.|  
|[Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)|Предоставляет методы, позволяющие основному приложению запускать и прекращать работу среды CLR, создавать и настраивать домены приложений, получать доступ к домену по умолчанию и перечислять все домены, выполняющиеся в процессе.|  
|[Интерфейс IDebuggerInfo](idebuggerinfo-interface.md)|Предоставляет методы для получения сведений о состоянии служб отладки.|  
|[Интерфейс IGCHost](igchost-interface.md)|Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.|  
|IValidator|Предоставляет методы для проверки переносимых исполняемых образов и подробных отчетов об ошибках проверки.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение коклассов](hosting-coclasses.md)
