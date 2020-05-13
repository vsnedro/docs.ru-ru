---
title: Функция CreateDebuggingInterfaceFromVersion Silverlight
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: f40345b09cae164660711b987f62130518736518
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208628"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>Функция CreateDebuggingInterfaceFromVersion Silverlight

Принимает строку версии среды CLR, возвращаемую [функцией CreateVersionStringFromModule](createversionstringfrommodule-function.md), и возвращает соответствующий интерфейс отладчика (как правило, [ICorDebug](icordebug-interface.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szDebuggeeVersion`\
 окне Строка версии среды CLR в целевом отлаживаемом объекте, возвращаемом [функцией CreateVersionStringFromModule](createversionstringfrommodule-function.md).  
  
 `ppCordb`\
 [out] Указатель на COM-объект (`IUnknown`). Перед возвращением этот объект будет приведен к объекту [ICorDebug](icordebug-interface.md) .  
  
## <a name="return-value"></a>Возвращаемое значение

 `S_OK`\
 `ppCordb`ссылается на допустимый объект, реализующий интерфейс [интерфейса ICorDebug](icordebug-interface.md) .  
  
 `E_INVALIDARG`\
 Либо `szDebuggeeVersion`, либо `ppCordb` имеет значение null.  
  
 `CORDBG_E_DEBUG_COMPONENT_MISSING`\
 Не удалось найти компонент, который необходим для отладки среды CLR. _Mscordbi. dll_ или _мскордаккоре. dll_ не найдены в том же каталоге, что и Целевая библиотека CoreCLR. dll.  
  
 `CORDBG_E_INCOMPATIBLE_PROTOCOL`\
 Версия mscordbi.dll или mscordaccore.dll не совпадает с версией целевого объекта CoreCLR.dll.  
  
 `E_FAIL`(или другие `E_` коды возврата) \
 Не удалось вернуть [Интерфейс ICorDebug](icordebug-interface.md).  
  
## <a name="remarks"></a>Remarks

 Возвращаемый интерфейс предоставляет средства для подключения к среде CLR в целевом процессе и отладки управляемого кода, который выполняется в этой среде CLR.  
  
## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** dbgshim. h  
  
 **Библиотека:** dbgshim. dll  
  
 **.NET Framework версии:** 3,5 SP1
