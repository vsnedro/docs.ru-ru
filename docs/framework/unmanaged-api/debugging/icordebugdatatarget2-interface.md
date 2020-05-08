---
title: Интерфейс ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 1c598d23cac77e50cf302e6936b88b5eb6e558c2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976439"
---
# <a name="icordebugdatatarget2-interface"></a>Интерфейс ICorDebugDataTarget2
Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateVirtualUnwinder](icordebugdatatarget2-createvirtualunwinder-method.md)|Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).|  
|[Метод EnumerateThreadIDs](icordebugdatatarget2-enumeratethreadids-method.md)|Возвращает список идентификаторов активных потоков.|  
|[Метод GetImageFromPointer](icordebugdatatarget2-getimagefrompointer-method.md)|Возвращает базовый адрес и размер модуля из адреса в этом модуле.|  
|[Метод GetImageLocation](icordebugdatatarget2-getimagelocation-method.md)|Возвращает путь для модуля из базового адреса модуля.|  
|[Метод GetSymbolProviderForImage](icordebugdatatarget2-getsymbolproviderforimage-method.md)|Возвращает поставщика символов для модуля из базового адреса модуля.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
