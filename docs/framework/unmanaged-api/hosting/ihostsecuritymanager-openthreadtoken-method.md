---
title: Метод IHostSecurityManager::OpenThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 85c7308f794929d753b50f58f69168f67a31cb85
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803876"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>Метод IHostSecurityManager::OpenThreadToken
Открывает маркер доступа на уровне пользователей, связанный с выполняющимся в данный момент потоком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 окне Маска значений доступа, указывающих запрошенные типы доступа к токену потока. Эти значения определены в `OpenThreadToken` функции Win32. Запрошенные типы доступа согласовываются с избирательным списком управления доступом (DACL) маркера, чтобы определить, какие типы доступа следует предоставить или запретить.  
  
 `bOpenAsSelf`  
 [входные] `true` значение, чтобы указать, что проверка доступа должна выполняться с помощью контекста безопасности процесса для вызывающего потока; `false`значение, чтобы указать, что проверка доступа должна выполняться с использованием контекста безопасности для самого вызывающего потока. Если поток олицетворяет клиента, контекст безопасности может быть таким же, как у клиентского процесса.  
  
 `phThreadToken`  
 заполняет Указатель на вновь открытый маркер доступа.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Замечания  
 `IHostSecurityManager::OpenThreadToken`ведет себя аналогично соответствующей функции Win32 с тем же именем, за исключением того, что функция Win32 позволяет вызывающему объекту передать маркер произвольному потоку, а `IHostSecurityManager::OpenThreadToken` открывает только маркер, связанный с вызывающим потоком.  
  
 `HANDLE`Тип не совместим с COM, то есть его размер зависит от операционной системы и требует настраиваемого маршалирования. Таким же маркер предназначен только для использования внутри процесса между средой CLR и узлом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IHostSecurityContext](ihostsecuritycontext-interface.md)
- [Интерфейс IHostSecurityManager](ihostsecuritymanager-interface.md)
