---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496765"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM

#### <a name="details"></a>Подробнее

Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM. Затронуты следующие типы:

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName> (и его производные типы, включая <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> и <xref:System.Reflection.TypeInfo?displayProperty=fullName>)
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

Вызовы <code>IMarshal</code> объекта возвращают <code>E_NOINTERFACE</code>.

#### <a name="suggestion"></a>Предложение

Обновите код маршалинга для работы с объектами без отражения.

| Имя    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
