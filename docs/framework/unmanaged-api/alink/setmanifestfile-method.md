---
description: Дополнительные сведения о методе SetManifestFile
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
ms.openlocfilehash: fe91c7f2b4e6f58a0a740de84e055ead49adb77d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662329"
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
  
## <a name="remarks"></a>Remarks  

 Вызовите этот метод, прежде чем запрашивать Win32ResBlob. Значение `pszFile` параметра — это имя файла манифеста, содержимое которого считывается и помещается в ресурсы Win32 с идентификатором RT_MANIFEST. При вызове с помощью параметра NULL все ранее прочитанные манифесты очищаются. Это позволяет сбросить состояние компоновщика до значения времени инициализации.  
  
## <a name="requirements"></a>Требования  

 Требуется aLink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink3](ialink3-interface.md)
- [API ALink](index.md)
- [Интерфейс IALink](ialink-interface.md)
- [Al.exe (компоновщик сборок)](../../tools/al-exe-assembly-linker.md)
