---
title: Использование служб TCP
description: Класс TcpClient абстрагирует сведения, чтобы создать сокет для запроса и получения данных по протоколу TCP. Используйте функцию обработки потока .NET Framework для чтения и записи данных.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, TCP
- receiving data, TCP
- TcpClient class, about TcpClient class
- data requests, TCP
- application protocols, TCP
- network resources, TCP
- sending data, TCP
- TCP
- protocols, TCP
- Internet, TCP
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
ms.openlocfilehash: 329701e8f11ca7f87c40ee8b2cc6a337435242b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501967"
---
# <a name="using-tcp-services"></a><span data-ttu-id="ddef3-104">Использование служб TCP</span><span class="sxs-lookup"><span data-stu-id="ddef3-104">Using TCP Services</span></span>

<span data-ttu-id="ddef3-105">Класс <xref:System.Net.Sockets.TcpClient> запрашивает данные из ресурса в Интернете по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="ddef3-105">The <xref:System.Net.Sockets.TcpClient> class requests data from an Internet resource using TCP.</span></span> <span data-ttu-id="ddef3-106">Методы и свойства **TcpClient** абстрагируют сведения для создания <xref:System.Net.Sockets.Socket> с целью запроса и получения данных по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="ddef3-106">The methods and properties of **TcpClient** abstract the details for creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using TCP.</span></span> <span data-ttu-id="ddef3-107">Так как подключение к удаленному устройству представлено в виде потока, данные можно считывать и записывать с помощью методов работы с потоками платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ddef3-107">Because the connection to the remote device is represented as a stream, data can be read and written with .NET Framework stream-handling techniques.</span></span>

<span data-ttu-id="ddef3-108">Протокол TCP устанавливает соединение с удаленной конечной точкой, а затем использует его для отправки и получения пакетов данных.</span><span class="sxs-lookup"><span data-stu-id="ddef3-108">The TCP protocol establishes a connection with a remote endpoint and then uses that connection to send and receive data packets.</span></span> <span data-ttu-id="ddef3-109">Протокол TCP отвечает за отправку пакетов данных в конечную точку и их сборку в правильном порядке после доставки.</span><span class="sxs-lookup"><span data-stu-id="ddef3-109">TCP is responsible for ensuring that data packets are sent to the endpoint and assembled in the correct order when they arrive.</span></span>

<span data-ttu-id="ddef3-110">Чтобы установить подключение TCP, необходимо знать адрес сетевого устройства, в котором размещается нужная служба, и порт TCP, который служба использует для обмена данными.</span><span class="sxs-lookup"><span data-stu-id="ddef3-110">To establish a TCP connection, you must know the address of the network device hosting the service you need and you must know the TCP port that the service uses to communicate.</span></span> <span data-ttu-id="ddef3-111">Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). См. документ [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Реестр названий служб и номеров портов транспортных протоколов).</span><span class="sxs-lookup"><span data-stu-id="ddef3-111">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="ddef3-112">Службы, отсутствующие в списке IANA, могут иметь номера портов в диапазоне от 1024 до 65535.</span><span class="sxs-lookup"><span data-stu-id="ddef3-112">Services not on the Iana list can have port numbers in the range 1,024 to 65,535.</span></span>

<span data-ttu-id="ddef3-113">В приведенном ниже примере показано, как настроить **TcpClient** для подключения к серверу времени через порт TCP 13:</span><span class="sxs-lookup"><span data-stu-id="ddef3-113">The following example demonstrates setting up a **TcpClient** to connect to a time server on TCP port 13:</span></span>

```vb
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeClient
    Private const portNum As Integer = 13
    Private const hostName As String = "host.contoso.com"

    ' Entry point  that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Try
            Dim client As New TcpClient(hostName, portNum)

            Dim ns As NetworkStream = client.GetStream()

            Dim bytes(1024) As Byte
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)

            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))

        Catch e As Exception
            Console.WriteLine(e.ToString())
        End Try

        client.Close()

        Return 0
    End Function
End Class
```

