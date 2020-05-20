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
ms.openlocfilehash: 8645878132359b6218cd62b1ff707208de53704b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442154"
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
 Отладчик вызывает `InitializeForProcess` метод во время создания, чтобы инициализировать отображение привязки. `InitializeForProcess`должен вызываться во время создания до вызова любого другого метода `IBindingDisplay` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Биндингдисплай. h  
  
 **Библиотека:** Биндингдисплай. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс IBindingDisplay](ibindingdisplay-interface.md)
