---
description: 'Дополнительные сведения о методе: ISymUnmanagedWriter::D Ефинедокумент'
title: Метод ISymUnmanagedWriter::DefineDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
ms.openlocfilehash: 35e918292e6ee50e17932645e003d19513e2397a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762543"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a>Метод ISymUnmanagedWriter::DefineDocument

Определяет исходный документ. Идентификаторы GUID предоставляются для известных языков, поставщиков и типов документов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `url`  
 окне Указатель на объект `WCHAR` , который определяет универсальный указатель ресурсов (URL-адрес), определяющий документ.  
  
 `language`  
 окне Указатель на идентификатор GUID, определяющий язык документа.  
  
 `languageVendor`  
 окне Указатель на идентификатор GUID, определяющий удостоверение поставщика для языка документа.  
  
 `documentType`  
 окне Указатель на идентификатор GUID, определяющий тип документа.  
  
 `pRetVal`  
 заполняет Указатель на возвращаемый интерфейс [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
