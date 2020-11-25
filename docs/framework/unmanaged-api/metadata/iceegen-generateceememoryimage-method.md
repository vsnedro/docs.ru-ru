---
title: Метод ICeeGen::GenerateCeeMemoryImage
ms.date: 03/30/2017
api_name:
- ICeeGen.GenerateCeeMemoryImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GenerateCeeMemoryImage
helpviewer_keywords:
- ICeeGen::GenerateCeeMemoryImage method [.NET Framework metadata]
- GenerateCeeMemoryImage method [.NET Framework metadata]
ms.assetid: b3847495-0ae6-4a72-b496-65ce2424afc6
topic_type:
- apiref
ms.openlocfilehash: 69c4a64dee0eb12481a78aa6f185ab568266ee30
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715403"
---
# <a name="iceegengenerateceememoryimage-method"></a>Метод ICeeGen::GenerateCeeMemoryImage

Создает изображение в памяти для базы кода.  
  
 Этот метод устарел и не должен использоваться.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GenerateCeeMemoryImage (  
    [out] void    **ppImage  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppImage`  
 заполняет Указатель на созданное изображение.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICeeGen](iceegen-interface.md)
