---
title: Кодирование двоичных объектов при помощи кодировщика ByteStream
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: cc63cb8de1e245c3b58fb69819e59cb815b777d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276741"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a>Кодирование двоичных объектов при помощи кодировщика ByteStream

Отправка и получение необработанных двоичных данных с помощью Windows Communication Foundation (WCF) настраивается с использованием <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> .  
  
## <a name="byte-stream-message-encoder-architecture"></a>Архитектура кодировщика сообщений потока байтов  

 Кодировщик двоичных сообщений, используемый WCF, не имеет средства для обработки, проверки или идентификации базовых двоичных данных в сообщении. Производится кодирование пакета данных в XML, отправка, получение и декодирование. Кодировщик обрабатывает данные после передачи транспортной подсистеме, до передачи сообщения в очередь сообщений. С технической точки зрения двоичный кодировщик упаковывает данные сообщения в элементы `<binary>` и удаляет эти элементы после его получения.  
  
## <a name="using-the-byte-stream-message-encoder"></a>Использование кодировщика сообщений потока байтов  

 В следующем примере показан контракт службы, реализующий кодировщик сообщений потока байтов.  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 В следующем примере показан вызов службы.  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 Если служба реализует инфраструктуру сообщения (например, маршрутизатора), то сообщение обрабатывается без проверки и любого другого взаимодействия с сообщением, как показано в следующем примере.  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a>Сценарии  

 Кодировщик байтового потока полезен в следующих сценариях.  
  
- Передача изображения JPEG между компьютерами с помощью WCF. В данном сценарии изображение поступает через этот транспорт из внешнего источника и отправляемые данные представляют собой необработанные байты, из которых состоит изображение. Служба получает двоичные данные и отображает изображение.  
  
- Чтение данных из очереди сообщений и их обработка. Сообщение считывается из диспетчера очереди сообщений и передается по каналу очереди сообщений для обработки. Канал очереди сообщений будет работать как диспетчер очереди в стеке канала WCF.  
  
 В случае если сообщение отправляется по каналу очереди сообщений, отправитель не управляет байтами, получаемыми от диспетчера очереди. Если принимающий процесс не может считывать необработанные байты, полученное сообщение будет рассматриваться как имеющее неправильный формат и не будет обработано. Предполагается, что принимающий процесс умеет преобразовывать полученные байты в поддерживаемый формат.
