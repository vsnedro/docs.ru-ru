---
title: Метод IHostMemoryManager::GetMemoryLoad
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 0611b82e22ec9d5d2cde2a7f46e65b5e25733610
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731362"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>Метод IHostMemoryManager::GetMemoryLoad

Возвращает объем физической памяти, используемой в данный момент, и, следовательно, недоступен, сообщаемый узлом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pMemoryLoad`  
 заполняет Указатель на Приблизительный процент общего объема физической памяти, который используется в данный момент.  
  
 `pAvailableBytes`  
 заполняет Указатель на число байтов, доступных для среды CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Комментарии  

 `GetMemoryLoad` заключает в оболочку `GlobalMemoryStatus` функцию Win32. Значение `pMemoryLoad` является эквивалентом `dwMemoryLoad` поля в `MEMORYSTATUS` структуре, возвращаемой из `GlobalMemoryStatus` .  
  
 Среда выполнения использует возвращаемое значение в качестве эвристики для сборщика мусора. Например, если основное приложение сообщает о том, что используется большая часть памяти, сборщик мусора может выбрать сбор данных из нескольких поколений, чтобы увеличить объем памяти, который потенциально может стать доступным.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.GC?displayProperty=nameWithType>
- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
