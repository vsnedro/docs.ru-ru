---
description: 'Подробнее о: Корпубпублиш coclass'
title: Кокласс CorpubPublish
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: fdf4be6ff2d20391e989998cd0045ed27d602561
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661705"
---
# <a name="corpubpublish-coclass"></a>Кокласс CorpubPublish

Предоставляет интерфейсы для публикации сведений о доменах приложений и процессах.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Интерфейс ICorPublish](icorpublish-interface.md)|Предоставляет методы для публикации сведений о процессах и доменах приложений в этих процессах.|  
|[Интерфейс ICorPublishAppDomain](icorpublishappdomain-interface.md)|Представляет и предоставляет сведения о домене приложения в процессе.|  
|[Интерфейс ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)|Предоставляет методы, которые проходят через коллекцию доменов приложений, которые в данный момент существуют в процессе.|  
|[Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)|Представляет процесс, выполняющийся на компьютере.|  
|[Интерфейс ICorPublishProcessEnum](icorpublishprocessenum-interface.md)|Предоставляет методы, которые проходят по коллекции процессов, выполняющихся на компьютере.|  
  
## <a name="remarks"></a>Remarks  

 Типичный сценарий публикации включает в себя разработчика, желающего отлаживать управляемый код, выполняющийся на компьютере в домене приложения. Среда размещения может запускать несколько доменов приложений в рамках одного процесса. Разработчику хотелось бы использовать графический пользовательский интерфейс или другие средства для перечисления всех процессов, запущенных на компьютере, и выбрать конкретный процесс. Список должен включать все домены приложений в процессах, выполняющих управляемый код. Затем разработчик может определить конкретный домен приложения и подключить к этому домену отладчик.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Отладка](index.md)
