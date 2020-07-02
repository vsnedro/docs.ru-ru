---
ms.openlocfilehash: 3f330d5e601d599231ef0336b785e677fe1d114e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616082"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a><span data-ttu-id="37b1f-101">DataObject.GetData теперь получает данные в кодировке UTF-8</span><span class="sxs-lookup"><span data-stu-id="37b1f-101">DataObject.GetData now retrieves data as UTF-8</span></span>

#### <a name="details"></a><span data-ttu-id="37b1f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="37b1f-102">Details</span></span>

<span data-ttu-id="37b1f-103">В приложениях, предназначенных для .NET Framework 4 или выполняющихся в .NET Framework 4.5.1 или более ранних версий, `DataObject.GetData` получает HTML-данные в виде строки ASCII.</span><span class="sxs-lookup"><span data-stu-id="37b1f-103">For apps that target the .NET Framework 4 or that run on the .NET Framework 4.5.1 or earlier versions, `DataObject.GetData` retrieves HTML-formatted data as an ASCII string.</span></span> <span data-ttu-id="37b1f-104">В результате символы, не относящиеся к ASCII (т. е. символы с кодами ASCII больше 0x7F), представляются двумя случайными символами.</span><span class="sxs-lookup"><span data-stu-id="37b1f-104">As a result, non-ASCII characters (characters whose ASCII codes are greater than 0x7F) are represented by two random characters.</span></span><p/><span data-ttu-id="37b1f-105">Для приложений, предназначенных для NET Framework 4.5 и более поздней версии и выполняемых в .NET Framework 4.5.2, `DataObject.GetData` получает HTML-данные в формате UTF-8, который правильно представляет символы с кодами более 0x7F.</span><span class="sxs-lookup"><span data-stu-id="37b1f-105">For apps that target the .NET Framework 4.5 or later and run on the .NET Framework 4.5.2, `DataObject.GetData` retrieves HTML-formatted data as UTF-8, which represents characters greater than 0x7F correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="37b1f-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="37b1f-106">Suggestion</span></span>

<span data-ttu-id="37b1f-107">Если реализован обходной путь для проблемы с кодировкой HTML-строк (например, явная кодировка HTML-строки, полученной из буфера обмена, путем ее передачи в метод <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>), и выполняется изменение целевой платформы приложения с версии 4 на версию 4.5, этот обходной путь необходимо удалить. Если по какой-либо причине требуется старое поведение, для приложения можно выбрать целевую платформу .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="37b1f-107">If you implemented a workaround for the encoding problem with HTML-formatted strings (for example, by explicitly encoding the HTML string retrieved from the Clipboard by passing it to <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) and you're retargeting your app from version 4 to 4.5, that workaround should be removed.If the old behavior is needed for some reason, the app can target the .NET Framework 4.0 to get that behavior.</span></span>

| <span data-ttu-id="37b1f-108">name</span><span class="sxs-lookup"><span data-stu-id="37b1f-108">Name</span></span>    | <span data-ttu-id="37b1f-109">Значение</span><span class="sxs-lookup"><span data-stu-id="37b1f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="37b1f-110">Область</span><span class="sxs-lookup"><span data-stu-id="37b1f-110">Scope</span></span>   | <span data-ttu-id="37b1f-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="37b1f-111">Edge</span></span>        |
| <span data-ttu-id="37b1f-112">Version</span><span class="sxs-lookup"><span data-stu-id="37b1f-112">Version</span></span> | <span data-ttu-id="37b1f-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="37b1f-113">4.5.2</span></span>       |
| <span data-ttu-id="37b1f-114">Type</span><span class="sxs-lookup"><span data-stu-id="37b1f-114">Type</span></span>    | <span data-ttu-id="37b1f-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="37b1f-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="37b1f-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="37b1f-116">Affected APIs</span></span>

- <xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType>
