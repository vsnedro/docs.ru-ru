---
description: 'Дополнительные сведения о: Ассембляттрибутесгохере Class'
title: Класс Ассембляттрибутесгохере (System. Runtime. CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHere
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type:
- apiref
ms.openlocfilehash: b95ff377f7fa0ffc85136dd69eb4a32121a50dc2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638591"
---
# <a name="assemblyattributesgohere-class"></a>Класс Ассембляттрибутесгохере

Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.

## <a name="syntax"></a>Синтаксис

```csharp
internal sealed class AssemblyAttributesGoHere
```

## <a name="remarks"></a>Remarks

Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки. При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов. Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.

Ссылки на этот тип указывают пользовательские атрибуты, не связанные с безопасностью, которые нельзя использовать многократно.

Эти типы помечены как "внутренние" в платформа .NET Framework и находятся в <xref:System.Runtime.CompilerServices> пространстве имен.

## <a name="requirements"></a>Требования

mscorlib.dll

## <a name="see-also"></a>См. также

- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
