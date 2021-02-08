---
description: Дополнительные сведения о функции Креатекордбобжект
title: Функция CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: b6a585fc89f780b22f842127e1923414dbb8230f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801479"
---
# <a name="createcordbobject-function"></a>Функция CreateCordbObject

Создает интерфейс отладчика ([ICorDebug](icordebug-interface.md)), который предоставляет функциональные возможности для создания экземпляра управляемого сеанса отладки на удаленном процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `iDebuggerVersion`  
 [in] Версия отладчика целевого процесса. Для удаленной отладки этот параметр должен иметь значение CorDebugVersion_2_0.  
  
 `ppCordb`  
 заполняет Указатель на указатель на объект, который будет приведен к интерфейсу [ICorDebug](icordebug-interface.md) и возвращен.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK  
 Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.  
  
 E_INVALIDARG  
 Параметр `ppCordb` имеет значение null, или параметр `iDebuggerVersion` не имеет значение CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 Не удается выделить достаточно памяти для `ppCordb`.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="remarks"></a>Remarks  

 Интерфейс [ICorDebug](icordebug-interface.md) , возвращаемый в, `ppCordb` является интерфейсом отладки верхнего уровня для всех управляемых служб отладки.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Кореклрремотедебуггингинтерфацес. h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **Платформа .NET Framework версии:** 3,5 SP1
