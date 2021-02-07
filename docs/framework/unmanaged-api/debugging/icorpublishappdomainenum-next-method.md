---
description: 'Дополнительные сведения о методе: ICorPublishAppDomainEnum:: Next'
title: Метод ICorPublishAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: 8e8255aa2326c6f0678132f5735d6cdf504dcbd0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721727"
---
# <a name="icorpublishappdomainenumnext-method"></a>Метод ICorPublishAppDomainEnum::Next

Возвращает указанное количество доменов приложений, которые в данный момент существуют в процессе, начиная с текущей позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `celt`  
 окне Число извлекаемых элементов.  
  
 `objects`  
 заполняет Указатель на массив полученных объектов [ICorPublishAppDomain](icorpublishappdomain-interface.md) , каждый из которых представляет домен приложения.  
  
 `pceltFetched`  
 заполняет Указатель на число фактически возвращенных доменов приложений. Это значение может быть равно NULL `celt` , если равно единице.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)
