---
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
ms.openlocfilehash: 0c3b5da52b78150198fa9f910bf01b4657e4eba8
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421167"
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
  
## <a name="remarks"></a>Комментарии  
 Список доменов приложений основан на моментальном снимке доменов приложений, существующих при `EnumAppDomains` вызове метода. Этот метод может быть вызван более одного раза для создания нового списка обновлений. Последующие вызовы этого метода не будут затронуты существующими списками.  
  
 Если процесс был завершен, `EnumAppDomains` произойдет сбой со ЗНАЧЕНИЕМ HRESULT CORDBG_E_PROCESS_TERMINATED.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)
