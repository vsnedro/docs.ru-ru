---
title: Интерфейс ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8ee59e9d416d1c53312e4fccb6953f20b03b29b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693090"
---
# <a name="icorpublishprocess-interface"></a>Интерфейс ICorPublishProcess

Предоставляет методы, которые обращаются к сведениям, отображаемым в процессе.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumAppDomains](icorpublishprocess-enumappdomains-method.md)|Возвращает экземпляр [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) , содержащий домены приложений в процессе, на который ссылается this `ICorPublishProcess` .|  
|[Метод GetDisplayName](icorpublishprocess-getdisplayname-method.md)|Возвращает полный путь к исполняемому файлу для процесса, на который ссылается this `ICorPublishProcess` .|  
|[Метод GetProcessID](icorpublishprocess-getprocessid-method.md)|Возвращает идентификатор операционной системы для процесса, на который ссылается this `ICorPublishProcess` .|  
|[Метод IsManaged](icorpublishprocess-ismanaged-method.md)|Возвращает значение, указывающее, называется ли процесс, на который ссылается данный объект, `ICorPublishProcess` выполнением управляемого кода.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Кокласс CorpubPublish](corpubpublish-coclass.md)
