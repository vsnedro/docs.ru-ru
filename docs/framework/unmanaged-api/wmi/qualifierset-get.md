---
title: Функция QualifierSet_Get (Справочник по неуправляемым интерфейсам API)
description: Функция QualifierSet_Get Возвращает именованный квалификатор.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fd096287b85b4a51a8cae85dddcca95cc1a8dbae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721144"
---
# <a name="qualifierset_get-function"></a>Функция QualifierSet_Get

Получает указанный именованный квалификатор.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a>Параметры

`vFunc` окне Этот параметр не используется.

`ptr` окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName` окне Имя квалификатора, значение которого запрашивается.

`lFlags` окне Процессу. Этот параметр должен иметь значение 0.

`pVal` заполняет При успешном выполнении, правильный тип и значение для квалификатора. Если функция завершается ошибкой, то, на `VARIANT` которую указывает, `pVal` не изменяется. Если этот параметр имеет значение `null` , параметр игнорируется.

`plFlavor` заполняет Указатель на значение типа LONG, которое получает биты флагов для запрошенного описателя. Если сведения о разновидностях не нужны, этот параметр может иметь значение `null` .

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недействительный параметр. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанный квалификатор не существует. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) .

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
