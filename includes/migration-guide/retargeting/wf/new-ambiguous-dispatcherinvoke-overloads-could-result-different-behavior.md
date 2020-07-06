---
ms.openlocfilehash: 80e61d4dd5b8d4754a39e95e37475fefff57fcbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617264"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>Новые (неоднозначные) перегрузки Dispatcher.Invoke могут привести к изменению поведения

#### <a name="details"></a>Подробнее

В .NET Framework 4.5 добавлены новые перегрузки в метод <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType>, включающие параметр типа <xref:System.Action>. Если существующий код перекомпилируется, компиляторы могут разрешить вызовы методов Dispatcher.Invoke, имеющие параметр <xref:System.Delegate>, как вызовы методов Dispatcher.Invoke с параметром <xref:System.Action>. Если вызов перегрузки Dispatcher.Invoke с параметром <xref:System.Delegate> разрешается как вызов перегрузки Dispatcher.Invoke с параметром <xref:System.Action>, возможны следующие различия в поведении.

- При возникновении исключения события <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> и <xref:System.Windows.Threading.Dispatcher.UnhandledException> не вызываются. Вместо этого исключения обрабатываются событием <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName>.
- Вызовы некоторых членов, например свойства <xref:System.Windows.Threading.DispatcherOperation.Result>, блокируются до тех пор, пока операция не будет завершена.

#### <a name="suggestion"></a>Предложение

Чтобы избежать неоднозначности (и потенциальных различий в обработке исключений и поведениях блокировки), код, вызывающий Dispatcher.Invoke, может передать пустой object[] как второй параметр в вызов Invoke, чтобы гарантировать разрешение перегрузки метода в .NET Framework 4.0.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
