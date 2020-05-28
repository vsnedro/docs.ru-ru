---
title: Метод IMetaDataEmit::SetHandler
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 4fa227d18b8cb10936d93fda9bcaf413ce63ca3b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003958"
---
# <a name="imetadataemitsethandler-method"></a>Метод IMetaDataEmit::SetHandler
Задает метод, на который ссылается указанный `IUnknown` указатель, в качестве обратного вызова уведомления для повторного сопоставления токена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pUnk`  
 окне Регистрируемый обработчик.  
  
## <a name="remarks"></a>Примечания  
 Обработчик метаданных отправляет уведомление с помощью метода, предоставляемого `SetHandler` , компиляторам, которые не создают записи оптимизированным образом и хотели бы оптимизировать сохраненные записи.  
  
 Если метод обратного вызова не предоставляется через `SetHandler` , то для сохранения не будет выполняться оптимизация, за исключением случаев, когда для каждой области были объединены несколько областей импорта с использованием `IMapToken` On MERGE.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
