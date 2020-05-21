---
title: Метод ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 7874424150e0f4e1818ad9c72e31fd584e016829
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762400"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>Метод ICorConfiguration::SetGCThreadControl
Задает интерфейс обратного вызова для потоков планирования для задач, не относящихся к среде выполнения, которые в противном случае были бы заблокированы для сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pGCThreadControl`  
 окне Указатель на объект [IGCThreadControl](igcthreadcontrol-interface.md) , который уведомляет основное приложение о приостановке потоков для задач, не относящихся к среде выполнения.  
  
## <a name="remarks"></a>Комментарии  
 Узел может выбрать один из обратных вызовов [IGCThreadControl:: среадисблоккингфорсуспенсион](igcthreadcontrol-threadisblockingforsuspension-method.md) , следует ли перепланировать поток.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorConfiguration](icorconfiguration-interface.md)
