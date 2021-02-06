---
description: 'Дополнительные сведения о методе: ICorDebugProcess2:: SetDesiredNGENCompilerFlags'
title: Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 3a4749ad26e88d1a602876f28a52754323093fce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650106"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags

Задает флаги, которые должны быть внедрены в предкомпилированное изображение, чтобы среда выполнения загружала этот образ в текущий процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pdwFlags`  
 окне Значение перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) , указывающее флаги компилятора, используемые для выбора правильного предварительно скомпилированного изображения.  
  
## <a name="remarks"></a>Remarks  

 `SetDesiredNGENCompilerFlags`Метод задает флаги, которые должны быть внедрены в предкомпилированное изображение, чтобы среда выполнения загружала этот образ в этот процесс. Флаги, заданные этим методом, используются только для выбора правильного предкомпилированного изображения. Если такого образа не существует, среда выполнения загрузит образ MSIL и JIT-компилятор, вместо этого. В этом случае отладчик должен по-прежнему использовать метод [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) , чтобы установить флаги для JIT-компиляции.  
  
 Если изображение загружено, но для этого образа необходимо выполнить некоторые JIT-компиляции (что будет так, если изображение содержит универсальные шаблоны), то флаги компилятора, заданные в `SetDesiredNGENCompilerFlags` методе, будут применяться к дополнительной JIT-компиляции.  
  
 `SetDesiredNGENCompilerFlags`Метод должен вызываться во время обратного вызова [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . Попытки вызвать `SetDesiredNGENCompilerFlags` метод позже завершатся ошибкой. Кроме того, пытается установить флаги, которые либо не определены в `CorDebugJITCompilerFlags` перечислении, либо не являются допустимыми для данного процесса.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](icordebug-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
