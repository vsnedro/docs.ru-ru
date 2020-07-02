---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616087"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load не удаляет свойство символа

#### <a name="details"></a>Подробнее

При выборе целевой версии платформы .NET Framework 4.5 в конструкторе рабочих процессов и загрузке повторно размещаемого рабочего процесса 3.5 с помощью метода <xref:System.Activities.Presentation.WorkflowDesigner.Load> во время сохранения рабочего процесса создается исключение <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Эта ошибка возникает только при нацеливании на .NET Framework 4.5 в конструкторе рабочих процессов, поэтому ее можно устранить, установив `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` в 4.0 .NET Framework. Этой проблемы можно избежать, если использовать метод <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> для загрузки рабочего процесса вместо <xref:System.Activities.Presentation.WorkflowDesigner.Load>.

| name    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
