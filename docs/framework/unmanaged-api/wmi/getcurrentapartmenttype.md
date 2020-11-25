---
title: Функция Жеткуррентапартменттипе (Справочник по неуправляемым API)
description: Функция Жеткуррентапартменттипе Извлекает тип подразделения, в котором выполняется вызывающий объект.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0832867d86b7dda80e037846d9aa66c1d37f87be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726201"
---
# <a name="getcurrentapartmenttype-function"></a>Функция GetCurrentApartmentType

Получает тип подразделения, в котором выполняется вызывающий объект.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc,
   [in] IComThreadingInfo*    ptr,
   [out] APTTYPE*             aptType
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [икомсреадингинфо](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) .

`aptType`  
заполняет Указатель на значение перечисления [апттипе](/windows/win32/api/objidlbase/ne-objidlbase-apttype) , указывающее подразделение вызывающего объекта.

## <a name="return-value"></a>Возвращаемое значение

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `S_OK` | 0 | Функция успешно завершена. |
| `E_FAIL` | 0x80000008 | Вызывающий объект не выполняется в апартаменте. |
  
## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [икомсреадингинфо:: жеткуррентапартменттипе](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
