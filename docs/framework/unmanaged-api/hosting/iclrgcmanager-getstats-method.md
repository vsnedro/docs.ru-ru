---
description: 'Дополнительные сведения о методе: Иклргкманажер:: stats'
title: Метод ICLRGCManager::GetStats
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
ms.openlocfilehash: 94b20fb313f06d73f1e7fafd1f46fefb0da3fe95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790026"
---
# <a name="iclrgcmanagergetstats-method"></a>Метод ICLRGCManager::GetStats

Возвращает набор текущих статистических данных о системе сборки мусора среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pStats`  
 [вход, выход] Экземпляр [COR_GC_STATS](cor-gc-stats-structure.md) , содержащий запрошенную статистику.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`GetStats` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Среда CLR вычисляет и возвращает только те статистические данные, которые указаны в `Flags` поле `pStats` .  
  
 Задайте в `Flags` поле одно или несколько значений перечисления [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) , чтобы указать, какие статистические данные должны быть заданы в структуре [COR_GC_STATS](cor-gc-stats-structure.md) .  
  
 Пример использования таков:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Автоматическое управление памятью](../../../standard/automatic-memory-management.md)
- [Структура COR_GC_STATS](cor-gc-stats-structure.md)
- [Перечисление COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md)
- [Сборка мусора](../../../standard/garbage-collection/index.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLRGCManager](iclrgcmanager-interface.md)
- [Интерфейсы размещения CLR](clr-hosting-interfaces.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)
