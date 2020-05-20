---
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
ms.openlocfilehash: 6fe8c3266a8c9a52cd1022589cd68485c4326fd1
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442193"
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
  
## <a name="remarks"></a>Комментарии  
 Метод [ибиндингдисплай:: инитиализефорпроцесс](ibindingdisplay-initializeforprocess-method.md) должен быть ранее успешно завершен, и программа должна быть остановлена отладчиком.  
  
 Вызывающий объект должен освободить возвращенную `SAFEARRAY` память с помощью [сафеаррайдестрой](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Биндингдисплай. h  
  
 **Библиотека:** Биндингдисплай. idl  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс IBindingDisplay](ibindingdisplay-interface.md)
- [Метод InitializeForProcess](ibindingdisplay-initializeforprocess-method.md)
