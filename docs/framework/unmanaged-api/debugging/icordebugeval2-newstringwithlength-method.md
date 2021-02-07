---
description: 'Дополнительные сведения о методе: ICorDebugEval2:: NewStringWithLength'
title: Метод ICorDebugEval2::NewStringWithLength
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
ms.openlocfilehash: 23864dabefcb4fc12f73c66bc2d19a6cca1aacf0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693529"
---
# <a name="icordebugeval2newstringwithlength-method"></a>Метод ICorDebugEval2::NewStringWithLength

Создает строку указанной длины с указанным содержимым.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `string`  
 окне Указатель на строковое значение.  
  
 `uiLength`  
 окне Длина строки.  
  
## <a name="remarks"></a>Remarks  

 Если конечный нуль-символ строки должен быть в управляемой строке, вызывающий `NewStringWithLength` метод должен обеспечить, чтобы длина строки включала завершающий нуль-символ.  
  
 Строка всегда создается в домене приложения, в котором в данный момент выполняется поток.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
