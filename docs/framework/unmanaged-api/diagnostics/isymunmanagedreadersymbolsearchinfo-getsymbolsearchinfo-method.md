---
description: 'Дополнительные сведения о методе: ISymUnmanagedReaderSymbolSearchInfo:: Жетсимболсеарчинфо'
title: Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
ms.openlocfilehash: e14f78d6736684205b3f86150ce1fbb44a8112b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763609"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a>Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo

Возвращает сведения о поиске символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a>Параметры  

 `cSearchInfo`  
 окне Значение типа `ULONG32` , указывающее размер `rgpSearchInfo` .  
  
 `pcSearchInfo`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения сведений о поиске.  
  
 `rgpSearchInfo`  
 заполняет Указатель, которому присваивается возвращаемый интерфейс [исимунманажедсимболсеарчинфо](isymunmanagedsymbolsearchinfo-interface.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReaderSymbolSearchInfo](isymunmanagedreadersymbolsearchinfo-interface.md)
