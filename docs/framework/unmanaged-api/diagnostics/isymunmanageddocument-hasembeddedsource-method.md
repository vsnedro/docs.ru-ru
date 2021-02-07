---
description: 'Дополнительные сведения о методе: ISymUnmanagedDocument:: Хасембеддедсаурце'
title: Метод ISymUnmanagedDocument::HasEmbeddedSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: fcab83fea65d9a9e483bff9d2d75714c233718eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710131"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a>Метод ISymUnmanagedDocument::HasEmbeddedSource

Возвращает `true` , если документ имеет исходный код, внедренный в отладочные символы; в противном случае возвращает `false` .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `pRetVal`  
 заполняет Указатель на переменную, которая указывает, имеет ли документ исходный код, внедренный в отладочные символы.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен.  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedDocument](isymunmanageddocument-interface.md)
