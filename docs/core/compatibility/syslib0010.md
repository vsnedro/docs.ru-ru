---
title: Предупреждение SYSLIB0010
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0010.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dcd331aa5c68381ea29848bc54ee4b1a5e75330d
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333110"
---
# <a name="syslib0010-unsupported-remoting-apis"></a>SYSLIB0010. Неподдерживаемые API удаленного взаимодействия

Технология [удаленного взаимодействия .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) является устаревшей, и соответствующая инфраструктура существует только в .NET Framework. Следующие API, связанные с удаленным взаимодействием, помечены как устаревшие, начиная с версии .NET 5.0. При их использовании во время компиляции создается предупреждение `SYSLIB0010`.

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workaround"></a>Обходной путь

Для взаимодействия с объектами в других приложениях или на других компьютерах рекомендуется использовать WCF или службы RESTFUL на основе HTTP. Дополнительные сведения см. в разделе [Технологии .NET Framework, недоступные в .NET Core](../porting/net-framework-tech-unavailable.md).

## <a name="see-also"></a>См. также

- [Удаленное взаимодействие .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
