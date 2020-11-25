---
title: Функция раскрывшемся (Справочник по неуправляемым API)
description: Функция раскрывшемся определяет, является ли класс или экземпляр производным от конкретного родительского класса.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3cfe3388dc808335e6d3daaf7ec949108e95f52e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726799"
---
# <a name="inheritsfrom-function"></a>Функция InheritsFrom

Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszAncestor`  
окне Имя класса. `wszAncestor` должен указывать на допустимое значение `LPCWSTR` .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | 0 | Текущий объект наследует от `wszAncestor` .  |
| `WBEM_S_FALSE` | 1 | Текущий объект не наследует от `wszAncestor` . |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszAncestor` имеет значение `null`. |
  
## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: раскрывшемся](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
