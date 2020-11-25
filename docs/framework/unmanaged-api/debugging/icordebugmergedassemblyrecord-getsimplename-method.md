---
title: Метод ICorDebugMergedAssemblyRecord::GetSimpleName
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 11e43846f7b119933fb53bdf21423e28bbb792ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710549"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a>Метод ICorDebugMergedAssemblyRecord::GetSimpleName

Получает простое имя сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cchName`  
 [in] Число символов в буфере `szName`.  
  
 `pcchName`  
 [out] Указатель на число символов, фактически записанных в буфер `szName`.  
  
 `szName`  
 Указатель на массив символов.  
  
## <a name="remarks"></a>Комментарии  

 Этот метод возвращает простое имя сборки (например, System.Collections) без расширения имени файла, версии, языка и региональных параметров и токена открытого ключа. Оно соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> в управляемом коде.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
