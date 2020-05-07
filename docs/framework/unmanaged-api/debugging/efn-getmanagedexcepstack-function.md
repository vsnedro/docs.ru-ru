---
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
ms.openlocfilehash: c50fe09648793ba7340960654811ff31187269d8
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860790"
---
# <a name="_efn_getmanagedexcepstack-function"></a>\_ЕФН\_Жетманажедексцепстакк, функция
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
 окне Указатель на управляемый объект, производный от <xref:System.Exception>.  
  
 сзстаккстринг  
 заполняет Возвращаемая строка.  
  
 `cbString`  
 заполняет Число символов, доступных в буфере строк.  
  
## <a name="remarks"></a>Примечания  
 Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0x82 и кодом ошибки 0x1000.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace. h  
  
 **Версия .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции отладки](debugging-global-static-functions.md)
