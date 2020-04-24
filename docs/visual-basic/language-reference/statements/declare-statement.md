---
title: Declare Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
ms.openlocfilehash: 9895709076634ce156ba9d1009f79ba7ddd2ba56
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646382"
---
# <a name="declare-statement"></a>Declare Statement

Объявляет ссылку на процедуру, реализованную во внешнем файле.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ]
' -or-
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]
```

## <a name="parts"></a>Компоненты

|Термин|Определение|
|---|---|
|`attributelist`|Необязательный параметр. Посмотреть [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|
|`accessmodifier`|Необязательный параметр. Может применяться один из перечисленных ниже типов.<br /><br /> -   [Общественного](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Защищены](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Друг](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Частная](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Защищенный друг](../../language-reference/modifiers/protected-friend.md)<br />- [Частные охраняемые](../../language-reference/modifiers/private-protected.md)<br /><br /> Посмотреть [уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Необязательный параметр. Смотрите [Тени](../../../visual-basic/language-reference/modifiers/shadows.md).|
|`charsetmodifier`|Необязательный параметр. Определяет набор символов и информацию о поиске файлов. Может применяться один из перечисленных ниже типов.<br /><br /> -   [Анси](../../../visual-basic/language-reference/modifiers/ansi.md) (по умолчанию)<br />-   [Юникода](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Авто](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|Необязательно, `Sub` но `Function` либо или должны появиться. Означает, что внешняя процедура не возвращает значение.|
|`Function`|Необязательно, `Sub` но `Function` либо или должны появиться. Означает, что внешняя процедура возвращает значение.|
|`name`|Обязательный элемент. Название этой внешней ссылки. Для получения дополнительной информации [см.](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)|
|`Lib`|Обязательный элемент. Вводит `Lib` положение, которое идентифицирует внешний файл (DLL или кодовый ресурс), содержащий внешнюю процедуру.|
|`libname`|Обязательный элемент. Название файла, содержащего заявленную процедуру.|
|`Alias`|Необязательный параметр. Означает, что объявленная процедура не может быть идентифицирована в файле по имени, указанному в. `name` Вы указываете `aliasname`его идентификацию в .|
|`aliasname`|Требуется, если `Alias` вы используете ключевое слово. Строка, которая определяет процедуру одним из двух способов:<br /><br /> Название точки входа процедуры в своем файле, в пределах котировок (`""`)<br /><br /> -или-<br /><br /> Знак числа`#`(), за которым следует целый номер, указывающий на ординаторский номер точки входа процедуры в своем файле|
|`parameterlist`|Требуется, если процедура принимает параметры. Посмотреть [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|
|`returntype`|Требуется, `Function` если `Option Strict` `On`указан и является . Тип значения, возвращаемого процедурой, является типом данных.|

## <a name="remarks"></a>Примечания

Иногда требуется вызвать процедуру, определенную в файле (например, DLL или кодовый ресурс) за пределами проекта. При этом компилятор Visual Basic не имеет доступа к информации, необходимой для правильного вызова процедуры, например, к месту расположения процедуры, к ее идентификации, последовательности вызовов и типу возврата, а также к набору персонажа строки. В `Declare` заявлении содержится ссылка на внешнюю процедуру и содержится необходимая информация.

`Declare` можно использовать только на уровне модуля. Это означает, что *контекст объявления* для внешней ссылки должен быть классом, структурой или модулем и не может быть исходным файлом, пространством имен, интерфейсом, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Внешние ссылки по умолчанию для [публичного](../../../visual-basic/language-reference/modifiers/public.md) доступа. Вы можете настроить их уровни доступа с помощью модификаторов доступа.

## <a name="rules"></a>Правила

- **Атрибуты.** Можно применить атрибуты к внешней ссылке. Любой атрибут, который вы применяете, действует только в проекте, а не во внешнем файле.

- **Модификаторы.** Внешние процедуры неявно [общие](../../../visual-basic/language-reference/modifiers/shared.md). Вы не `Shared` можете использовать ключевое слово при объявлении внешней ссылки, и вы не можете изменить его общий статус.

  Внешняя процедура не может участвовать в переопределение, реализовать элементы интерфейса или обрабатывать события. Соответственно, вы не `Overrides`можете `Overridable` `NotOverridable`использовать `MustOverride` `Implements`, `Handles` , , `Declare` , или ключевое слово в заявлении.

- **Внешнее название процедуры.** Вы не должны дать эту внешнюю ссылку то же имя (в), `name`как имя`aliasname`точки входа процедуры в своем внешнем файле ( ). Можно использовать `Alias` оговорку для указания имени точки входа. Это может быть полезно, если внешняя процедура имеет то же имя, что и зарезервированный модификатор Visual Basic или переменный, процедура или любой другой элемент программирования в той же области.

  > [!NOTE]
  > Имена точек входа в большинстве DLL чувствительны к случаям.

- **Внешний номер процедуры.** Кроме того, можно `Alias` использовать положение, чтобы указать обычное число точки входа в таблице экспорта внешнего файла. Для этого вы `aliasname` начинаете с`#`знака числа (). Это может быть полезно, если какой-либо символ во внешнем названии процедуры не допускается в Visual Basic, или если внешний файл экспортирует процедуру без имени.

## <a name="data-type-rules"></a>Правила типа данных

- **Типы параметров данных.** Если `Option Strict` `On`это так, то необходимо указать `parameterlist`тип данных каждого параметра в. Это может быть любой тип данных или название перечисления, структура, класс или интерфейс. Внутри, `parameterlist`вы `As` используете оговорку, чтобы указать тип данных аргумента, который будет передан каждому параметру.

  > [!NOTE]
  > Если внешняя процедура не была написана для рамочного соглашения .NET, необходимо позаботиться о том, чтобы типы данных соответствовали действительности. Например, если вы объявляете внешнюю ссылку на `Integer` процедуру Visual Basic 6.0 с параметром (16 `Short` бит `Declare` в Visual Basic 6.0), необходимо определить соответствующий аргумент, как в заявлении, потому что это 16-битный целый тип в Visual Basic. Аналогичным `Long` образом, имеет различную ширину данных в Visual Basic 6.0, и `Date` реализуется по-разному.

- **Тип возврата данных.** Если внешняя `Function` процедура `Option Strict` `On`является и есть, необходимо указать тип значения, возвращенного в код вызова. Это может быть любой тип данных или название перечисления, структура, класс или интерфейс.

  > [!NOTE]
  > Компилятор Visual Basic не проверяет, что типы данных совместимы с типами внешней процедуры. При несоответствии время выполнения общего языка генерирует <xref:System.Runtime.InteropServices.MarshalDirectiveException> исключение во время выполнения.

- **Типы данных по умолчанию.** Если `Option Strict` `Off` это так, и вы не указываете тип параметра в `parameterlist`данных, то компилятор Visual Basic преобразует соответствующий аргумент в тип [данных объекта.](../../../visual-basic/language-reference/data-types/object-data-type.md) Аналогичным образом, если `returntype`вы не указали, компилятор принимает тип возврата данных, чтобы быть. `Object`

  > [!NOTE]
  > Поскольку вы имеете дело с внешней процедурой, которая могла быть написана на другой платформе, опасно делать какие-либо предположения о типах данных или позволять им по умолчанию. Гораздо безопаснее указать тип данных каждого параметра и значение возврата, если такового. Это также улучшает читаемость кода.

## <a name="behavior"></a>Поведение

- **Области.** Внешняя ссылка находится в области по всему классу, структуре или модулю.

- **Жизни.** Внешняя ссылка имеет тот же срок службы, что и класс, структура или модуль, в котором она заявлена.

- **Вызов внешней процедуры.** Вы вызываете внешнюю процедуру `Function` так `Sub` же, как вы называете или процедуру, используя ее в выражении, если она возвращает значение, или указывая его в [выписке вызова,](../../../visual-basic/language-reference/statements/call-statement.md) если она не возвращает значение.

  Аргументы перед внешней процедурой передаются точно так, как указано `parameterlist` в заявлении. `Declare` Не принимайте во внимание, как параметры были первоначально объявлены во внешнем файле. Аналогичным образом, при наличии значения возврата используйте его точно так же, как указано `returntype` в выписке. `Declare`

- **Наборы символов.** Можно указать, `charsetmodifier` как Visual Basic должен маршалировать строки, когда он вызывает внешнюю процедуру. Модификатор `Ansi` направляет Visual Basic для маршала всех строк на `Unicode` значения ANSI, а модификатор направляет его для маршала всех строк к значениям Unicode. Модификатор `Auto` направляет Visual Basic на строки маршала в соответствии с правилами .NET Framework, основанными на внешней ссылке `name`или `aliasname` если указано. Значение по умолчанию — `Ansi`.

  `charsetmodifier`также указывается, как Visual Basic должен искать внешнюю процедуру в своем внешнем файле. `Ansi`и `Unicode` как прямой Visual Basic, чтобы посмотреть его без изменения его имени во время поиска. `Auto`направляет Visual Basic для определения базового набора символов платформы времени выполнения и, возможно, изменения внешнего названия процедуры следующим образом:

  - На платформе ANSI, такой как Windows 95, Windows 98 или Windows Millennium Edition, сначала ищите внешнюю процедуру без изменения имени. Если это не удается, придя "А" в конец внешнего имени процедуры и посмотреть его снова.

  - На платформе Unicode, такой как Windows NT, Windows 2000 или Windows XP, сначала ищите внешнюю процедуру без изменения имени. Если это не удается, придя "W" в конце внешнего имени процедуры и посмотреть его снова.

- **Механизм.** Visual Basic использует механизм ссылки на *платформу* .NET Framework (PInvoke) для решения и доступа к внешним процедурам. Заявление `Declare` и <xref:System.Runtime.InteropServices.DllImportAttribute> класс используют этот механизм автоматически, и вам не нужны знания о PInvoke. Для получения дополнительной информации смотрите [Пошаговая прогулка: Вызов Windows AIS](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).

> [!IMPORTANT]
> Если внешняя процедура выходят за рамки общего времени выполнения языка (CLR), это *неуправляемый код.* При вызове такой процедуры, например функции API Windows или метода COM, приложение может подвергать приложение рискам безопасности. Для получения дополнительной информации [см.](https://docs.microsoft.com/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code)

## <a name="example"></a>Пример

В следующем примере объявляется `Function` внешняя ссылка на процедуру, которая возвращает текущее имя пользователя. Затем он вызывает `GetUserNameA` внешнюю процедуру как часть процедуры. `getUser`

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Пример

Предоставляет <xref:System.Runtime.InteropServices.DllImportAttribute> альтернативный способ использования функций в неуправляемом коде. В следующем примере объявляется импортируемая функция без использования `Declare` оператора.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [AddressOf Оператор](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Оператор Call](../../../visual-basic/language-reference/statements/call-statement.md)
- [Пошаговое руководство. Вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
