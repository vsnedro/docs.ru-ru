---
description: 'Дополнительные сведения о: интерфейс ICLRGCManager2'
title: Интерфейс ICLRGCManager2
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
ms.openlocfilehash: 455b3a99d10fa43bf325e9f7075d255dd55ae38b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789961"
---
# <a name="iclrgcmanager2-interface"></a>Интерфейс ICLRGCManager2

Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md)|Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора. Включает поколение 0 и размеры сегментов, превышающие `DWORD` .|  
  
## <a name="remarks"></a>Remarks  

 Этот интерфейс наследуется от [интерфейса иклргкманажер](iclrgcmanager-interface.md).  
  
 Среда CLR реализует механизм сборки мусора для управляемого <xref:System.GC> типа. Дополнительные сведения о системе сборки мусора см. в разделе [сборка мусора](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Автоматическое управление памятью](../../../standard/automatic-memory-management.md)
- [Структура COR_GC_STATS](cor-gc-stats-structure.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)
