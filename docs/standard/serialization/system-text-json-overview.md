---
title: Сериализация и десериализация JSON с помощью C# — .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159550"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="e00a2-102">Сериализация и десериализация JSON (маршалинг и демаршалинг) в .NET — обзор</span><span class="sxs-lookup"><span data-stu-id="e00a2-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="e00a2-103">Пространство имен `System.Text.Json` предоставляет функциональные возможности для сериализации в нотацию объектов JavaScript (JSON) и десериализации объектов из этой нотации.</span><span class="sxs-lookup"><span data-stu-id="e00a2-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="e00a2-104">Архитектура библиотеки позволяет обеспечить высокую производительность и низкое выделение памяти для обширного набора функций.</span><span class="sxs-lookup"><span data-stu-id="e00a2-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="e00a2-105">Встроенная поддержка UTF-8 оптимизирует процесс чтения и записи текста JSON в кодировке UTF-8, которая является наиболее распространенной кодировкой для данных в Интернете и файлов на диске.</span><span class="sxs-lookup"><span data-stu-id="e00a2-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="e00a2-106">Библиотека также предоставляет классы для работы с объектной моделью документов (DOM) в памяти.</span><span class="sxs-lookup"><span data-stu-id="e00a2-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="e00a2-107">Эта возможность обеспечивает произвольный доступ только для чтения к элементам в файле JSON или строке.</span><span class="sxs-lookup"><span data-stu-id="e00a2-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="e00a2-108">Получение библиотеки</span><span class="sxs-lookup"><span data-stu-id="e00a2-108">How to get the library</span></span>

* <span data-ttu-id="e00a2-109">Библиотека входит в состав общей платформы [.NET Core 3.0](https://aka.ms/netcore3download).</span><span class="sxs-lookup"><span data-stu-id="e00a2-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="e00a2-110">Для других целевых платформ установите пакет NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json).</span><span class="sxs-lookup"><span data-stu-id="e00a2-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="e00a2-111">Пакет поддерживает:</span><span class="sxs-lookup"><span data-stu-id="e00a2-111">The package supports:</span></span>
  * <span data-ttu-id="e00a2-112">.NET Standard 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="e00a2-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="e00a2-113">.NET Framework 4.7.2 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="e00a2-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="e00a2-114">.NET Core 2.0, 2.1 и 2.2</span><span class="sxs-lookup"><span data-stu-id="e00a2-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e00a2-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e00a2-115">Additional resources</span></span>

* [<span data-ttu-id="e00a2-116">Использование библиотеки</span><span class="sxs-lookup"><span data-stu-id="e00a2-116">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="e00a2-117">[Как выполнить миграцию из Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="e00a2-117">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="e00a2-118">Написание преобразователей</span><span class="sxs-lookup"><span data-stu-id="e00a2-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="e00a2-119">[Исходный код System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="e00a2-119">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="e00a2-120">[Справочник по API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="e00a2-120">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="e00a2-121">[Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="e00a2-121">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
