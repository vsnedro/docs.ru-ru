---
title: -langversion (параметры компилятора C#)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: fd05802008a20267fea54f14bae4c8deb0e21c65
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656217"
---
# <a name="-langversion-c-compiler-options"></a>-langversion (параметры компилятора C#)

Инструктирует компилятор принимать только синтаксис, включенный в заданную спецификацию языка C#.

## <a name="syntax"></a>Синтаксис

```console
-langversion:option
```

## <a name="arguments"></a>Аргументы

`option`

Допустимы следующие значения.

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

Версия языка по умолчанию зависит от целевой платформы приложения, а также от установленной версии пакета SDK или Visual Studio. Эти правила определяются в статье о [настройке версии языка](../configure-language-version.md#defaults).

## <a name="remarks"></a>Примечания

Параметр компилятора **-langversion** не влияет на метаданные, на которые ссылается ваше приложение C#.

Так как каждая версия компилятора C# содержит расширения для спецификации языка, параметр **-langversion** не позволяет получить функциональные возможности, аналогичные более ранней версии компилятора.

Кроме того, в отличие от обновлений версии C#, которые обычно совпадают с основными выпусками платформы .NET Framework, новые функции и возможности синтаксиса могут быть не привязаны к конкретной версии этой платформы. Для работы с новыми версиями требуется обновление компилятора, которое также выпускается с новой редакцией C#. Тем не менее для каждой функции определен собственный набор минимальных требований к API .NET или общеязыковой среде выполнения, в результате чего их можно выполнять на более ранних версиях платформы, добавив необходимые пакеты NuGet или другие библиотеки.

Независимо от того, какой параметр **-langversion** вы задали, используйте для создания файлов с расширением .exe или .dll. текущую версию общеязыковой среды выполнения. Единственным исключением являются дружественные сборки и [-moduleassemblyname (параметр компилятора C#)](./moduleassemblyname-compiler-option.md), которые работают при установке параметра **-langversion:ISO-1**.

Другие способы указания версии языка C# см. в статье [Выбор версии языка C#](../configure-language-version.md).

Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.

## <a name="c-language-specification"></a>Спецификация языка C#

| Version          | Ссылка                       | Описание                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| C# 7.0 и более поздние версии |                            | В настоящее время недоступно.                                                 |
| C# 6.0           | [Ссылка][csharp-6]           | Спецификация языка C# версии 6 (неофициальный проект): .NET Foundation |
| C# 5.0           | [Загрузить PDF-файл][csharp-5]   | Стандарт ECMA-334, 5-й выпуск                                           |
| C# 3.0           | [Загрузить DOC-файл][csharp-3]   | Спецификация языка C#, версия 3.0: Microsoft Corporation            |
| C# 2.0           | [Загрузить PDF-файл][csharp-2]   | Стандарт ECMA-334, 4-й выпуск                                           |
| C# 1.2           | [Загрузить DOC-файл][csharp-1.2] | Спецификация языка C#, версия 1.2: Microsoft Corporation            |
| C# 1.0           | [Загрузить DOC-файл][csharp-1]   | Спецификация языка C#, версия 1.0: Microsoft Corporation            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a>Минимальная версия пакета SDK, необходимая для поддержки всех возможностей языка

В следующей таблице перечислены минимальные версии пакета SDK с компилятором C#, поддерживающим соответствующую версию языка:

| Версия C# | Минимальная версия пакета SDK                                                                  |
|------------|--------------------------------------------------------------------------------------|
| C# 8.0     | Microsoft Visual Studio/Build Tools 2019, версия 16.3 или пакет SDK .NET Core 3.0         |
| C# 7.3     | Microsoft Visual Studio/Build Tools 2017, версия 15.7                               |
| C# 7.2     | Microsoft Visual Studio/Build Tools 2017, версия 15.5                               |
| C# 7.1     | Microsoft Visual Studio/Build Tools 2017, версия 15.3                               |
| C# 7.0     | Microsoft Visual Studio/Build Tools 2017                                             |
| C# 6       | Microsoft Visual Studio/Build Tools 2015                                             |
| C# 5       | Microsoft Visual Studio/Build Tools 2012 или встроенный компилятор .NET Framework 4.5      |
| C# 4       | Microsoft Visual Studio/Build Tools 2010 или встроенный компилятор .NET Framework 4.0      |
| C# 3       | Microsoft Visual Studio/Build Tools 2008 или встроенный компилятор .NET Framework 3.5      |
| C# 2       | Microsoft Visual Studio/Build Tools 2005 или встроенный компилятор .NET Framework 2.0      |
| C# 1.0/1.2 | Microsoft Visual Studio/Build Tools .NET 2002 или встроенный компилятор .NET Framework 1.0 |

## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
