---
description: 'Дополнительные сведения о: интерфейс ICorDebugILFrame'
title: Интерфейс ICorDebugILFrame
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 251fa18151ff286bee3e1bcf7707bf5f7145b4f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791365"
---
# <a name="icordebugilframe-interface"></a>Интерфейс ICorDebugILFrame

Представляет кадр стека кода промежуточного языка MSIL. Этот интерфейс является подклассом интерфейса ICorDebugFrame.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanSetIP](icordebugilframe-cansetip-method.md)|Возвращает значение, указывающее, можно ли задать для указателя инструкции заданное расположение смещения.|  
|[Метод EnumerateArguments](icordebugilframe-enumeratearguments-method.md)|Возвращает перечислитель для аргументов в этом кадре.|  
|[Метод EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)|Возвращает перечислитель для локальных переменных в этом кадре.|  
|[Метод GetArgument](icordebugilframe-getargument-method.md)|Возвращает значение указанного аргумента в этом кадре стека MSIL.|  
|[Метод GetIP](icordebugilframe-getip-method.md)|Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.|  
|[Метод GetLocalVariable](icordebugilframe-getlocalvariable-method.md)|Возвращает значение указанной локальной переменной в этом кадре стека MSIL.|  
|[Метод GetStackDepth](icordebugilframe-getstackdepth-method.md)|Не реализован.|  
|[Метод GetStackValue](icordebugilframe-getstackvalue-method.md)|Не реализован.|  
|[Метод SetIP](icordebugilframe-setip-method.md)|Устанавливает указатель инструкции на указанное положение смещения в коде MSIL.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugILFrame`Интерфейс является специализированным интерфейсом ICorDebugFrame. Он используется либо для кадров кода MSIL, либо для кадров, скомпилированных JIT. JIT-скомпилированные кадры реализуют `ICorDebugILFrame` интерфейс и интерфейс ICorDebugNativeFrame.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
