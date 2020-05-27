---
title: Метод IHostMemoryManager::ReleasedVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
ms.openlocfilehash: 4a246fb95ab5b4a7f187aa660f20e590c63ddff2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804458"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a>Метод IHostMemoryManager::ReleasedVirtualAddressSpace
Уведомляет узел о том, что среда CLR завершила работу с заданной памятью.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `startAddress`  
 окне Указатель на начальный адрес памяти для освобождения.  
  
## <a name="remarks"></a>Замечания  
 `ReleasedVirtualAddressSpace`Метод является методом обратного вызова и должен быть реализован модулем записи размещающего приложения. Он вызывается средой CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
