---
title: Функция QualifierSet_EndEnumeration (Справочник по неуправляемым интерфейсам API)
description: Функция QualifierSet_EndEnumeration прерывает перечисление.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2739003fc9c1f93d379e4a59338cbef7a1a0f135
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726747"
---
# <a name="qualifierset_endenumeration-function"></a>Функция QualifierSet_EndEnumeration

Завершает перечисление, начатое вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr` окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

## <a name="return-value"></a>Возвращаемое значение

Следующее значение, возвращаемое этой функцией, определено в файле заголовка *вбемкли. h* , или его можно определить как константу в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .

Этот вызов рекомендуется, но не является обязательным. Он немедленно освобождает ресурсы, связанные с перечислением.

## <a name="requirements"></a>Требования  

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
**Заголовок:** WMINet_Utils. idl  
  
**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
