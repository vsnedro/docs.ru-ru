---
ms.openlocfilehash: 0d6847b7a937094f36efae70ae450cc37824221d
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955565"
---
### <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a>Изменения в поведении API, связанные со сборкой, для формата публикации с одним файлом

Изменилось поведение нескольких интерфейсов API, связанных с расположением файла сборки, когда они вызываются в формате публикации с одним файлом.

#### <a name="change-description"></a>Описание изменений

В публикации с одним файлом для .NET 5.0 и более поздних версий упакованные сборки загружаются из памяти, а не извлекаются на диск. Для приложений, опубликованных в одном файле, это означает, что определенные интерфейсы API, связанные с расположением, возвращают в .NET 5.0 и более поздних версиях другие значения по сравнению с предыдущими версиями .NET. Изменения заключается в следующем.

| API | предыдущих версий | .NET 5.0 и более поздней версии |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | Возвращает путь к извлеченному файлу DLL | Возвращает пустую строку для упакованных сборок |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | Возвращает путь к извлеченному файлу DLL | Вызывает исключение для упакованных сборок |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | Возвращает `null` для упакованных сборок | Вызывает исключение для упакованных сборок |
| `Environment.GetCommandLineArgs()[0]` | Значением является имя точки входа библиотеки DLL | Значением является имя исполняемого файла узла |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | Значением является временный каталог извлечения | Значением является каталог, содержащий исполняемый файл узла |

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="recommended-action"></a>Рекомендованное действие

Избегайте зависимостей от расположения файлов сборок при публикации в виде одного файла.

#### <a name="category"></a>Категория

- Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
