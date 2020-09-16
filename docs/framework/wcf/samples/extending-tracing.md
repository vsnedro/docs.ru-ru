---
title: Расширение трассировки
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: f2b9deb346077609193ec08c2c01b10a3ad9357b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556516"
---
# <a name="extend-tracing"></a>Расширить трассировку

В этом примере показано, как расширить функцию трассировки Windows Communication Foundation (WCF) путем написания пользовательских трассировок действий в клиенте и в коде службы. Написание трассировки определяемых пользователем действий позволяет пользователю создавать действия трассировки и группировать трассировки в логические единицы работы. Кроме того, возможно согласование действий с помощью передач (в рамках одной конечной точки) и распространения (между конечными точками). В этом образце трассировка включается как для клиента, так и для службы. Дополнительные сведения о включении трассировки в файлах конфигурации клиента и службы см. в разделе [Трассировка и ведение журнала сообщений](tracing-and-message-logging.md).  
  
 Этот образец основан на [Начало работы](getting-started-sample.md).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a>Трассировка и распространение действий  
 Определяемая пользователем трассировка действий позволяет пользователю создавать собственные действия трассировки для группирования трассировок в логические единицы работы, сопоставлять действия посредством передачи и распространения, а также уменьшить затраты на производительность трассировки WCF (например, стоимость дискового пространства в файле журнала).  
  
### <a name="add-custom-sources"></a>Добавление пользовательских источников  
 Пользовательские трассировки можно добавлять как в код клиента, так и в код службы. Добавление источников трассировки в файлы конфигурации клиента или службы позволяет записывать и отображать эти пользовательские трассировки в средстве [Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md). В следующем примере кода показано, как добавить в файл конфигурации пользовательский источник трассировки с именем `ServerCalculatorTraceSource`.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>
....
```  
  
### <a name="correlate-activities"></a>Корреляция действий  
 Для непосредственного согласования действий между конечными точками в источнике трассировки `propagateActivity` атрибут `true` должен иметь значение `System.ServiceModel`. Кроме того, для распространения трассировок без выполнения действий WCF трассировка действий ServiceModel должна быть отключена. Это показано в следующем примере кода.  
  
> [!NOTE]
> Отключение трассировки действия ServiceModel не эквивалентно указанию значения off для уровня трассировки, обозначаемого свойством `switchValue`.  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessen-performance-cost"></a>Снижение затрат на производительность  
 Установка для свойства `ActivityTracing` значения off в трассировке `System.ServiceModel` создает файл трассировки, который содержит только пользовательские трассировки действий без включения каких-либо трассировок действий ServiceModel. Исключение трассировки действий ServiceModel приводит к тому, что файл журнала намного меньше. Однако возможность корреляции трассировок обработки WCF теряется.  
  
## <a name="set-up-build-and-run-the-sample"></a>Настройка, сборка и запуск примера  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).  
  
## <a name="see-also"></a>См. также

- [Образцы наблюдения за AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))
