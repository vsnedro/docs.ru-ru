---
description: Дополнительные сведения о функции _EFN_GetManagedExcepStack
title: Функция _EFN_GetManagedExcepStack
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
ms.openlocfilehash: a3c7e30a377e10b9d4d0b1dd663a594a0e872f3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738316"
---
# <a name="_efn_getmanagedexcepstack-function"></a>\_ЕФН \_ жетманажедексцепстакк, функция

Учитывая адрес объекта управляемого исключения, возвращает строковую версию трассировки стека, содержащейся внутри.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `Client`  
 окне Отлаживаемый клиент.  
  
 `StackObjAddr`  
 окне Указатель на управляемый объект, производный от <xref:System.Exception> .  
  
 сзстаккстринг  
 заполняет Возвращаемая строка.  
  
 `cbString`  
 заполняет Число символов, доступных в буфере строк.  
  
## <a name="remarks"></a>Remarks  

 Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0x82 и кодом ошибки 0x1000.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace. h  
  
 **Версия платформа .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции отладки](debugging-global-static-functions.md)
