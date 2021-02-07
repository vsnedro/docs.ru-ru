---
description: 'Дополнительные сведения о методе: Исимунманажедасинкмесод:: Жетасинкстепинфо'
title: Метод ISymUnmanagedAsyncMethod::GetAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: dc255323f103b3422b927b0489402b24767dcd92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737848"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a>Метод ISymUnmanagedAsyncMethod::GetAsyncStepInfo

См. раздел [метод дефинеасинкстепинфо](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает `HRESULT`.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedAsyncMethod](isymunmanagedasyncmethod-interface.md)
