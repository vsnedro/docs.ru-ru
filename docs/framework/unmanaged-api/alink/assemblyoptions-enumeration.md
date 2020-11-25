---
title: Перечисление AssemblyOptions
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717035"
---
# <a name="assemblyoptions-enumeration"></a>Перечисление AssemblyOptions

Перечисляет параметры сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Поля  
  
|Поле|Описание|  
|-----------|-----------------|  
|оптассемтитле|Строка — представляет заголовок сборки.|  
|оптассемдескриптион|Строка — содержит описание сборки.|  
|оптассемконфиг|Строка — содержит конфигурацию сборки.|  
|оптассемос|Строка в кодировке: "Двосплатформид. Двосмажорверсион. Двосминорверсион".|  
|оптассемпроцессор|ULONG|  
|оптассемлокале|Строка — содержит языковой стандарт сборки.|  
|оптассемверсион|Строка в кодировке: "основная. Дополнительная. сборка. Редакция".|  
|оптассемкомпани|Строка — содержит компанию.|  
|оптассемпродукт|Строка — содержит имя продукта.|  
|оптассемпродуктверсион|Строка (также известная как Информатионалверсион).|  
|оптассемкопиригхт|Строка — содержит сведения об авторских правах.|  
|оптассемтрадемарк|Строка — содержит сведения о товарном знаке.|  
|оптассемкэйфиле|Строка (имя файла).|  
|оптассемкэйнаме|Строка (имя ключа).|  
|оптассемалгид|ULONG|  
|оптассемфлагс|ULONG|  
|оптассемхалфсигн|Bool (также называется DelaySign).|  
|оптассемфилеверсион|Строка, закодированная как "основная. Дополнительная. сборка. Редакция"--то же, что и ProductVersion.|  
|оптассемсателлитевер|Строка, закодированная как "основная. Дополнительная. сборка. Редакция".|  
|оптластассемоптион|Счетчик числа элементов.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** ALink. h  
  
 **Библиотека**: alink.dll  
  
## <a name="see-also"></a>См. также раздел

- [Al.exe (компоновщик сборок)](../../tools/al-exe-assembly-linker.md)
