---
title: 'How to: Write Event Information to a Text File'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs [Visual Studio], writing event information
- text files [Visual Basic], writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
ms.openlocfilehash: 6e83f8450ca7be8a2dcd5ff43eab3dd2ec0d2f1b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410066"
---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a><span data-ttu-id="46022-102">Практическое руководство. Запись сведений о событиях в текстовый файл (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46022-102">How to: Write Event Information to a Text File (Visual Basic)</span></span>

<span data-ttu-id="46022-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.</span><span class="sxs-lookup"><span data-stu-id="46022-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="46022-104">В этом примере показано использование метода `My.Application.Log.WriteEntry` для записи данных трассировки в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="46022-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information to a log file.</span></span>

### <a name="to-add-and-configure-the-file-log-listener"></a><span data-ttu-id="46022-105">Добавление и настройка прослушивателя файлового журнала</span><span class="sxs-lookup"><span data-stu-id="46022-105">To add and configure the file log listener</span></span>

1. <span data-ttu-id="46022-106">Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="46022-106">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="46022-107">\- или -</span><span class="sxs-lookup"><span data-stu-id="46022-107">\- or -</span></span>

     <span data-ttu-id="46022-108">Если файл app.config отсутствует, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="46022-108">If there is no app.config file:</span></span>

    1. <span data-ttu-id="46022-109">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="46022-109">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="46022-110">В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.</span><span class="sxs-lookup"><span data-stu-id="46022-110">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="46022-111">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="46022-111">Click **Add**.</span></span>

2. <span data-ttu-id="46022-112">Найдите раздел `<listeners>` в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="46022-112">Locate the `<listeners>` section in the application configuration file.</span></span>

     <span data-ttu-id="46022-113">Вы найдете раздел \<listeners> в разделе \<source> с атрибутом имени DefaultSource, вложенным в раздел \<system.diagnostics> , который, в свою очередь, вложен в раздел \<configuration> верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="46022-113">You will find the \<listeners> section in the \<source> section with the name attribute "DefaultSource", which is nested under the \<system.diagnostics> section, which is nested under the top-level \<configuration> section.</span></span>

3. <span data-ttu-id="46022-114">Добавьте в этот раздел `<listeners>` следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="46022-114">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="FileLogListener" />
    ```

4. <span data-ttu-id="46022-115">Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе верхнего уровня `<configuration>`.</span><span class="sxs-lookup"><span data-stu-id="46022-115">Locate the `<sharedListeners>` section in the `<system.diagnostics>` section, nested under the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="46022-116">Добавьте в этот раздел `<sharedListeners>` следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="46022-116">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="FileLogListener"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
              PublicKeyToken=b03f5f7f11d50a3a"
        initializeData="FileLogListenerWriter"
        location="Custom"
        customlocation="c:\temp\" />
    ```

     <span data-ttu-id="46022-117">Измените значение атрибута `customlocation` на путь к каталогу журнала.</span><span class="sxs-lookup"><span data-stu-id="46022-117">Change the value of the `customlocation` attribute to the log directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="46022-118">Чтобы задать значение свойства прослушивателя, используйте атрибут, имеющий то же имя, что и свойство, но со всеми строчными буквами в имени.</span><span class="sxs-lookup"><span data-stu-id="46022-118">To set the value of a listener property, use an attribute that has the same name as the property, with all letters in the name lowercase.</span></span> <span data-ttu-id="46022-119">Например, атрибуты `location` и `customlocation` задают значения свойств <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> и <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A>.</span><span class="sxs-lookup"><span data-stu-id="46022-119">For example, the `location` and `customlocation` attributes set the values of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> and <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> properties.</span></span>

### <a name="to-write-event-information-to-the-file-log"></a><span data-ttu-id="46022-120">Запись информации о событии в файловый журнал</span><span class="sxs-lookup"><span data-stu-id="46022-120">To write event information to the file log</span></span>

<span data-ttu-id="46022-121">Для записи сведений в файловый журнал используйте метод `My.Application.Log.WriteEntry` или `My.Application.Log.WriteException`.</span><span class="sxs-lookup"><span data-stu-id="46022-121">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the file log.</span></span> <span data-ttu-id="46022-122">Дополнительные сведения см. в разделах [Практическое руководство. Запись сообщений в журнал](how-to-write-log-messages.md) и [Практическое руководство. Запись в журнал сведений об исключениях](how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="46022-122">For more information, see [How to: Write Log Messages](how-to-write-log-messages.md) and [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

<span data-ttu-id="46022-123">После настройки прослушивателя файлового журнала для сборки он получает все сообщения, которые записываются объектом `My.Application.Log` из этой сборки.</span><span class="sxs-lookup"><span data-stu-id="46022-123">After you configure the file log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="46022-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46022-124">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="46022-125">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="46022-125">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="46022-126">Практическое руководство. Запись в журнал сведений об исключениях</span><span class="sxs-lookup"><span data-stu-id="46022-126">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
