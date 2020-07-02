---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614748"
---
### <a name="serialport-background-thread-exceptions"></a><span data-ttu-id="15bea-101">Исключения фонового потока SerialPort</span><span class="sxs-lookup"><span data-stu-id="15bea-101">SerialPort background thread exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="15bea-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="15bea-102">Details</span></span>

<span data-ttu-id="15bea-103">Фоновые потоки, созданные с помощью потоков <xref:System.IO.Ports.SerialPort>, больше не завершают процесс при возникновении исключений ОС.</span><span class="sxs-lookup"><span data-stu-id="15bea-103">Background threads created with <xref:System.IO.Ports.SerialPort> streams no longer terminate the process when OS exceptions are thrown.</span></span> <br/><span data-ttu-id="15bea-104">В приложениях, предназначенных для .NET Framework 4.7 и более ранних версий, процесс завершался при возникновении исключений операционной системы в фоновом потоке, созданном с помощью потока <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="15bea-104">In applications that target the .NET Framework 4.7 and earlier versions, a process is terminated when an operating system exception is thrown on a background thread created with a <xref:System.IO.Ports.SerialPort> stream.</span></span> <br/><span data-ttu-id="15bea-105">В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, фоновые потоки ожидают события ОС, связанные с активным последовательным портом, и могут аварийно завершиться в некоторых случаях, например при внезапном удалении последовательного порта.</span><span class="sxs-lookup"><span data-stu-id="15bea-105">In applications that target the .NET Framework 4.7.1 or a later version, background threads wait for OS events related to the active serial port and could crash in some cases, such as sudden removal of the serial port.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="15bea-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="15bea-106">Suggestion</span></span>

<span data-ttu-id="15bea-107">Для приложений, предназначенных для .NET Framework 4.7.1, можно отказаться от обработки исключений, добавив следующую строку в раздел `<runtime>` файла `app.config`:</span><span class="sxs-lookup"><span data-stu-id="15bea-107">For apps that target the .NET Framework 4.7.1, you can opt out of the exception handling if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

<span data-ttu-id="15bea-108">Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.7.1 или более поздней версии, можно включить обработку исключений, добавив следующую строку в раздел `<runtime>` файла `app.config`:</span><span class="sxs-lookup"><span data-stu-id="15bea-108">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.1 or later, you can opt in to the exception handling by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| <span data-ttu-id="15bea-109">name</span><span class="sxs-lookup"><span data-stu-id="15bea-109">Name</span></span>    | <span data-ttu-id="15bea-110">Значение</span><span class="sxs-lookup"><span data-stu-id="15bea-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="15bea-111">Область</span><span class="sxs-lookup"><span data-stu-id="15bea-111">Scope</span></span>   | <span data-ttu-id="15bea-112">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="15bea-112">Minor</span></span>       |
| <span data-ttu-id="15bea-113">Версия</span><span class="sxs-lookup"><span data-stu-id="15bea-113">Version</span></span> | <span data-ttu-id="15bea-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="15bea-114">4.7.1</span></span>       |
| <span data-ttu-id="15bea-115">Type</span><span class="sxs-lookup"><span data-stu-id="15bea-115">Type</span></span>    | <span data-ttu-id="15bea-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="15bea-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="15bea-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="15bea-117">Affected APIs</span></span>

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
