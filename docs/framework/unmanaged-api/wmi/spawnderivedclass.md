---
title: Функция Спавндериведкласс (Справочник по неуправляемым API)
description: Функция Спавндериведкласс создает новый объект, производный от объекта.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 8020dd851b6773e6c76c53892c4b2bc21e4261bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716516"
---
# <a name="spawnderivedclass-function"></a>Функция SpawnDerivedClass

Создает объект производного класса из указанного объекта.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`ppNewClass`  
заполняет Получает указатель на новый объект определения класса. При возникновении ошибки новый объект не возвращается и остается `ppNewClass` неизменным. Его значение не может быть `null` .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Общий сбой. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Запрошена Недопустимая операция, например порождение класса из экземпляра. |
| `WBEM_E_INCOMPLETE_CLASS` | Исходный класс не был полностью определен или зарегистрирован в управлении Windows, поэтому новый производный класс не разрешен. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для выполнения операции. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` имеет значение `null`. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: спавндериведкласс](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .

`ptr` должно быть определением класса, который станет родительским классом порожденного объекта. Возвращаемый объект превращается в подкласс текущего объекта.

Новый объект, возвращенный в `ppNewClass` , автоматически станет подклассом текущего объекта. Это поведение не может быть переопределено. Нет других методов, с помощью которых можно создать подклассы (производные классы).

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
