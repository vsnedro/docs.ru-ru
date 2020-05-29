---
title: Source Link и библиотеки .NET
description: Практические рекомендации по использованию Source Link для повышения эффективности отладки для библиотек .NET.
ms.date: 01/15/2019
ms.openlocfilehash: 0261019087bce8e9d088a90c5e36bdd0b22f556b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212429"
---
# <a name="source-link"></a>Source Link

Source Link — это технология, которая дает возможность разработчикам выполнять отладку исходного кода сборок .NET из NuGet. Source Link выполняется при создании пакета NuGet и внедряет метаданные системы управления версиями внутри сборки и пакета. Разработчики, загрузившие пакет и включившие Source Link в Visual Studio, могут выполнить исходный код по шагам. Source Link предоставляет метаданные системы управления версиями для создания эффективной среды отладки.

## <a name="source-link-demo"></a>Демонстрация Source Link

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a>Использование Source Link

Инструкции по использованию Source Link можно найти в репозитории GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).

Вы можете использовать [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), чтобы убедиться, что метаданные Source Link успешно внедрены в пакет. Проверьте наличие метаданных `Repository` с идентификатором фиксации и убедитесь, что для каждой DLL-библиотеки целевого пакета есть PDB-файлы.

![Ссылка на источник в обозревателе пакетов NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "Ссылка на источник в обозревателе пакетов NuGet")

✔ РЕКОМЕНДУЕТСЯ использовать Source Link для добавления метаданных системы управления версиями в сборки и пакеты NuGet.

> [!TIP]
> Вы можете дополнительно повысить эффективность отладки путем добавления атрибутов отладчика в типы.
>
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> может определять, как класс или поле будет отображаться в окнах переменных отладчика.
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> дает отладчику указание о сквозной обработке кода (вместо выполнения по шагам).
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> определяет, будет ли член отображаться в окнах переменных отладчика.

✔ РЕКОМЕНДУЕТСЯ публиковать файлы символов (`*.pdb`).

> Для повышения качества отладки библиотеки следует публиковать файлы символов, а также использовать ссылки на источник. См. дополнительные сведения о [файлах и пакетах символов](./nuget.md#symbol-packages).

✔️ РЕКОМЕНДУЕТСЯ включить детерминированные сборки.

> Детерминированные сборки позволяют убедиться в том, что полученный двоичный файл построен на основе указанного источника и обеспечивает трассировку. См. сведения о [детерминированных сборках](https://github.com/clairernovotny/DeterministicBuilds) и инструкции по их включению.

>[!div class="step-by-step"]
>[Назад](dependencies.md)
>[Вперед](publish-nuget-package.md)
