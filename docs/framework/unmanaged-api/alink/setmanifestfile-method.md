---
title: Метод SetManifestFile
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
ms.openlocfilehash: a4518e93db887dbdc4397636479be8bf5a705c2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733728"
---
# <a name="setmanifestfile-method"></a>Метод SetManifestFile

Позволяет указать или сбросить файл манифеста, используемый компоновщиком при создании сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `pszFile`  
  
 Имя файла манифеста, содержимое которого помещается в большой двоичный объект Win32 Resources.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="remarks"></a>Комментарии  

 Вызовите этот метод, прежде чем запрашивать Win32ResBlob. Значение `pszFile` параметра — это имя файла манифеста, содержимое которого считывается и помещается в ресурсы Win32 с идентификатором RT_MANIFEST. При вызове с помощью параметра NULL все ранее прочитанные манифесты очищаются. Это позволяет сбросить состояние компоновщика до значения времени инициализации.  
  
## <a name="requirements"></a>Требования  

 Требуется aLink. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IALink3](ialink3-interface.md)
- [API ALink](index.md)
- [Интерфейс IALink](ialink-interface.md)
- [Al.exe (компоновщик сборок)](../../tools/al-exe-assembly-linker.md)
