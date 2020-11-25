---
title: Функция Блессивбемсервицес (Справочник по неуправляемым API)
description: Функция Блессивбемсервицес указывает, допускают ли учетные данные пользователя доступ к классу IWbemServices.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 43ef617ee754c9dcd661b31abba6b17434563c22
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708157"
---
# <a name="blessiwbemservices-function"></a>Функция BlessIWbemServices

Указывает, допускают ли учетные данные пользователя доступ к указанному классу [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) .
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a>Параметры

`pIWbemServices`\
окне Указатель на объект [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) , для которого требуются разрешения.

`strUser`\
окне Имя пользователя.

`strPassword`\
окне Пароль, связанный с `strUser` .

`strAuthority`\
окне Доменное имя пользователя. Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .

`impLevel`\
окне Уровень олицетворения.

`authnLevel`\
окне Уровень авторизации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *Winerror. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Один или несколько аргументов недопустимы. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` имеет значение `null`. |
| `E_FAIL` | 0x80000008 | Возникла неопределенная ошибка. |
| `E_OUTOFMEMORY` | 0x80000002 | Недостаточно свободной памяти для выполнения операции. |
| `S_OK` | 0 | Вызов функции выполнен успешно. |

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