```csharp
using System;
using System.Net.Sockets;
using System.Text;

public class TcpTimeClient
{
    private const int portNum = 13;
    private const string hostName = "host.contoso.com";

    public static int Main(String[] args)
    {
        try
        {
            var client = new TcpClient(hostName, portNum);

            NetworkStream ns = client.GetStream();

            byte[] bytes = new byte[1024];
            int bytesRead = ns.Read(bytes, 0, bytes.Length);

            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));

            client.Close();

        }
        catch (Exception e)
        {
            Console.WriteLine(e.ToString());
        }

        return 0;
    }
}
```

<span data-ttu-id="ddef3-114"><xref:System.Net.Sockets.TcpListener> используется для отслеживания входящих запросов на порте и последующего создания объекта **Socket** или **TcpClient**, который управляет подключением к клиенту.</span><span class="sxs-lookup"><span data-stu-id="ddef3-114"><xref:System.Net.Sockets.TcpListener> is used to monitor a TCP port for incoming requests and then create either a **Socket** or a **TcpClient** that manages the connection to the client.</span></span> <span data-ttu-id="ddef3-115">Метод <xref:System.Net.Sockets.TcpListener.Start%2A> включает прослушивание порта, а метод <xref:System.Net.Sockets.TcpListener.Stop%2A> отключает его.</span><span class="sxs-lookup"><span data-stu-id="ddef3-115">The <xref:System.Net.Sockets.TcpListener.Start%2A> method enables listening, and the <xref:System.Net.Sockets.TcpListener.Stop%2A> method disables listening on the port.</span></span> <span data-ttu-id="ddef3-116">Метод <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> принимает входящие запросы на подключение и создает **TcpClient** для их обработки, а метод <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> делает то же самое, но создает **Socket**.</span><span class="sxs-lookup"><span data-stu-id="ddef3-116">The <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> method accepts incoming connection requests and creates a **TcpClient** to handle the request, and the <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> method accepts incoming connection requests and creates a **Socket** to handle the request.</span></span>

<span data-ttu-id="ddef3-117">В приведенном ниже примере показано создание сервера времени в сети с использованием **TcpListener** для наблюдения за портом TCP 13.</span><span class="sxs-lookup"><span data-stu-id="ddef3-117">The following example demonstrates creating a network time server using a **TcpListener** to monitor TCP port 13.</span></span> <span data-ttu-id="ddef3-118">При получении входящего запроса на подключение сервер времени сообщает в ответ текущую дату и время с сервера узла.</span><span class="sxs-lookup"><span data-stu-id="ddef3-118">When an incoming connection request is accepted, the time server responds with the current date and time from the host server.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeServer

    Private const portNum As Integer = 13

    ' Entry point that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Dim done As Boolean = False

        Dim listener As New TcpListener(IPAddress.Any, portNum)

        listener.Start()

        While Not done
            Console.Write("Waiting for connection...")
            Dim client As TcpClient = listener.AcceptTcpClient()

            Console.WriteLine("Connection accepted.")
            Dim ns As NetworkStream = client.GetStream()

            Dim byteTime As Byte() = _
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())

            Try
                ns.Write(byteTime, 0, byteTime.Length)
                ns.Close()
                client.Close()
            Catch e As Exception
                Console.WriteLine(e.ToString())
            End Try
        End While

        listener.Stop()

        Return 0
    End Function
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class TcpTimeServer
{

    private const int portNum = 13;

    public static int Main(String[] args)
    {
        bool done = false;

        var listener = new TcpListener(IPAddress.Any, portNum);

        listener.Start();

        while (!done)
        {
            Console.Write("Waiting for connection...");
            TcpClient client = listener.AcceptTcpClient();

            Console.WriteLine("Connection accepted.");
            NetworkStream ns = client.GetStream();

            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());

            try
            {
                ns.Write(byteTime, 0, byteTime.Length);
                ns.Close();
                client.Close();
            }
            catch (Exception e)
            {
                Console.WriteLine(e.ToString());
            }
        }

        listener.Stop();

        return 0;
    }

}
```
