---
title: Метод IMapToken::Map
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
ms.openlocfilehash: 027694cee1b3e4d990796ba31300918f6d859679
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008200"
---
# <a name="imaptokenmap-method"></a>Метод IMapToken::Map
Сопоставляет связь между сборками, используя подписи метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tkImp`  
 окне Токен метаданных, представляющий импортированный объект кода.  
  
 `tkEmit`  
 окне Токен метаданных, представляющий созданный объект кода.  
  
## <a name="remarks"></a>Примечания  
 Когда повторное отображение токена происходит во время слияния, исходный маркер ограничивается в импортированной (исходной) области метаданных, а новый маркер — в области исрожденных (целевых) метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMapToken](imaptoken-interface.md)
