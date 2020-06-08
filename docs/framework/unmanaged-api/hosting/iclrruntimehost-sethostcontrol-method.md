---
title: Метод ICLRRuntimeHost::SetHostControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 644b31ae8e8f0c51c08bcad57220a028406cfd3a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504080"
---
# <a name="iclrruntimehostsethostcontrol-method"></a>Метод ICLRRuntimeHost::SetHostControl
Задает указатель интерфейса, который среда CLR может использовать для получения реализации [интерфейса IHostControl](ihostcontrol-interface.md)в узле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pHostControl`  
 окне Указатель интерфейса на реализацию [интерфейса IHostControl](ihostcontrol-interface.md)узла.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetHostControl`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_CLR_ALREADY_STARTED|Среда CLR уже инициализирована.|  
  
## <a name="remarks"></a>Примечания  
 Необходимо вызвать `SetHostControl` перед инициализацией среды CLR, то есть до вызова [метода Start](iclrruntimehost-start-method.md) или использования любого [интерфейса метаданных](../metadata/metadata-interfaces.md). Рекомендуется вызывать `SetHostControl` немедленно после вызова [функции Корбиндтокуррентрунтиме](corbindtocurrentruntime-function.md) или [функции CorBindToRuntimeEx](corbindtoruntimeex-function.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeHost](iclrruntimehost-interface.md)
- [Интерфейс IHostControl](ihostcontrol-interface.md)
