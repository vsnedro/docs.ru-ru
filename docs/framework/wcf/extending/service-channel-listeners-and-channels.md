---
description: 'Дополнительные сведения о службе: прослушиватели каналов и каналы'
title: 'Служба: прослушиватели каналов и каналы'
ms.date: 03/30/2017
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
ms.openlocfilehash: 2a092813faaa6f8964158adb55d11f21bf3ee60a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643999"
---
# <a name="service-channel-listeners-and-channels"></a>Служба: прослушиватели каналов и каналы

Существует три категории объектов Channel: каналы, прослушиватели каналов и фабрики каналов. Каналы - это интерфейс между приложением и стеком канала. Прослушиватели каналов отвечают за создание каналов на принимающей (ожидающей передачи данных) стороне, обычно в ответ на новое входящее сообщение или подключение. Фабрики каналов отвечают за создание каналов на передающей стороне для инициации связи с конечной точкой.

## <a name="channel-listeners-and-channels"></a>Прослушиватели каналов и каналы

Прослушиватели каналов отвечают за создание каналов и прием сообщений с более низкого уровня или из сети. Принятые сообщения доставляются на уровень выше с помощью канала, созданного прослушивателем каналов.

Следующая схема показывает процесс приема сообщения и доставки его на уровень выше.

![Прослушиватели каналов и каналы](./media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")

Прослушиватель каналов принимает сообщения и доставляет их на уровень выше через каналы.

Процесс можно концептуально представить в виде очереди внутри каждого канала, хотя реализация может не использовать очередь. Прослушиватель канала отвечает за прием сообщений с более низкого уровня или из сети и добавление их в очередь. Канал отвечает за получение сообщений из очереди и передачу их на уровень выше, откуда приходит запрос на сообщение, например вызовом команды `Receive` для данного канала.

WCF предоставляет вспомогательные методы базового класса для этого процесса. Схему вспомогательных классов канала, обсуждаемых в этой статье, см. в разделе [Общие сведения о модели каналов](channel-model-overview.md).

- <xref:System.ServiceModel.Channels.CommunicationObject>Класс реализует <xref:System.ServiceModel.ICommunicationObject> и применяет конечный автомат, описанный в шаге 2 [разработки каналов](developing-channels.md).

- <xref:System.ServiceModel.Channels.ChannelManagerBase>Класс реализует <xref:System.ServiceModel.Channels.CommunicationObject> и предоставляет унифицированный базовый класс для <xref:System.ServiceModel.Channels.ChannelFactoryBase> и <xref:System.ServiceModel.Channels.ChannelListenerBase> . Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> работает совместно с классом <xref:System.ServiceModel.Channels.ChannelBase> - базовым классом, реализующим интерфейс <xref:System.ServiceModel.Channels.IChannel>.

- <xref:System.ServiceModel.Channels.ChannelFactoryBase>Класс реализует <xref:System.ServiceModel.Channels.ChannelManagerBase> и <xref:System.ServiceModel.Channels.IChannelFactory> объединяет `CreateChannel` перегрузки в один `OnCreateChannel` абстрактный метод.

- <xref:System.ServiceModel.Channels.ChannelListenerBase>Класс реализует <xref:System.ServiceModel.Channels.IChannelListener> . Он отвечает за базовое управление состоянием.

Следующее обсуждение основано на примере [Transport: UDP](../samples/transport-udp.md) .

## <a name="creating-a-channel-listener"></a>Создание прослушивателя каналов

Объект `UdpChannelListener` , который реализуется в примере, является производным от <xref:System.ServiceModel.Channels.ChannelListenerBase> класса. Он использует один UDP-сокет для приема датаграмм. Метод `OnOpen` принимает данные через UDP-сокет в асинхронном цикле. Затем данные преобразуются в сообщения с помощью системы кодирования:

```csharp
message = UdpConstants.MessageEncoder.ReadMessage(
  new ArraySegment<byte>(buffer, 0, count),
  bufferManager
);
```

Поскольку один канал датаграмм представляет сообщения, приходящие из нескольких источников, `UdpChannelListener` - одноэлементный прослушиватель. <xref:System.ServiceModel.Channels.IChannel>Одновременно с этим прослушивателем связано не более одного активного времени. В образце создается новый экземпляр только в том случае, если канал, возвращенный методом <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A>, был впоследствии освобожден. При получении сообщения оно помещается в очередь в этот одноэлементный канал.

### <a name="udpinputchannel"></a>UdpInputChannel

`UdpInputChannel`Класс реализует <xref:System.ServiceModel.Channels.IInputChannel> . Он состоит из очереди входящих сообщений, которая заполняется сокетом прослушивателя `UdpChannelListener`. Эти сообщения выводятся из очереди <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A> методом.
