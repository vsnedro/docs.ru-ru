---
description: Дополнительные сведения о функции Креатеалинк
title: Функция CreateALink
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
ms.openlocfilehash: cf34ae8d38a8339f539c770df8f5dd14e4a3e4b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638370"
---
# <a name="createalink-function"></a>Функция CreateALink

Создает экземпляр компоновщика сборок и задает указатель на указанный интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`riid`|Физическое имя одного из интерфейсов компоновщика сборок.|  
|`ppInterface`|Расположение, которое в случае успешного завершения содержит указатель на `riid` интерфейс.|  
  
## <a name="requirements"></a>Требования  

 **Библиотека**: alink.dll  
  
## <a name="see-also"></a>См. также

- [Al.exe (компоновщик сборок)](../../tools/al-exe-assembly-linker.md)
