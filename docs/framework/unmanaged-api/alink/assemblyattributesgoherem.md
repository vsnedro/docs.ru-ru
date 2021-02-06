---
description: 'Дополнительные сведения о: Ассембляттрибутесгохерем Class'
title: Класс Ассембляттрибутесгохерем (System. Runtime. CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
ms.openlocfilehash: 9afa72e5adbd539acaf8dfe45b446a61862df49e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638578"
---
# <a name="assemblyattributesgoherem-class"></a>Класс Ассембляттрибутесгохерем

Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.

## <a name="syntax"></a>Синтаксис

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a>Remarks

Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки. При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов. Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.

Ссылки на этот тип указывают пользовательские атрибуты, не связанные с безопасностью, но многократного использования.

Эти типы помечены как "внутренние" в платформа .NET Framework и находятся в <xref:System.Runtime.CompilerServices> пространстве имен.

## <a name="requirements"></a>Требования

mscorlib.dll

## <a name="see-also"></a>См. также

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
