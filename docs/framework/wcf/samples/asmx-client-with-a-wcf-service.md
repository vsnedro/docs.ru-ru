---
description: Дополнительные сведения о клиенте ASMX со службой WCF
title: Клиент ASMX со службой WCF
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: b9f561f6651c591556f821478c4c4bfd7d7da23d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778923"
---
# <a name="asmx-client-with-a-wcf-service"></a>Клиент ASMX со службой WCF

В этом примере показано, как создать службу с помощью Windows Communication Foundation (WCF), а затем получить доступ к службе из клиента, не являющегося клиентом WCF, например клиента ASMX.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

Этот образец содержит консольную программу клиента (EXE) и библиотеку службы (DLL), размещаемую в службах IIS. Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (`Add`, `Subtract`, `Multiply` и `Divide`). Клиент ASMX осуществляет синхронные вызовы математической операции, а служба отправляет в ответ результат.

Служба реализует контракт `ICalculator`, как показано в следующем примере кода.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

Объекты <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Xml.Serialization.XmlSerializer> сопоставляют типы среды CLR с XML-представлением. <xref:System.Runtime.Serialization.DataContractSerializer> интерпретирует некоторые XML-представления не так, как XmlSerializer. Генераторы прокси, отличные от WCF, такие как Wsdl.exe, создают более подходящий интерфейс при использовании XmlSerializer. Объект <xref:System.ServiceModel.XmlSerializerFormatAttribute> применяется к `ICalculator` интерфейсу, чтобы убедиться, что XmlSerializer используется для СОПОСТАВЛЕНИЯ типов CLR с XML. Реализация службы выполняет вычисления и возвращает соответствующий результат.

Служба предоставляет одну конечную точку для взаимодействия с ней; конечная точка определяется в файле конфигурации (Web.config). Конечная точка состоит из адреса, привязки и контракта. Служба предоставляет конечную точку по базовому адресу, предоставляемую узлом IIS. Для атрибута `binding` задается значение basicHttpBinding, что обеспечивает взаимодействие по протоколу HTTP с использованием протокола SOAP 1.1, который совместим со спецификацией WS-I BasicProfile 1.1, как показано в следующем образце конфигурации.

```xml
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->
    <endpoint address=""
              binding="basicHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
</services>
```

Клиент ASMX взаимодействует со службой WCF, используя типизированный прокси-сервер, созданный служебной программой языка описания веб-служб (WSDL) (Wsdl.exe). Типизированный прокси содержится в файле generatedClient.cs. Специальная программа WSDL извлекает метаданные для заданной службы и создает типизированный прокси, который будет использоваться клиентом для взаимодействия. По умолчанию платформа не предоставляет никаких метаданных. Чтобы предоставить метаданные, необходимые для создания прокси-сервера, необходимо добавить [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) и задать `httpGetEnabled` для атрибута значение, `True` как показано в следующей конфигурации.

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <!-- Setting httpGetEnabled to True on the serviceMetadata
           behavior exposes the service's wsdl at <base address>?wsdl :
           http://localhost/servicemodelsamples/service.svc?wsdl -->
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

Чтобы создать типизированную учетную запись-посредник, выполните следующую команду из командной строки в каталоге клиента.

```console
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl
```

С помощью созданного типизированного прокси клиент может обращаться к заданной конечной точке службы путем задания в конфигурации соответствующего адреса. Чтобы задать конечную точку для взаимодействия, клиент использует файл конфигурации (App.config).

```xml
<appSettings>
  <add key="CalculatorServiceAddress"
       value="http://localhost/ServiceModelSamples/service.svc"/>
</appSettings>
```

Реализация клиента создает экземпляр типизированного прокси, чтобы начать взаимодействие со службой.

```csharp
// Create a client to the CalculatorService.
using (CalculatorService client = new CalculatorService())
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

    // Call the Subtract service operation.
    value1 = 145.00D;
    value2 = 76.54D;
    result = client.Subtract(value1, value2);
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

    // Call the Multiply service operation.
    value1 = 9.00D;
    value2 = 81.25D;
    result = client.Multiply(value1, value2);
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

    // Call the Divide service operation.
    value1 = 22.00D;
    value2 = 7.00D;
    result = client.Divide(value1, value2);
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

}

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).

> [!NOTE]
> Дополнительные сведения о передаче и возврате сложных типов данных см. в разделе [Привязка данных в Windows Formsном клиенте](data-binding-in-a-windows-forms-client.md), [привязка данных в Windows Presentation Foundationном клиенте](data-binding-in-a-wpf-client.md)и [привязка данных в клиенте ASP.NET](data-binding-in-an-aspnet-client.md) .

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для платформа .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`
