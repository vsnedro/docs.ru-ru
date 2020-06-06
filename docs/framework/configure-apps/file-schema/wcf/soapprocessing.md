---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 0728e22205d4ac2c7674f7690e142aed51d42440
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399541"
---
# \<soapProcessing>

<span data-ttu-id="64bf7-101">Определяет поведение конечной точки клиента, используемое для маршалинга сообщений между различными типами привязок и версиями сообщения.</span><span class="sxs-lookup"><span data-stu-id="64bf7-101">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**
  
## <a name="syntax"></a><span data-ttu-id="64bf7-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64bf7-102">Syntax</span></span>  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64bf7-103">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="64bf7-103">Attributes and elements</span></span>  
  
<span data-ttu-id="64bf7-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="64bf7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64bf7-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="64bf7-105">Attributes</span></span>  
  
|                   | <span data-ttu-id="64bf7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="64bf7-106">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="64bf7-107">Логическое значение, указывающее, нужно ли выполнять упаковку сообщений между различными версиями SOAP.</span><span class="sxs-lookup"><span data-stu-id="64bf7-107">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="64bf7-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="64bf7-108">Child elements</span></span>

<span data-ttu-id="64bf7-109">Нет</span><span class="sxs-lookup"><span data-stu-id="64bf7-109">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="64bf7-110">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="64bf7-110">Parent elements</span></span>

|     | <span data-ttu-id="64bf7-111">Описание</span><span class="sxs-lookup"><span data-stu-id="64bf7-111">Description</span></span> |
| --- | ----------- |
| [**\<behavior>**](behavior-of-endpointbehaviors.md) | <span data-ttu-id="64bf7-112">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="64bf7-112">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="64bf7-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="64bf7-113">Remarks</span></span>

<span data-ttu-id="64bf7-114">Обработка SOAP - это процесс преобразования сообщения из одной версии в другую.</span><span class="sxs-lookup"><span data-stu-id="64bf7-114">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="64bf7-115">Служба маршрутизации Windows Communication Foundation (WCF) может преобразовывать сообщения из одного протокола в другой.</span><span class="sxs-lookup"><span data-stu-id="64bf7-115">The Windows Communication Foundation (WCF) Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="64bf7-116">Если исходящее и входящее сообщение имеют разные версии, создается новое сообщение с правильной версией.</span><span class="sxs-lookup"><span data-stu-id="64bf7-116">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="64bf7-117">Обработка сообщений от одного <xref:System.ServiceModel.Channels.MessageVersion> до другого выполняется путем составления нового сообщения WCF, содержащего текстовую часть и подходящие заголовки из входящих сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="64bf7-117">Processing messages from one <xref:System.ServiceModel.Channels.MessageVersion> to another is accomplished by constructing a new WCF message that contains the body part and relevant headers from the incoming WCF message.</span></span> <span data-ttu-id="64bf7-118">Заголовки, заданные для адресации или распознаваемые на уровне маршрутизатора, не применяются при построении нового сообщения WCF, так как эти заголовки либо имеют другую версию (в случае заголовков адресации), либо обрабатываются на этапе связи между клиентом и маршрутизатором.</span><span class="sxs-lookup"><span data-stu-id="64bf7-118">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="64bf7-119">Будет ли заголовок добавлен в исходящее сообщение, зависит от того, было ли это сообщение помечено как распознанное при прохождении уровня входящего канала.</span><span class="sxs-lookup"><span data-stu-id="64bf7-119">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="64bf7-120">Заголовки, которые не удалось распознать (например, пользовательские заголовки), не удаляются и проходят через службу маршрутизации (копируются в исходящее сообщение).</span><span class="sxs-lookup"><span data-stu-id="64bf7-120">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="64bf7-121">Текст сообщения копируется в исходящее сообщение.</span><span class="sxs-lookup"><span data-stu-id="64bf7-121">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="64bf7-122">Затем сообщение отправляется по исходящему каналу. К этому моменту создаются и добавляются все заголовки и другие данные конверта, относящиеся к этому протоколу связи или транспорта.</span><span class="sxs-lookup"><span data-stu-id="64bf7-122">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="64bf7-123">Эти шаги обработки выполняются, если определено поведение обработки SOAP.</span><span class="sxs-lookup"><span data-stu-id="64bf7-123">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="64bf7-124">Это поведение [\<soapProcessingExtension>](soapprocessing.md) конечной точки, которое применяется ко всем конечным точкам клиента (исходящих) при запуске службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="64bf7-124">This [\<soapProcessingExtension>](soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="64bf7-125">по умолчанию, [\<routing>](routing-of-servicebehavior.md) поведение создает и прикрепляет новое [\<soapProcessingExtension>](soapprocessing.md) поведение со `processMessages` значением `true` для каждой конечной точки клиента.</span><span class="sxs-lookup"><span data-stu-id="64bf7-125">default, the [\<routing>](routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="64bf7-126">Если служба маршрутизации не поддерживает выбранный протокол или нужно переопределить режим обработки по умолчанию, можно отключить обработку протокола SOAP для всей службы маршрутизации или для отдельных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="64bf7-126">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="64bf7-127">Чтобы отключить обработку SOAP для всей службы маршрутизации на всех конечных точках, присвойте `soapProcessing` атрибуту [\<routing>](routing-of-servicebehavior.md) поведения значение `false` .</span><span class="sxs-lookup"><span data-stu-id="64bf7-127">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="64bf7-128">Чтобы отключить обработку протокола SOAP для одной конечной точки, используйте это поведение и установите его атрибут `processMessages` в значение `false`. Затем присоедините это поведение к конечной точке, в которой не должен выполняться код обработки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64bf7-128">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="64bf7-129">Когда [\<routing>](routing-of-servicebehavior.md) поведение настраивает службу маршрутизации, повторное применение поведения конечной точки будет пропущено, так как оно уже существует.</span><span class="sxs-lookup"><span data-stu-id="64bf7-129">When the [\<routing>](routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
