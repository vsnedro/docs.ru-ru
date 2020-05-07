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
ms.openlocfilehash: 0a36af5b411673081e74aa243ec8e0f8f876f238
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860472"
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
  
## <a name="remarks"></a>Примечания  
 `FreeVirtual` Метод служит логической оболочкой для функции Win32 `VirtualFree` .  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)
- [Метод AllocVirtual](iclrdatatarget2-allocvirtual-method.md)
