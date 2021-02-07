---
description: 'Дополнительные сведения о методе: IHostMemoryManager:: VirtualFree'
title: Метод IHostMemoryManager::VirtualFree
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: 987661ce1b7bfd08f757f53082313b8eb60ff282
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707546"
---
# <a name="ihostmemorymanagervirtualfree-method"></a>Метод IHostMemoryManager::VirtualFree

Служит логической оболочкой для соответствующей функции Win32. Реализация в Win32 `VirtualFree` выпусков, снятие фиксаций, освобождение и отменяет фиксацию области страниц в виртуальном адресном пространстве вызывающего процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `lpAddress`  
 окне Указатель на базовый адрес страниц виртуальной памяти, которые должны быть освобождены.  
  
 `dwSize`  
 окне Размер (в байтах) области, которая должна быть освобождена.  
  
 `dwFreeType`  
 окне Тип операции освобождения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`VirtualFree` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|Предпринята попытка освободить память, которая не была выделена через узел.|  
  
## <a name="remarks"></a>Remarks  

 `VirtualFree` Освобождает страницы виртуальной памяти, связанные с `lpAddress` параметром, с помощью предыдущего вызова функции [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) . Пытается освободить память, которая не была выделена с помощью узла, должна возвращать HOST_E_INVALIDOPERATION.  
  
 Семантика идентична реализации Win32 `VirtualFree` . Дополнительные сведения см. в документации по платформе Windows.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
- [Интерфейс IHostMalloc](ihostmalloc-interface.md)
