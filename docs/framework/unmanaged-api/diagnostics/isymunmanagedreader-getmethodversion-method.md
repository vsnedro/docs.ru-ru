---
description: 'Дополнительные сведения о методе: ISymUnmanagedReader:: GetMethodVersion'
title: Метод ISymUnmanagedReader::GetMethodVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: 027f65f858aab3e4ad0bc0bfbffd91f6118b80b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764025"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a>Метод ISymUnmanagedReader::GetMethodVersion

Возвращает версию метода. Версия метода начинается с 1 и увеличивается каждый раз при повторной компиляции метода. Перекомпиляция может произойти без изменения метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a>Параметры  

 `pMethod`  
 окне Метод, для которого необходимо получить версию.  
  
 `version`  
 заполняет Указатель на переменную, которая получает версию метода.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
