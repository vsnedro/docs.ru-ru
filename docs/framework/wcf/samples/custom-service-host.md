---
title: Пользовательский узел службы
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 56846f4021b2a0be1801decedb02c4c637847d07
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275597"
---
# <a name="custom-service-host"></a>Пользовательский узел службы

Этот образец показывает, как применять пользовательский производный класс для класса <xref:System.ServiceModel.ServiceHost>, чтобы изменять поведение службы во время выполнения. Такой подход обеспечивает поддерживающую повторное использование альтернативу настройке большого числа служб одинаковым образом. Кроме того, в этом примере демонстрируется, как с помощью класса <xref:System.ServiceModel.Activation.ServiceHostFactory> применять пользовательский объект ServiceHost в среде размещения IIS или службы активации Windows (WAS).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a>Сценарий

 Чтобы предотвратить непреднамеренное раскрытие потенциально конфиденциальных метаданных службы, конфигурация по умолчанию для служб Windows Communication Foundation (WCF) отключает публикацию метаданных. Такое поведение является безопасным по умолчанию, но также означает, что нельзя использовать средство импорта метаданных (например, Svcutil.exe) для создания клиентского кода, необходимого для вызова службы, если в конфигурации не включено явное поведение публикации метаданных службы.  
  
 Включение публикации метаданных для большого числа служб связано с добавлением одинаковых элементов конфигурации для всех служб по отдельности, что приводит к появлению значительного объема повторяющейся информации конфигураций. Вместо конфигурации всех служб по отдельности можно написать принудительный код, один раз включающий публикацию метаданных, а затем использовать его повторно для нескольких других служб. Для этого создается новый класс, наследуемый от класса <xref:System.ServiceModel.ServiceHost>, переопределяющий метод `ApplyConfiguration`() так, чтобы принудительно добавить поведение публикации метаданных.  
  
> [!IMPORTANT]
> Для ясности этот образец демонстрирует создание незащищенной конечной точки публикации метаданных. Такие конечные точки потенциально доступны для анонимных пользователей, не прошедших проверку подлинности, и необходимо соблюдать осторожность перед развертыванием таких конечных точек, чтобы обеспечить оптимальное раскрытие метаданных службы.  
  
## <a name="implementing-a-custom-servicehost"></a>Реализация пользовательского ServiceHost

 Класс <xref:System.ServiceModel.ServiceHost> предоставляет несколько полезных виртуальных методов, которые наследующие классы могут переопределять, чтобы изменять поведение службы во время выполнения. Например, метод `ApplyConfiguration`() выполняет чтение сведений конфигурации службы из хранилища конфигураций и соответствующим образом изменяет объект <xref:System.ServiceModel.Description.ServiceDescription> ведущего приложения. Реализация по умолчанию считывает конфигурацию из файла конфигурации приложения. Пользовательские реализации могут переопределять метод `ApplyConfiguration`() для дополнительного изменения<xref:System.ServiceModel.Description.ServiceDescription> с помощью императивного кода или даже полностью заменять хранилище конфигураций по умолчанию. Например, чтобы считать конфигурацию конечной точки службы из базы данных, а не файла конфигурации приложения.  
  
 В этом примере мы хотим создать пользовательский ServiceHost, добавляющий ServiceMetadataBehavior (который включает публикацию метаданных), даже если это поведение явно не Добавлено в файл конфигурации службы. Для этого создайте новый класс, который наследует от <xref:System.ServiceModel.ServiceHost> и переопределяет `ApplyConfiguration` ().  
  
