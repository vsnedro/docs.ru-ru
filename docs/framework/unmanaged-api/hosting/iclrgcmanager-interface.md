---
title: Интерфейс ICLRGCManager
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
ms.openlocfilehash: dbe3df6bb20e5ad8f9eb534a366405eb9c33984f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678250"
---
# <a name="iclrgcmanager-interface"></a>Интерфейс ICLRGCManager

Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.  
  
> [!NOTE]
> Начиная с .NET Framework 4,5, можно использовать метод [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) , чтобы задать размер сегмента сборки мусора и максимальный размер поколения 0 системы сборки мусора до значений, превышающих `DWORD` предельное значение, накладываемое методом [сетгкстартуплимитс](iclrgcmanager-setgcstartuplimits-method.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Collect](iclrgcmanager-collect-method.md)|Вызывает принудительную сборку мусора для указанного поколения.|  
|[Метод GetStats](iclrgcmanager-getstats-method.md)|Возвращает набор текущих статистических данных о системе сборки мусора.|  
|[Метод SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md)|Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.|  
  
## <a name="remarks"></a>Комментарии  

 Среда CLR реализует механизм сборки мусора для управляемого <xref:System.GC> типа. Дополнительные сведения о системе сборки мусора см. в разделе [сборка мусора](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Автоматическое управление памятью](../../../standard/automatic-memory-management.md)
- [Структура COR_GC_STATS](cor-gc-stats-structure.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейсы размещения CLR](clr-hosting-interfaces.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)
