---
description: 'Дополнительные сведения о методе: Ибиндингдисплай:: Жеткуррентдисплай'
title: Метод IBindingDisplay::GetCurrentDisplay
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: 680a91c8025ac3247701c14c23f442da5e304ecb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800426"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a>Метод IBindingDisplay::GetCurrentDisplay

Возвращает текущие отображаемые сведения о привязке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `display`  
 [out, retval] Указатель на массив SafeArray, содержащий сведения, отображаемые при привязке.  
  
## <a name="remarks"></a>Remarks  

 Метод [ибиндингдисплай:: инитиализефорпроцесс](ibindingdisplay-initializeforprocess-method.md) должен быть ранее успешно завершен, и программа должна быть остановлена отладчиком.  
  
 Вызывающий объект должен освободить возвращенную `SAFEARRAY` память с помощью [сафеаррайдестрой](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Биндингдисплай. h  
  
 **Библиотека:** Биндингдисплай. idl  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IBindingDisplay](ibindingdisplay-interface.md)
- [Метод InitializeForProcess](ibindingdisplay-initializeforprocess-method.md)
