---
description: 'Дополнительные сведения о методе: ICorDebugNativeFrame2:: GetStackParameterSize'
title: Метод ICorDebugNativeFrame2::GetStackParameterSize
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
ms.openlocfilehash: 08a17ced0be75737c1c49aa3f9bb42b13bbe8aa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722338"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>Метод ICorDebugNativeFrame2::GetStackParameterSize

Возвращает совокупный размер параметров в стеке в операционных системах x86.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a>Параметры  

 `pSize`  
 заполняет Указатель на совокупный размер параметров в стеке.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Размер стека успешно возвращен.|  
|S_FALSE|`GetStackParameterSize` был вызван на платформе, отличной от x86.|  
|E_FAIL|`The size of the parameters could not be returned`.|  
|E_INVALIDARG|`pSize` Имеет `null` .|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  

 Методы [икордебугстакквалк](icordebugstackwalk-interface.md) не настраивают указатель стека для параметров, помещаемых в стек. Вместо этого можно использовать значение, возвращаемое методом, `GetStackParameterSize` чтобы настроить указатель стека на заполнение собственного, неуправляемого кода, который корректируется для параметров.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
