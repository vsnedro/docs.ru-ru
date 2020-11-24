---
title: Функция GetALinkMessageDll
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 554bd32ae965b21a88a09577749bbd7975f5ec7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684750"
---
# <a name="getalinkmessagedll-function"></a>Функция GetALinkMessageDll

Находит и загружает библиотеку DLL сообщений. Возвращает 0, если не удалось обнаружить или загрузить библиотеку DLL сообщений. DLL сообщения должна быть либо в подкаталоге, имя которого является ИДЕНТИФИКАТОРом языка, либо в текущем каталоге.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** ALink. h  
  
 **Библиотека**: alink.dll  
  
## <a name="see-also"></a>См. также раздел

- [Al.exe (компоновщик сборок)](../../tools/al-exe-assembly-linker.md)
