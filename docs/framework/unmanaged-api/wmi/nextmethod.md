---
title: Функция Некстмесод (Справочник по неуправляемым API)
description: Функция Некстмесод извлекает следующий метод в перечислении.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a0466aee47b0a6142870640c78b43f49e221ac2b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726773"
---
# <a name="nextmethod-function"></a>Функция NextMethod

Извлекает следующий метод в перечислении, который начинается с вызова [бегинмесоденумератион](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`pName`  
заполняет Указатель, указывающий на `null` перед вызовом. Когда функция возвращает, адрес нового `BSTR` , который содержит имя метода.

`ppSignatureIn`  
заполняет Указатель, получающий указатель на объект [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий `in` параметры для метода.

`ppSignatureOut`  
заполняет Указатель, получающий указатель на объект [ивбемклассобжект](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , содержащий `out` параметры для метода.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Нет вызова [`BeginEnumeration`](beginenumeration.md) функции. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | В перечислении больше нет свойств. |
  
## <a name="remarks"></a>Комментарии

Эта функция заключает в оболочку вызов метода [ивбемклассобжект:: некстмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

Вызывающий объект начинает последовательность перечисления, вызывая функцию [бегинмесоденумератион](beginmethodenumeration.md) , а затем вызывает функцию [некстмесод] до тех пор, пока функция не вернет значение `WBEM_S_NO_MORE_DATA` . При необходимости вызывающий объект завершает последовательность путем вызова [ендмесоденумератион](endmethodenumeration.md). Вызывающий объект может завершить перечисление раньше, вызвав [ендмесоденумератион](endmethodenumeration.md) в любое время.

## <a name="example"></a>Пример

Пример для C++ см. в описании метода [ивбемклассобжект:: некстмесод](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
