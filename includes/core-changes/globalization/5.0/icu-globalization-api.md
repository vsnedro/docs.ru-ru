---
ms.openlocfilehash: 74c3d3247912dcd638a9379d54e682967c5e400b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302723"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a>API-интерфейсы глобализации, которые используют библиотеки ICU в Windows

.NET 5.0 и более поздних версий использует библиотеки [ICU (международные компоненты для Юникода)](http://site.icu-project.org/home) для поддержки глобализации при работе в Windows 10 с обновлением за май 2019 года или более поздней версии.

#### <a name="change-description"></a>Описание изменений

Ранее в библиотеках .NET для поддержки глобализации использовались API-интерфейсы [NLS (многоязыковая поддержка)](/windows/win32/intl/national-language-support). Например, функции NLS применялись для получения данных о языке и региональных параметрах, таких как шаблоны формата, правила сравнения строк, а также для изменения капитализации строк.

Начиная с .NET 5.0, для приложений в среде Windows 10 с обновлением за май 2019 года или более поздней версии библиотеки .NET используют API-интерфейсы глобализации [ICU](http://site.icu-project.org/home). В Windows 10 с обновлением за май 2019 года и более поздних версий входит библиотека ICU. Если среда выполнения .NET не может загрузить ICU, вместо нее используется NLS.

Это изменение внесено по следующим двум причинам:

- Приложения получают одинаковые стандарты глобализации на разных платформах, включая Linux, macOS и Windows.
- Приложения могут управлять параметрами глобализации с помощью пользовательских библиотек ICU.

#### <a name="version-introduced"></a>Представленная версия

Предварительная версия 4 .NET 5.0

#### <a name="recommended-action"></a>Рекомендованное действие

От разработчика не требуется никаких действий. Но если вы хотите по-прежнему использовать API-интерфейсы глобализации NLS, настройте [параметр времени выполнения](../../../../docs/core/run-time-config/globalization.md#nls), чтобы вернуться к старому поведению. Дополнительные сведения о доступных параметрах см. в статье [Глобализация .NET и ICU](/dotnet/standard/globalization-localization/globalization-icu).

#### <a name="category"></a>Категория

Глобализация

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- Почти все типы в пространстве имен <xref:System.Globalization?displayProperty=fullName>

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`

-->
