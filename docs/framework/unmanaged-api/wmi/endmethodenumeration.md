---
title: Функция Ендмесоденумератион (Справочник по неуправляемым API)
description: Функция Ендмесоденумератион завершает последовательность перечисления методов.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 82f50530967699427d8a00b1c9f518b639273626
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708066"
---
# <a name="endmethodenumeration-function"></a>Функция EndMethodEnumeration

Завершает последовательность перечисления, запущенную с вызовом [функции бегинмесоденумератион](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | 0x8004101d | Произошла внутренняя ошибка. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: ендмесоденумератион](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) .

Вызывающий объект начинает последовательность перечисления с помощью [функции бегинмесоденумератион](beginmethodenumeration.md), а затем вызывает [функцию некстмесод](nextmethod.md ), пока метод не вернет значение `WBEM_S_NO_MORE_DATA` . Вызывающий объект, по желанию, завершает последовательность путем вызова `EndMethodEnumeration` . Вызывающий объект может завершить перечисление раньше, вызвав `EndMethodEnumeration` в любое время.

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
