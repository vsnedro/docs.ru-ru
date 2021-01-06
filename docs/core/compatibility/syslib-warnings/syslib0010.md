---
title: Предупреждение SYSLIB0010
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0010.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 289fb3f766a6e1d37bea8faec1896d20442f43f9
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596337"
---
# <a name="syslib0010-unsupported-remoting-apis"></a>SYSLIB0010. Неподдерживаемые API удаленного взаимодействия

Технология [удаленного взаимодействия .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) является устаревшей, и соответствующая инфраструктура существует только в .NET Framework. Следующие API, связанные с удаленным взаимодействием, помечены как устаревшие, начиная с версии .NET 5.0. При их использовании во время компиляции создается предупреждение `SYSLIB0010`.

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workarounds"></a>Обходные пути

Для взаимодействия с объектами в других приложениях или на других компьютерах рекомендуется использовать WCF или службы RESTFUL на основе HTTP. Дополнительные сведения см. в разделе [Технологии .NET Framework, недоступные в .NET Core](../../porting/net-framework-tech-unavailable.md).

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>См. также

- [Удаленное взаимодействие .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
