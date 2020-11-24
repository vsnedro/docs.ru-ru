---
title: Функция CreateAssemblyEnum
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
ms.openlocfilehash: b7e3696121475885f5061bd96eb6905d7ccae734
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683177"
---
# <a name="createassemblyenum-function"></a>Функция CreateAssemblyEnum

Возвращает указатель на экземпляр [IAssemblyEnum](iassemblyenum-interface.md) , который может перечислить объекты в сборке с указанным [IAssemblyName](iassemblyname-interface.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `pEnum`  
 заполняет Указатель на место в памяти, содержащее запрошенный `IAssemblyEnum` указатель.  
  
 `pUnkReserved`  
 окне Зарезервировано для будущего расширения. `pUnkReserved` должен быть пустой ссылкой.  
  
 `pName`  
 окне Объект `IAssemblyName` запрошенной сборки. Это имя используется для фильтрации перечисления. Для перечисления всех сборок в глобальном кэше сборок может быть задано значение null.  
  
 `dwFlags`  
 окне Флаги для изменения поведения перечислителя. Этот параметр содержит ровно один бит от перечисления [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
## <a name="remarks"></a>Комментарии  

 `dwFlags`Параметр содержит ровно один бит из `ASM_CACHE_FLAGS` перечисления.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IAssemblyEnum](iassemblyenum-interface.md)
- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
