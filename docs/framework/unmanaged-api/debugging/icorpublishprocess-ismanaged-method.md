---
title: Метод ICorPublishProcess::IsManaged
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: dfe247bda75c3695c7c09b85729b4e057c13c62d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692635"
---
# <a name="icorpublishprocessismanaged-method"></a>Метод ICorPublishProcess::IsManaged

Возвращает значение, указывающее, известно ли для процесса, на который ссылается этот [ICorPublishProcess](icorpublishprocess-interface.md) , управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbManaged`  
 заполняет Указатель на логическое значение, указывающее, имеет ли процесс управляемый код. Значение равно `true` , если процесс имеет управляемый код; в противном случае — `false` .  
  
## <a name="remarks"></a>Комментарии  

 Поскольку текущая версия `ICorPublishProcess` разрешает доступ только к процессам, имеющим управляемый код, `IsManaged` всегда возвращает `true` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)
