---
title: Интерфейс ICorDebugAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
ms.openlocfilehash: 140e67417f4fad552f972a93bc8c620b440b2370
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895171"
---
# <a name="icordebugappdomain-interface"></a>Интерфейс ICorDebugAppDomain

Предоставляет методы для отладки доменов приложения. Этот интерфейс является подклассом ICorDebugController.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Attach](icordebugappdomain-attach-method.md)|Присоединяет отладчик к домену приложения.|  
|[Метод EnumerateAssemblies](icordebugappdomain-enumerateassemblies-method.md)|Возвращает перечислитель для сборок в домене приложения.|  
|[Метод EnumerateBreakpoints](icordebugappdomain-enumeratebreakpoints-method.md)|Возвращает перечислитель для всех активных точек останова в домене приложения.|  
|[Метод EnumerateSteppers](icordebugappdomain-enumeratesteppers-method.md)|Возвращает перечислитель для всех активных шагов в домене приложения.|  
|[Метод GetId](icordebugappdomain-getid-method.md)|Возвращает уникальный идентификатор домена приложения.|  
|[Метод GetModuleFromMetaDataInterface](icordebugappdomain-getmodulefrommetadatainterface-method.md)|Возвращает объект ICorDebugModule с заданным интерфейсом метаданных.|  
|[Метод GetName](icordebugappdomain-getname-method.md)|Возвращает имя домена приложения.|  
|[Метод GetObject](icordebugappdomain-getobject-method.md)|Возвращает указатель интерфейса на домен приложения среды CLR.|  
|[Метод GetProcess](icordebugappdomain-getprocess-method.md)|Возвращает процесс, содержащий домен приложения.|  
|[Метод IsAttached](icordebugappdomain-isattached-method.md)|Определяет, присоединен ли отладчик к домену приложения.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