```csharp
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to
    //alter the ServiceDescription prior to opening  
    //the service host.
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 Так как мы не будем пропускать все настройки, предоставленные в файле конфигурации приложения, первое, что делает переопределение `ApplyConfiguration` (), вызывает базовую реализацию. После выполнения этого метода можно принудительно добавить в описание поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior> с помощью следующего принудительного кода.  
  
```csharp
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,
    //so we do not have any work to do.  
    return;  
}  
```  
  
 Наконец, переопределение `ApplyConfiguration`() должно добавить конечную точку метаданных по умолчанию. По соглашению для каждого URI в коллекции BaseAddresses узла службы создается одна конечная точка метаданных.  
  
```csharp
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
```  
  
## <a name="using-a-custom-servicehost-in-self-host"></a>Использование пользовательского ServiceHost в резидентной службе  

 Выполненную реализацию пользовательского ServiceHost можно использовать для добавления поведения публикации метаданных к любой службе, разместив эту службу внутри экземпляра `SelfDescribingServiceHost`. В следующем примере кода демонстрируется его использование с резидентной службой.  
  
```csharp
SelfDescribingServiceHost host =
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 Наш пользовательский узел по-прежнему считывает конфигурацию конечной точки службы из файла конфигурации приложения, как если бы мы использовали класс по умолчанию <xref:System.ServiceModel.ServiceHost> для размещения службы. Но так как в пользовательское основное приложение добавлена логика, включающая публикацию метаданных, нет необходимости явно включать поведение публикации метаданных в конфигурации. Этот подход удобен при создании приложения, содержащего несколько служб, для которых нужно включить публикацию метаданных. Он позволяет не повторять несколько раз запись одинаковых элементов конфигурации.  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a>Использование пользовательского ServiceHost в службах IIS или WAS  

 Использовать пользовательский узел службы в резидентных сценариях нетрудно, потому что за создание и открытие экземпляра основного приложения службы отвечает в итоге код вашего приложения. Однако в среде IIS или WAS инфраструктура WCF динамически создает экземпляр узла службы в ответ на входящие сообщения. В этой среде размещения также можно использовать пользовательские узлы служб, но для этого требуется дополнительный код в виде ServiceHostFactory. В следующем коде приведен класс, наследуемый от <xref:System.ServiceModel.Activation.ServiceHostFactory>, возвращающий экземпляры пользовательского `SelfDescribingServiceHost`.  
  
```csharp
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,
                                             baseAddresses);  
    }  
}  
```  
  
 Как видите, реализация пользовательского ServiceHostFactory проста. Вся пользовательская логика находится внутри реализации ServiceHost; фабрика возвращает экземпляр производного класса.  
  
 Чтобы использовать настраиваемую фабрику с реализацией службы, необходимо добавить некоторые дополнительные метаданные в SVC-файл службы.  
  
```aspx-csharp
<% @ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 Здесь мы добавили `Factory` к `@ServiceHost` директиве дополнительный атрибут и передали имя типа CLR нашей пользовательской фабрике в качестве значения атрибута. Когда IIS или WAS получает сообщение для этой службы, инфраструктура хостинга WCF сначала создает экземпляр ServiceHostFactory, а затем создает объект узла службы, вызывая `ServiceHostFactory.CreateServiceHost()` .  
  
## <a name="running-the-sample"></a>Выполнение примера  

 Несмотря на то, что этот пример обеспечивает полностью функциональную реализацию клиента и службы, точка примера заключается в том, чтобы продемонстрировать, как изменить поведение службы во время выполнения с помощью пользовательского узла. выполните следующие действия.  
  
### <a name="observe-the-effect-of-the-custom-host"></a>Наблюдение за результатом пользовательского узла
  
1. Откройте файл Web.config службы и убедитесь, что в конфигурации нет явного включения метаданных для службы.  
  
2. Откройте SVC-файл службы и убедитесь, что его @ServiceHost директива содержит атрибут Factory, указывающий имя пользовательского ServiceHostFactory.  
  
### <a name="set-up-build-and-run-the-sample"></a>Настройка, сборка и запуск примера
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](building-the-samples.md).

3. После построения решения запустите Setup.bat, чтобы настроить приложение ServiceModelSamples в IIS 7,0. Теперь каталог ServiceModelSamples должен отображаться как приложение IIS 7,0.

4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).

5. Чтобы удалить приложение IIS 7,0, запустите *Cleanup.bat*.

## <a name="see-also"></a>См. также

- [Практическое руководство. Размещение службы WCF в IIS](../feature-details/how-to-host-a-wcf-service-in-iis.md)
