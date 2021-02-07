---
description: 'Дополнительные сведения о методе: ICorPublish:: EnumProcesses'
title: Метод ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 2451f179301eff4caca966568f966d145e269f51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722000"
---
# <a name="icorpublishenumprocesses-method"></a>Метод ICorPublish::EnumProcesses

Возвращает перечислитель для управляемых процессов, выполняющихся на этом компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `Type`  
 Значение перечисления [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) , указывающее тип получаемого процесса. В текущей версии допускается только COR_PUB_MANAGEDONLY.  
  
 `ppIEnum`  
 Указатель на адрес экземпляра [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) , который является перечислителем процессов.  
  
## <a name="remarks"></a>Remarks  

 Коллекция процессов перечислителя основана на моментальном снимке процессов, выполняемых при `EnumProcesses` вызове метода. Перечислитель не будет включать процессы, которые завершаются до или запуска после `EnumProcesses` вызова.  
  
 `EnumProcesses`Метод может быть вызван более одного раза в этом экземпляре [ICorPublish](icorpublish-interface.md) для создания новой актуальной коллекции процессов. Последующие вызовы метода не будут затронуты существующими коллекциями `EnumProcesses` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorPublish](icorpublish-interface.md)
