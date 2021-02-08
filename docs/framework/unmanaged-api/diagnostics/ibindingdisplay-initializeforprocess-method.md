---
description: 'Дополнительные сведения о методе: Ибиндингдисплай:: Инитиализефорпроцесс'
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
ms.openlocfilehash: cf7f0f4d057659089bd7da173e5fac98a7c00dad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800415"
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
  
## <a name="remarks"></a>Remarks  

 Отладчик вызывает `InitializeForProcess` метод во время создания, чтобы инициализировать отображение привязки. `InitializeForProcess` должен вызываться во время создания до вызова любого другого метода `IBindingDisplay` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Биндингдисплай. h  
  
 **Библиотека:** Биндингдисплай. idl  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IBindingDisplay](ibindingdisplay-interface.md)
