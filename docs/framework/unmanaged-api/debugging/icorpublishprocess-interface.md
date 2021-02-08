---
description: 'Дополнительные сведения о: интерфейс ICorPublishProcess'
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
ms.openlocfilehash: 8dbc619d33c2c9b625dde852948dff00b5be926e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800881"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Кокласс CorpubPublish](corpubpublish-coclass.md)
