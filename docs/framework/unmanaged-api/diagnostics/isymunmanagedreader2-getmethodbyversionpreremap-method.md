---
title: Метод ISymUnmanagedReader2::GetMethodByVersionPreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: 5484242562deaf463b7435ad4e54735a7abee45e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730491"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a>Метод ISymUnmanagedReader2::GetMethodByVersionPreRemap

Возвращает метод чтения символов по заданному маркеру метода и номеру версии "изменить и продолжить". Номера версий начинаются с 1 и увеличиваются каждый раз при изменении метода в результате операции "изменить и продолжить".  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `token`  
 окне Токен метаданных метода.  
  
 `version`  
 окне Версия метода.  
  
 `pRetVal`  
 заполняет Указатель на возвращаемый интерфейс [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl. Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedReader2](isymunmanagedreader2-interface.md)
