---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617271"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a>Версия Entity Framework должна соответствовать версии .NET Framework

#### <a name="details"></a>Подробнее

Версия Entity Framework (EF) должна соответствовать версии платформы .NET Framework. Для .NET Framework 4.5 рекомендуется Entity Framework 5. Существуют некоторые известные проблемы с EF 4.x в проекте .NET Framework 4.5, связанные с <xref:System.ComponentModel.DataAnnotations>. В .NET Framework 4.5 они были перемещены в другую сборку, поэтому существуют проблемы с выбором заметок для использования.

#### <a name="suggestion"></a>Предложение

Обновление до версии Entity Framework 5 для .NET Framework 4.5

| name    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |
