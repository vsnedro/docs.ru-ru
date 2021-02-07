---
description: 'Дополнительные сведения: настраиваемое время существования'
title: Настраиваемое время существования
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 24845aaa20e60f92e2add568c81ab3d6502ebedf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732479"
---
# <a name="custom-lifetime"></a>Настраиваемое время существования

В этом примере демонстрируется написание расширения Windows Communication Foundation (WCF) для предоставления служб времени жизни для общих экземпляров службы WCF.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.

## <a name="shared-instancing"></a>Общий создание экземпляров

WCF предлагает несколько режимов создания экземпляров для экземпляров службы. Режим совместного создания экземпляров, описанный в этой статье, предоставляет способ совместного использования экземпляра службы несколькими каналами. Клиенты могут обратиться к методу фабрики в службе и создать новый канал для запуска обмена данными. В следующем фрагменте кода показано, как клиентское приложение создает новый канал для существующего экземпляра службы:

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

В отличие от других режимов создания экземпляров, режим создания общих экземпляров располагает уникальным способом освобождения экземпляров служб. По умолчанию, когда все каналы закрыты для <xref:System.ServiceModel.InstanceContext> , среда выполнения службы WCF проверяет <xref:System.ServiceModel.InstanceContextMode> , настроена ли служба для <xref:System.ServiceModel.InstanceContextMode.PerCall> или <xref:System.ServiceModel.InstanceContextMode.PerSession> , и, если это так, освобождает экземпляр и заявляет ресурсы. Если используется настраиваемый объект <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> , WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод реализации поставщика перед освобождением экземпляра. <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> `true` Значение, если метод возвращает экземпляр, в противном случае <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Реализация отвечает за уведомление о `Dispatcher` состоянии простоя с помощью метода обратного вызова. Это делается путем вызова <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> метода поставщика.

В этом образце показано, как можно отложить освобождение <xref:System.ServiceModel.InstanceContext> с временем ожидания простоя 20 секунд.

## <a name="extending-the-instancecontext"></a>Расширение InstanceContext

В WCF <xref:System.ServiceModel.InstanceContext> — это связь между экземпляром службы и `Dispatcher` . WCF позволяет расширить этот компонент среды выполнения, добавив новое состояние или поведение, используя его расширяемый шаблон объектов. Шаблон расширяемого объекта используется в WCF для расширения существующих классов среды выполнения с новыми функциональными возможностями или для добавления новых функций состояния в объект. Предусмотрено три интерфейса в шаблоне расширяемого объекта: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> и <xref:System.ServiceModel.IExtensionCollection%601>.

<xref:System.ServiceModel.IExtensibleObject%601>Интерфейс реализуется объектами, чтобы разрешить расширения, которые настраивают их функциональность.

Интерфейс <xref:System.ServiceModel.IExtension%601> реализуется объектами, которые могут быть расширениями классов типа `T`.

И, наконец, <xref:System.ServiceModel.IExtensionCollection%601> интерфейс представляет собой коллекцию <xref:System.ServiceModel.IExtension%601> реализаций, которые позволяют получить реализацию <xref:System.ServiceModel.IExtension%601> по типу.

Таким образом, для расширения необходимо <xref:System.ServiceModel.InstanceContext> реализовать <xref:System.ServiceModel.IExtension%601> интерфейс. В этом примере проекта `CustomLeaseExtension` класс содержит эту реализацию.

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

У интерфейса <xref:System.ServiceModel.IExtension%601> имеется два метода: <xref:System.ServiceModel.IExtension%601.Attach%2A> и <xref:System.ServiceModel.IExtension%601.Detach%2A>. Как видно по их именам, два этих метода вызываются, когда среда выполнения присоединяет и отсоединяет расширение экземпляра класса <xref:System.ServiceModel.InstanceContext>. В этом образце метод `Attach` используется для отслеживания объекта <xref:System.ServiceModel.InstanceContext>, который принадлежит текущему экземпляру расширения.

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

Кроме того, в расширение необходимо добавить требуемую реализацию, чтобы обеспечить поддержку продленного времени существования. Поэтому `ICustomLease` интерфейс объявляется с нужными методами и реализуется в `CustomLeaseExtension` классе.

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

