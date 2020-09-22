---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606444"
---
### <a name="workflow-30-types-are-obsolete"></a>Типы WorkFlow 3.0 устарели

#### <a name="details"></a>Подробнее

API-интерфейсы Windows Workflow Foundation (WWF) 3.0 (из пространства имен System.Workflow) теперь являются устаревшими.

#### <a name="suggestion"></a>Предложение

Вместо них следует использовать новые интерфейсы API WWF 4.0 (в System.Activities). Пример использования новых интерфейсов API можно найти [здесь](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), а дальнейшие рекомендации доступны [здесь](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5). Кроме того, поскольку API-интерфейсы WWF 3.0 по-прежнему поддерживаются, их можно использовать, а чтобы избежать вывода предупреждения во время построения, его можно подавить или воспользоваться более старой версией компилятора.

| name    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |
