---
description: 'Дополнительные сведения о методе: ICorConfiguration:: Сетгчостконтрол'
title: Метод ICorConfiguration::SetGCHostControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: 4d3d6e5e5275adf02f9d693234a5c8e77714fd03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636654"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a>Метод ICorConfiguration::SetGCHostControl

Задает интерфейс обратного вызова, используемый сборщиком мусора для запроса изменения ограничения виртуальной памяти на узле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pGCHostControl`  
 окне Указатель на объект [игчостконтрол](igchostcontrol-interface.md) , который позволяет сборщику мусора запрашивать у узла изменение ограничений виртуальной памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorConfiguration](icorconfiguration-interface.md)
