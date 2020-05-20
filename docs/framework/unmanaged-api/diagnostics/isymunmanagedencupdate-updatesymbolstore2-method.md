---
title: Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
ms.openlocfilehash: f363bed8e7002bf898755b434c919f8722dea3fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614504"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2
Позволяет компилятору опускать функции, которые не были изменены из потока базы данных программы (PDB), при условии, что сведения о строке соответствуют требованиям. Правильная информация о строке может быть определена со старыми сведениями о строке PDB и одной разностью для всех строк в функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a>Параметры  
 `pIStream`  
 окне Указатель на объект [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , содержащий сведения о строке.  
  
 `pDeltaLines`  
 окне Указатель на структуру [SYMLINEDELTA](symlinedelta-structure.md) , содержащую измененные строки.  
  
 `cDeltaLines`  
 окне Объект `ULONG` , представляющий число измененных строк.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ISymUnmanagedENCUpdate](isymunmanagedencupdate-interface.md)
