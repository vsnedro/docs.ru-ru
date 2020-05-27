---
title: Интерфейс IGCHost
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
ms.openlocfilehash: 9d6c9d22f4e50c21e2f41b7efd402907ff5843db
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805216"
---
# <a name="igchost-interface"></a>Интерфейс IGCHost
Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.  
  
> [!NOTE]
> Начиная с .NET Framework 4,5, можно использовать метод [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) , чтобы задать размер сегмента сборки мусора и максимальный размер поколения 0 системы сборки мусора до значений, превышающих `DWORD` предельное значение, накладываемое методом [сетгкстартуплимитс](igchost-setgcstartuplimits-method.md) .  
  
> [!NOTE]
> Этот интерфейс предназначен только для экспертного использования. Это может повлиять на производительность приложения при неправильном использовании.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Collect](igchost-collect-method.md)|Принудительно выполняет сбор данных для данного поколения независимо от состояния текущей сборки мусора.|  
|[Метод GetStats](igchost-getstats-method.md)|Возвращает статистику текущего состояния системы сборки мусора.|  
|[Метод GetThreadStats](igchost-getthreadstats-method.md)|Возвращает статистику по потокам для сборки мусора.|  
|[Метод SetGCStartupLimits](igchost-setgcstartuplimits-method.md)|Задает размер сегмента и максимальный размер для поколения 0.|  
|[Метод SetVirtualMemLimit](igchost-setvirtualmemlimit-method.md)|Задает максимальный размер виртуальной памяти среды выполнения.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl, Гчост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейсы размещения](hosting-interfaces.md)
- [Компонентный класс CorRuntimeHost](corruntimehost-coclass.md)
