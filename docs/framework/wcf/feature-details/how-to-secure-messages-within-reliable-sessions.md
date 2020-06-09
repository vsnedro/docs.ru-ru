---
title: Практическое руководство. Защита сообщений с помощью надежных сеансов
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: 306d0f96b5163fe5c24d270b4b9a7c1d3f499e7e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596959"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="23862-102">Практическое руководство. Защита сообщений с помощью надежных сеансов</span><span class="sxs-lookup"><span data-stu-id="23862-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="23862-103">В этом разделе описывается обеспечение безопасности на уровне сообщения в ходе надежного сеанса обмена сообщениями с использованием одной из предоставляемых системой привязок, которые поддерживают такие сеансы, но не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="23862-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="23862-104">Включите безопасный, надежный сеанс принудительно с помощью кода или декларативно в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="23862-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="23862-105">В этой процедуре для разрешения защищенного, надежного сеанса используются файлы конфигурации клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="23862-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="23862-106">Эта процедура включает выполнение трех основных задач, а именно:</span><span class="sxs-lookup"><span data-stu-id="23862-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="23862-107">необходимо задать, что клиент и служба обмениваются сообщениями в ходе надежного сеанса;</span><span class="sxs-lookup"><span data-stu-id="23862-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="23862-108">необходимо обеспечить безопасность на уровне сообщения в ходе надежного сеанса;</span><span class="sxs-lookup"><span data-stu-id="23862-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="23862-109">необходимо задать тип учетных данных клиента, который должен использоваться при проверке подлинности клиента в службе.</span><span class="sxs-lookup"><span data-stu-id="23862-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="23862-110">В первой задаче важно, чтобы элемент конфигурации конечной точки содержал `bindingConfiguration` атрибут, который ссылается на конфигурацию привязки с именем (в этом примере) `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="23862-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="23862-111">[**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)Элемент Configuration затем ссылается на это имя, чтобы включить надежные сеансы, задав `enabled` атрибуту [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) элемента значение `true` .</span><span class="sxs-lookup"><span data-stu-id="23862-111">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="23862-112">Можно потребовать гарантии упорядоченной доставки сообщений в ходе надежного сеанса, присвоив атрибуту `ordered` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="23862-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="23862-113">Исходный экземпляр примера, на котором основана эта процедура конфигурации, см. в разделе [надежный сеанс WS](../samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="23862-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="23862-114">Ключевые элементы второй задачи выполняются путем установки `mode` атрибута **\<security>** элемента, содержащегося в **\<binding>** элементе клиента и службы, на `Message` .</span><span class="sxs-lookup"><span data-stu-id="23862-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="23862-115">Наиболее важными элементами третьей задачи является установка `clientCredentialType` атрибута **\<message>** элемента, содержащегося в **\<security>** элементе клиента и службы, в значение `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="23862-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="23862-116">При использовании безопасности сообщений с надежными сеансами надежный обмен сообщениями пытается проверить подлинность клиента, не прошедшего проверку подлинности, до тех пор, пока не будет вызвано исключение при первом сбое.</span><span class="sxs-lookup"><span data-stu-id="23862-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="23862-117">Настройка службы с помощью WSHttpBinding для использования надежного сеанса</span><span class="sxs-lookup"><span data-stu-id="23862-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="23862-118">Эта процедура описана в разделе [как обмениваться сообщениями в надежном сеансе](how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="23862-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="23862-119">Настройка клиента с помощью WSHttpBinding для использования надежного сеанса</span><span class="sxs-lookup"><span data-stu-id="23862-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="23862-120">Эта процедура описана в разделе [как обмениваться сообщениями в надежном сеансе](how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="23862-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="23862-121">Установка режима и ClientCredentialType в конфигурации</span><span class="sxs-lookup"><span data-stu-id="23862-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="23862-122">Добавьте соответствующий элемент привязки в [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) элемент файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="23862-122">Add an appropriate binding element to the [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="23862-123">В следующем примере добавляется [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="23862-123">The following example adds a [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="23862-124">Добавьте **\<binding>** элемент и присвойте его `name` атрибуту соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="23862-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="23862-125">В примере используется имя `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="23862-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="23862-126">Добавьте **\<security>** элемент и присвойте `mode` атрибуту значение `Message` .</span><span class="sxs-lookup"><span data-stu-id="23862-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="23862-127">В **\<security>** элементе добавьте **\<message>** элемент и присвойте `clientCredentialType` атрибуту значение `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="23862-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
