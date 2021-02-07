---
description: 'Дополнительные сведения о методе: IHostMemoryManager:: Релеаседвиртуаладдрессспаце'
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
ms.openlocfilehash: e67e80018b5002bdf2a50530af9ab057696fff4c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707778"
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
  
## <a name="remarks"></a>Remarks  

 `ReleasedVirtualAddressSpace`Метод является методом обратного вызова и должен быть реализован модулем записи размещающего приложения. Он вызывается средой CLR.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
