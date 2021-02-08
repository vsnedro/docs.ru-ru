---
description: 'Подробнее о: Клррунтимехост coclass'
title: Кокласс CLRRuntimeHost
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
ms.openlocfilehash: a371b9b7263f8bb58b5c513de6647320f000beed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799893"
---
# <a name="clrruntimehost-coclass"></a>Кокласс CLRRuntimeHost

Предоставляет интерфейсы для управления выполнением кода средой выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Интерфейс ICLRRuntimeHost](iclrruntimehost-interface.md)|Предоставляет методы для управления выполнением приложений средой выполнения.|  
|[Интерфейс ICLRValidator](iclrvalidator-interface.md)|Предоставляет методы для проверки переносимых исполняемых образов и для подробных отчетов об ошибках проверки.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение коклассов](hosting-coclasses.md)
