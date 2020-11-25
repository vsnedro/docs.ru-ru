---
title: Перечисление CorSymSearchPolicyAttributes
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 2d5d19fb3fb7c727227827dacbaac2c910ac8b3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725226"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>Перечисление CorSymSearchPolicyAttributes

Указывает политику, используемую при поиске средства чтения символов. Эти константы используются методами [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) и [ISymUnmanagedBinder3:: жетреадерфромкаллбакк](isymunmanagedbinder3-getreaderfromcallback-method.md) .  
  
> [!IMPORTANT]
> При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`AllowRegistryAccess`|Запрашивает пути поиска символов в реестре.|  
|`AllowSymbolServerAccess`|Обращается к серверу символов.|  
|`AllowOriginalPathAccess`|Выполняет поиск по пути, указанному в каталоге отладки.|  
|`AllowReferencePathAccess`|Выполняет поиск PDB в месте, где находится EXE-файл.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления хранилища символов диагностики](diagnostics-symbol-store-enumerations.md)
