---
title: Метод IBindingDisplay::InitializeForProcess
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
ms.openlocfilehash: f9e65b49c9a3b506cba3493d81a40f2759dca781
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725155"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>Метод IBindingDisplay::InitializeForProcess

Инициализирует объект [ибиндингдисплай](ibindingdisplay-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pid`  
 окне Идентификатор процесса.  
  
## <a name="remarks"></a>Комментарии  

 Отладчик вызывает `InitializeForProcess` метод во время создания, чтобы инициализировать отображение привязки. `InitializeForProcess` должен вызываться во время создания до вызова любого другого метода `IBindingDisplay` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Биндингдисплай. h  
  
 **Библиотека:** Биндингдисплай. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IBindingDisplay](ibindingdisplay-interface.md)
