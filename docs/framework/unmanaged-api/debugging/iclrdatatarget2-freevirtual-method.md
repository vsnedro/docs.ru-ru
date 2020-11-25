---
title: Метод ICLRDataTarget2::FreeVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: 1fb701a40abe2dc6e51443837c07ee5ba05ddfbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723653"
---
# <a name="iclrdatatarget2freevirtual-method"></a>Метод ICLRDataTarget2::FreeVirtual

Вызывается службами доступа к данным среды CLR для освобождения памяти, которая была ранее выделена в адресном пространстве целевого процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `addr`  
 окне `CLRDATA_ADDRESS` Значение, указывающее начальный адрес памяти для высвобождения.  
  
 `size`  
 окне Размер (в байтах) памяти, которая должна быть освобождена.  
  
 `typeFlags`  
 окне Флаги, управляющие освобождением памяти. См. раздел `VirtualFree` функция Win32.  
  
## <a name="remarks"></a>Комментарии  

 `FreeVirtual`Метод служит логической оболочкой для `VirtualFree` функции Win32.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)
- [Метод AllocVirtual](iclrdatatarget2-allocvirtual-method.md)
