---
title: Функция Клонинумвбемклассобжект (Справочник по неуправляемым API)
description: Функция Клонинумвбемклассобжект создает логическую копию перечислителя.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fa8a7f436c018e3e083be452d300eb21e17f93f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708131"
---
# <a name="cloneenumwbemclassobject-function"></a>Функция CloneEnumWbemClassObject

Создает логическую копию перечислителя, сохраняя текущую позицию в перечислении.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum,
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject,
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority
);
```

## <a name="parameters"></a>Параметры

`ppEnum`\
заполняет Получает указатель на новый [иенумвбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`\
окне Уровень авторизации.

`impLevel`\
окне Уровень олицетворения.

`pCurrentEnumWbemClassObject`\
заполняет Указатель на экземпляр [иенумвбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) для клонирования.

`strUser`\
окне Имя пользователя. Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .

`strPassword`\
окне Пароль. Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .

`strAuthority`\
окне Доменное имя пользователя. Дополнительные сведения см. в описании функции [коннектсервервми](connectserverwmi.md) .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Не удалось создать ссылку на удаленный вызов процедур (RPC) между текущим процессом и WMI. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |

## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [иенумвбемклассобжект:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .

Этот метод делает только «наилучшую» копию. Из-за динамической природы многих объектов CIM возможно, что новый перечислитель не перечисляет тот же набор объектов, что и перечислитель источника.

Если вызов функции завершается неудачно, можно получить дополнительные сведения об ошибке, вызвав функцию [жетерроринфо](geterrorinfo.md) .

## <a name="example"></a>Пример

Пример см. в описании метода [иенумвбемклассобжект:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

 **Заголовок:** WMINet_Utils. idl

 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
