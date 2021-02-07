---
description: Дополнительные сведения о перечислении Ассембликомпарисонресулт
title: Перечисление AssemblyComparisonResult
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: 093cff830aa87d28ee86ecaeb6965887279a72d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761295"
---
# <a name="assemblycomparisonresult-enumeration"></a>Перечисление AssemblyComparisonResult

Указывает эквивалентность двух удостоверений сборки, как определено функцией [компареассемблидентити](compareassemblyidentity-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>Члены  
  
|Имя участника|Описание|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Указывает, что все поля сборки в совпадении сравнения.|  
|`ACR_EquivalentFXUnified`|Указывает, что сборки считаются эквивалентными на основе унификации номеров версий сборки среды CLR в версии платформа .NET Framework 2,0.|  
|`ACR_EquivalentPartialFXUnified`|Указывает частичное совпадение сборок на основе унификации версий сборки CLR в платформа .NET Framework 2,0.|  
|`ACR_EquivalentPartialMatch`|Указывает частичное совпадение сборок.|  
|`ACR_EquivalentPartialUnified`|Указывает частичное совпадение сборок на основе унификации устаревших номеров версий.|  
|`ACR_EquivalentPartialWeakNamed`|Указывает частичное совпадение с простыми именованными сборками.|  
|`ACR_EquivalentUnified`|Указывает, что сборки считаются эквивалентными на основе унификации версии CLR номеров версий в устаревших версиях платформа .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Указывает соответствие между двумя простыми именованными сборками, Номера версий которых были пропущены.|  
|`ACR_NonEquivalent`|Указывает, что между двумя сборками не произошло совпадений.|  
|`ACR_NonEquivalentPartialVersion`|Указывает, что две сборки совпадают, за исключением номеров версий, которые соответствуют только частично.|  
|`ACR_NonEquivalentVersion`|Указывает, что две сборки совпадают, за исключением номеров версий, которые не совпадают.|  
|`ACR_Unknown`|Указывает, что причина неравенства неизвестна.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CompareAssemblyIdentity](compareassemblyidentity-function.md)
- [Перечисления Fusion](fusion-enumerations.md)
