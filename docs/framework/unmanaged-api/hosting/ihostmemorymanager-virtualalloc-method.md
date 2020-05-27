---
title: Метод IHostMemoryManager::VirtualAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
ms.openlocfilehash: de41b5e0aaf835ee2d4e4f32696fe104d5830b57
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804448"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>Метод IHostMemoryManager::VirtualAlloc
Служит логической оболочкой для соответствующей функции Win32. Реализация Win32 `VirtualAlloc` резервирует или фиксирует область страниц в виртуальном адресном пространстве вызывающего процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAddress`  
 окне Указатель на начальный адрес области для выделения.  
  
 `dwSize`  
 окне Размер области в байтах.  
  
 `flAllocationType`  
 окне Тип выделения памяти.  
  
 `flProtect`  
 окне Защита памяти для выделяемого региона страниц.  
  
 `dwCriticalLevel`  
 окне Значение [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) , указывающее влияние сбоя выделения.  
  
 `ppMem`  
 заполняет Указатель на начальный адрес выделенной памяти или значение null, если запрос не может быть удовлетворен.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти для завершения запроса на выделение|  
  
## <a name="remarks"></a>Замечания  
 Чтобы зарезервировать регион в адресном пространстве процесса, вызовите метод `VirtualAlloc` . `pAddress`Параметр содержит начальный адрес требуемого блока памяти. Обычно этот параметр имеет значение null. Операционная система хранит записи доступных диапазонов свободных адресов для вашего процесса. `pAddress`Значение NULL предписывает системе зарезервировать регион везде, где он видит. Кроме того, можно указать конкретный начальный адрес для блока памяти. В обоих случаях выходной параметр возвращается в `ppMem` виде указателя на выделенную память. Сама функция возвращает значение HRESULT.  
  
 Функция Win32 `VirtualAlloc` не имеет `ppMem` параметра и вместо нее возвращает указатель на выделенную память. Дополнительные сведения см. в документации по платформе Windows.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
