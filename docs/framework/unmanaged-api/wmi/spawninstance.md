---
title: Функция Спавнинстанце (Справочник по неуправляемым API)
description: Функция Спавнинстанце создает новый экземпляр класса.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 176bc83dd02381af8c2bc3995a37e7fee7c1bebf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732233"
---
# <a name="spawninstance-function"></a>Функция SpawnInstance

Создает экземпляр класса.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`ppNewInstance`  
заполняет Получает указатель на новый экземпляр класса. При возникновении ошибки новый объект не возвращается и остается `ppNewInstance` неизменным.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr` не является допустимым определением класса и не может порождать новые экземпляры. Либо он неполон, либо не зарегистрирован в службе управления Windows путем вызова [путклассвми](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для выполнения операции. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` имеет значение `null`. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: спавнинстанце](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) .

`ptr` должно быть определением класса, полученным из системы управления Windows. (Обратите внимание, что порождение экземпляра из экземпляра поддерживается, но возвращаемый экземпляр пуст.) Затем это определение класса используется для создания новых экземпляров. Вызов функции [путинстанцевми](putinstancewmi.md) требуется, если вы планируете записать экземпляр в Windows Management.

Новый объект, возвращенный в `ppNewClass` , автоматически станет подклассом текущего объекта. Это поведение не может быть переопределено. Нет других методов, с помощью которых можно создать подклассы (производные классы).

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
