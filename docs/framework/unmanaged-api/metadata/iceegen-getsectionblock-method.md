---
description: 'Дополнительные сведения о методе ICeeGen:: Жетсектионблокк'
title: Метод ICeeGen::GetSectionBlock
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: d1a9fdeb35507f9dd6528b581be877049d2a1478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721149"
---
# <a name="iceegengetsectionblock-method"></a>Метод ICeeGen::GetSectionBlock

Возвращает блок базы кода.  
  
 Этот метод устарел и не должен использоваться.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a>Параметры  

 `section`  
 окне Раздел, из которого извлекается блок базы кода.  
  
 `len`  
 окне Длина извлекаемого блока.  
  
 `align`  
 окне Байт относительно начала раздела, с которым будет выравняться первый байт блока. Это расположение блока в разделе.  
  
 `ppBytes`  
 заполняет Указатель на расположение, которое получает адрес полученного блока.  
  
## <a name="remarks"></a>Remarks  

 Вызывайте `GetSectionBlock` только при наличии особых требований к разделам, которые не обрабатываются другими методами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICeeGen](iceegen-interface.md)
