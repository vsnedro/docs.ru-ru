---
description: 'Дополнительные сведения о: интерфейс ICorDebugReferenceValue'
title: Интерфейс ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: e516b1178b4f4268472dedd37d6443e673e16af6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690968"
---
# <a name="icordebugreferencevalue-interface"></a>Интерфейс ICorDebugReferenceValue

Предоставляет методы, управляющие значением, которое является ссылкой на объект. (Т. е. Этот интерфейс предоставляет методы, управляющие указателем.) Этот интерфейс реализует "ICorDebugValue".  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Dereference](icordebugreferencevalue-dereference-method.md)|Возвращает объект, на который указывает ссылка.|  
|[Метод DereferenceStrong](icordebugreferencevalue-dereferencestrong-method.md)|Не реализован. Этот метод не следует вызывать.|  
|[Метод GetValue](icordebugreferencevalue-getvalue-method.md)|Возвращает текущий адрес памяти объекта, на который указывает ссылка.|  
|[Метод IsNull](icordebugreferencevalue-isnull-method.md)|Возвращает значение, указывающее, является ли `ICorDebugReferenceValue` значение значением NULL, в этом случае, не `ICorDebugReferenceValue` указывает на объект.|  
|[Метод SetValue](icordebugreferencevalue-setvalue-method.md)|Задает текущий адрес памяти. Это значит, что этот метод задает `ICorDebugReferenceValue` значение, которое указывает на объект.|  
  
## <a name="remarks"></a>Remarks  

 Среда CLR может выполнять сборку мусора для объектов при продолжении отлаживаемого процесса. Сборка мусора может перемещать объекты в памяти. Либо взаимодействуют `ICorDebugReferenceValue` со сборкой мусора, так что ее сведения обновляются после сборки мусора, или же она становится неявной до сборки мусора.  
  
 `ICorDebugReferenceValue`После продолжения отлаживаемого процесса объект может быть неявно недействительным. Производный "ICorDebugHandleValue" не является недействительным до тех пор, пока он не будет явно освобожден или открыт.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
