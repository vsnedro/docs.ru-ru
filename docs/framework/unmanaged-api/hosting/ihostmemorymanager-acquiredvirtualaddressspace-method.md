---
description: 'Дополнительные сведения о методе: IHostMemoryManager:: Аккуиредвиртуаладдрессспаце'
title: Метод IHostMemoryManager::AcquiredVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
ms.openlocfilehash: 70424c5bf907cfc3fb2e8951464335323f9331f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707921"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a>Метод IHostMemoryManager::AcquiredVirtualAddressSpace

Уведомляет узел о том, что среда CLR получила указанную память из операционной системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `startAddress`  
 окне Начальный адрес памяти.  
  
 `size`  
 окне Размер памяти в байтах.  
  
## <a name="remarks"></a>Remarks  

 `AcquiredVirtualAddressSpace`Метод является методом обратного вызова и должен быть реализован модулем записи размещающего приложения. Он вызывается средой CLR.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
