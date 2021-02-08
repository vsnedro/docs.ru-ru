---
description: 'Дополнительные сведения о методе: ICorPublishProcess:: Енумаппдомаинс'
title: Метод ICorPublishProcess::EnumAppDomains
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: c7834b23967ab467c1589ee31929bf346b4b3b8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794615"
---
# <a name="icorpublishprocessenumappdomains-method"></a>Метод ICorPublishProcess::EnumAppDomains

Возвращает перечислитель для доменов приложений в процессе, на который ссылается этот [ICorPublishProcess](icorpublishprocess-interface.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppEnum`  
 заполняет Указатель на адрес экземпляра [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) , который позволяет выполнять итерацию по коллекции доменов приложений в этом процессе.  
  
## <a name="remarks"></a>Remarks  

 Список доменов приложений основан на моментальном снимке доменов приложений, существующих при `EnumAppDomains` вызове метода. Этот метод может быть вызван более одного раза для создания нового списка обновлений. Последующие вызовы этого метода не будут затронуты существующими списками.  
  
 Если процесс был завершен, `EnumAppDomains` произойдет сбой со ЗНАЧЕНИЕМ HRESULT CORDBG_E_PROCESS_TERMINATED.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)
