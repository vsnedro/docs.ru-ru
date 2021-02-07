---
description: 'Дополнительные сведения о: интерфейс IGCHost2'
title: Интерфейс IGCHost2
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: e32a4894fcff3600c9385f0f559443e23b2bc307
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709325"
---
# <a name="igchost2-interface"></a>Интерфейс IGCHost2

Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.  
  
> [!NOTE]
> Для новой разработки рекомендуется вместо этого использовать интерфейс [ICLRGCManager2](iclrgcmanager2-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md)|Задает размер сегмента и максимальный размер для поколения 0. Включает поколение 0 и размеры сегментов, превышающие `DWORD` .|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Гчост. idl, Гчост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
- [Интерфейсы размещения CLR](clr-hosting-interfaces.md)
- [Компонентный класс CorRuntimeHost](corruntimehost-coclass.md)
