---
title: Функция Ресетсекурити (Справочник по неуправляемым API)
description: Функция Ресетсекурити назначает маркер олицетворения текущему потоку.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 259bef74356f16221f1453dd4086e2fbb26faa83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721118"
---
# <a name="resetsecurity-function"></a>Функция ResetSecurity

Назначает предоставленный маркер олицетворения текущему потоку.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a>Параметры

`token`  
окне Токен олицетворения, связываемый с текущим потоком. Это значение может быть равно `null`.

## <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение равно `S_OK` (0).

Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки. Чтобы получить расширенные сведения об ошибке, вызовите функцию [жетерроринфо](geterrorinfo.md) .
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
