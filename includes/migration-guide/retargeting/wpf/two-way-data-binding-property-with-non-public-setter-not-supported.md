---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616126"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>Двусторонняя привязка данных к свойству с не предназначенным для общего доступа методом задания не поддерживается

#### <a name="details"></a>Подробнее

Попытка привязки данных к свойству без общедоступного метода задания никогда не поддерживалась. Начиная с .NET Framework 4.5.1 этот сценарий выдает исключение <xref:System.InvalidOperationException?displayProperty=fullName>. Обратите внимание, что это новое исключение создается только для приложений, которые предназначены специально для .NET Framework 4.5.1. Если приложение предназначено для .NET Framework 4.5, вызов будет разрешен. Если приложение не предназначено для определенной версии .NET Framework, привязка будет рассматриваться как односторонняя.

#### <a name="suggestion"></a>Предложение

Приложение следует обновить либо для использования односторонней привязки, либо для предоставления общего доступа к методу задания свойства. Кроме того, выбор .NET Framework 4.5 в качестве целевой платформы приведет к восстановлению старого поведения приложения.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.5.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
