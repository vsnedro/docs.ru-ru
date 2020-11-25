---
title: Метод ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: 636d0fd25d345f513e00504b9eb5adb4f0c03b0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710653"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a>Метод ICorDebugMergedAssemblyRecord::GetCulture

Возвращает строку с названием языка и региональных параметров сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cchCulture`  
 [in] Число символов в буфере `szCulture`.  
  
 `pcchCulture`  
 [выходной] Число символов, фактически записанных в буфер `szCulture`.  
  
 `szCulture`  
 [выходной] Массив символов, содержащий название языка и региональных параметров.  
  
## <a name="remarks"></a>Комментарии  

 Название языка и региональных параметров — это уникальная строка, определяющая язык и региональные параметры, например "en-US" (для английского языка (США)) или "neutral" (для нейтрального языка и региональных параметров).  
  
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