Когда WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод в <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализации, этот вызов направляется к <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> методу класса `CustomLeaseExtension` . Затем `CustomLeaseExtension` проверяется его закрытое состояние, чтобы узнать, <xref:System.ServiceModel.InstanceContext> не простаивает ли. Если он бездействует, возвращается значение `true` . В противном случае запускается таймер на указанное продленное время существования.

```csharp
public bool IsIdle
{
  get
  {
    lock (thisLock)
    {
      if (isIdle)
      {
        return true;
      }
      else
      {
        StartTimer();
        return false;
      }
    }
  }
}
```

В `Elapsed` событии таймера функция обратного вызова в Dispatcher вызывается для запуска другого цикла очистки.

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

Невозможно продлить выполняющийся таймер, когда поступит новое сообщение для перемещения экземпляра в состояние простоя.

Для перехвата вызовов метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> и их перенаправления расширению <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> образец реализует `CustomLeaseExtension`. Реализация <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> содержится в классе `CustomLifetimeLease`. <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>Метод вызывается, когда WCF собирается освободить экземпляр службы. Однако в коллекции `ISharedSessionInstance` ServiceBehavior имеется только один экземпляр конкретной реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>. Это означает, что не существует способа узнать, закрыт ли объект <xref:System.ServiceModel.InstanceContext> во время проверки метода в WCF <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> . Поэтому в этом образце для сериализации запросов к методу используется блокировка потока <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> .

> [!IMPORTANT]
> Использовать блокировку потока не рекомендуется, поскольку сериализация может значительно снизить производительность приложения.

Поле закрытого члена используется в `CustomLifetimeLease` классе для отслеживания состояния простоя и возврата <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> методом. При каждом <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> вызове метода `isIdle` поле возвращается и сбрасывается в `false` .  Важно задать этому параметру значение `false` с тем, чтобы гарантировать вызов диспетчером метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

Если <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> метод возвращает значение `false` , диспетчер регистрирует функцию обратного вызова с помощью <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> метода. Этот метод получает ссылку на освобождаемый контекст <xref:System.ServiceModel.InstanceContext>. Поэтому пример кода может запросить `ICustomLease` расширение типа и проверить `ICustomLease.IsIdle` свойство в расширенном состоянии.

```csharp
public void NotifyIdle(InstanceContextIdleCallback callback,
            InstanceContext instanceContext)
{
    lock (thisLock)
    {
       ICustomLease customLease =
           instanceContext.Extensions.Find<ICustomLease>();
       customLease.Callback = callback;
       isIdle = customLease.IsIdle;
       if (isIdle)
       {
             callback(instanceContext);
       }
    }
}
```

Перед установкой `ICustomLease.IsIdle` свойства необходимо установить свойство обратного вызова, так как это важно для `CustomLeaseExtension` уведомления диспетчера о состоянии простоя. Если `ICustomLease.IsIdle` возвращает значение `true`, то закрытому элементу `isIdle` в `CustomLifetimeLease` просто устанавливается значение `true` и вызывается метод обратного вызова. Так как код удерживает блокировку, другие потоки не могут изменить значение этого закрытого члена. И при следующем вызове диспетчера вызывается метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> , который возвращает `true` и позволяет диспетчеру освободить экземпляр.

Завершив подготовительную работу для пользовательского расширения, его необходимо подключить к модели службы. Чтобы подключить `CustomLeaseExtension` реализацию к <xref:System.ServiceModel.InstanceContext> , WCF предоставляет <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> интерфейс для выполнения начальной загрузки <xref:System.ServiceModel.InstanceContext> . В этом образце класс `CustomLeaseInitializer` реализует этот интерфейс и добавляет экземпляр `CustomLeaseExtension` в коллекцию <xref:System.ServiceModel.InstanceContext.Extensions%2A> из единственной инициализации метода. Этот метод вызывается диспетчером при инициализации <xref:System.ServiceModel.InstanceContext>.

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 Наконец, <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Реализация присоединяется к модели службы с помощью <xref:System.ServiceModel.Description.IServiceBehavior> реализации. Эта реализация помещается в класс `CustomLeaseTimeAttribute`, кроме того, она является производной от базового класса <xref:System.Attribute> для предоставления этого поведения в виде атрибута.

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

Это поведение можно добавить в класс образца службы, сопроводив его заметкой в вида атрибута `CustomLeaseTime`.

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для платформа .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
