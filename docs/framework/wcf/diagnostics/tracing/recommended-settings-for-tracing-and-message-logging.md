---
title: Рекомендуемые параметры для трассировки и ведения журналов сообщений
description: Сведения о рекомендуемых параметрах трассировки и ведения журнала сообщений для различных операционных сред в WCF.
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: 71067a4d6f4cec65a148a8162c40e44d82b85784
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245333"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="8057e-103">Рекомендуемые параметры для трассировки и ведения журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="8057e-103">Recommended Settings for Tracing and Message Logging</span></span>
<span data-ttu-id="8057e-104">Этот раздел содержит описание рекомендуемых параметров трассировки и регистрации сообщений для различных операционных сред.</span><span class="sxs-lookup"><span data-stu-id="8057e-104">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="8057e-105">Параметры, рекомендуемые для рабочей среды</span><span class="sxs-lookup"><span data-stu-id="8057e-105">Recommended Settings for a Production Environment</span></span>  
 <span data-ttu-id="8057e-106">В рабочей среде, если используются источники трассировки WCF, рекомендуется в `switchValue` задать значение Warning.</span><span class="sxs-lookup"><span data-stu-id="8057e-106">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="8057e-107">При использовании источника трассировки WCF `System.ServiceModel` рекомендуется задать в атрибуте `switchValue` значение `Warning`, а в атрибуте `propagateActivity` - значение `true`.</span><span class="sxs-lookup"><span data-stu-id="8057e-107">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="8057e-108">При использовании источника трассировки, определенного пользователем, рекомендуется присвоить атрибуту `switchValue` значение `Warning, ActivityTracing`.</span><span class="sxs-lookup"><span data-stu-id="8057e-108">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="8057e-109">Это можно сделать вручную с помощью [средства редактора конфигурации (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8057e-109">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="8057e-110">Если в работе не ожидается резкого подъема производительности, во всех перечисленных выше случаях атрибуту `switchValue` можно присвоить значение `Information`, при котором генерируется достаточно большое количество данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="8057e-110">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="8057e-111">Следующий пример иллюстрирует задание описанных рекомендуемых параметров.</span><span class="sxs-lookup"><span data-stu-id="8057e-111">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="8057e-112">Параметры, рекомендуемые для развертывания или отладки</span><span class="sxs-lookup"><span data-stu-id="8057e-112">Recommended Settings for Deployment or Debugging</span></span>  
 <span data-ttu-id="8057e-113">При работе в среде развертывания или отладки рекомендуется выбирать значения `Information` или `Verbose` наряду с `ActivityTracing` как для определенных пользователем, так и для заданных `System.ServiceModel` источников трассировки.</span><span class="sxs-lookup"><span data-stu-id="8057e-113">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="8057e-114">Чтобы улучшить процесс отладки, к конфигурации необходимо добавить дополнительный источник трассировки (`System.ServiceModel.MessageLogging`) для активации функции регистрации сообщений.</span><span class="sxs-lookup"><span data-stu-id="8057e-114">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="8057e-115">Обратите внимание, что атрибут `switchValue` не влияет на этот источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="8057e-115">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="8057e-116">Следующий пример иллюстрирует задание рекомендуемых параметров с помощью общего прослушивателя, использующего `XmlWriterTraceListener`.</span><span class="sxs-lookup"><span data-stu-id="8057e-116">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging
           logEntireMessage="true"
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="8057e-117">Изменение параметров с помощью инструментария WMI</span><span class="sxs-lookup"><span data-stu-id="8057e-117">Using WMI to Modify Settings</span></span>  
 <span data-ttu-id="8057e-118">Для изменения параметров конфигурации во время работы можно использовать инструментарий WMI (выполняется путем включения атрибута `wmiProviderEnabled` в конфигурации, как показано в предыдущем примере конфигурации).</span><span class="sxs-lookup"><span data-stu-id="8057e-118">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="8057e-119">Например, для изменения во время работы уровней источника трассировки с Warning на Information можно использовать инструментарий WMI в CIM Studio.</span><span class="sxs-lookup"><span data-stu-id="8057e-119">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="8057e-120">Следует помнить о том, что такой способ отладки может значительно снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="8057e-120">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="8057e-121">Дополнительные сведения об использовании инструментария WMI см. в разделе [использование инструментарий управления Windows (WMI) для диагностики](../wmi/index.md) .</span><span class="sxs-lookup"><span data-stu-id="8057e-121">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="8057e-122">Использование корреляции событий в трассировке ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8057e-122">Enable Correlated Events in ASP.NET Tracing</span></span>  
 <span data-ttu-id="8057e-123">События ASP.NET не получают корреляционный идентификатор (ActivityID), если не включена функция трассировки событий ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8057e-123">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="8057e-124">Чтобы правильно просмотреть коррелированные события, необходимо включить трассировку событий ASP.NET с помощью следующей команды в командной консоли, которую можно вызвать, выполнив команду **Пуск**, **запустите** и введите **команду cmd**.</span><span class="sxs-lookup"><span data-stu-id="8057e-124">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="8057e-125">Для отключения трассировки событий ASP.NET используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="8057e-125">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="8057e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8057e-126">See also</span></span>

- [<span data-ttu-id="8057e-127">Использование инструментарий управления Windows (WMI) для диагностики</span><span class="sxs-lookup"><span data-stu-id="8057e-127">Using Windows Management Instrumentation for Diagnostics</span></span>](../wmi/index.md)
