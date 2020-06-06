---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: f5bcd142fb2b032ea179bcbba68fee53b98d2d77
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736315"
---
# \<transactionFlow>
<span data-ttu-id="b8896-101">Задает поддержку потока транзакций для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b8896-101">Specifies transaction flow support for the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**  
  
## <a name="syntax"></a><span data-ttu-id="b8896-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8896-102">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8896-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b8896-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b8896-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b8896-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8896-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b8896-105">Attributes</span></span>  
  
|<span data-ttu-id="b8896-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b8896-106">Attribute</span></span>|<span data-ttu-id="b8896-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b8896-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8896-108">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="b8896-108">transactionProtocol</span></span>|<span data-ttu-id="b8896-109">Задает используемый протокол транзакций.</span><span class="sxs-lookup"><span data-stu-id="b8896-109">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="b8896-110">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="b8896-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b8896-111">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="b8896-111">-   OleTransactions</span></span><br /><span data-ttu-id="b8896-112">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="b8896-112">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="b8896-113">Значение по умолчанию - OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="b8896-113">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="b8896-114">Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="b8896-114">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8896-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b8896-115">Child Elements</span></span>  
 <span data-ttu-id="b8896-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b8896-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8896-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b8896-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b8896-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="b8896-118">Element</span></span>|<span data-ttu-id="b8896-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b8896-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b8896-120">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b8896-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8896-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="b8896-121">Remarks</span></span>  
 <span data-ttu-id="b8896-122">Этот элемент позволяет включить или отключить входящий поток транзакций в параметрах привязки конечной точки, а также задать необходимый формат протокола для входящих транзакций.</span><span class="sxs-lookup"><span data-stu-id="b8896-122">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="b8896-123">Дополнительные сведения об использовании этого элемента конфигурации см. в разделе [Конфигурация транзакций ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) и [Включение потока транзакций](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="b8896-123">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="b8896-124">При использовании протокола `OleTransactions` для реализации потока транзакций от одной конечной точки к другой время ожидания транзакции может быть потеряно, если целевая конечная точка попытается запустить поток снова, используя любой протокол, отличный от `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="b8896-124">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="b8896-125">Это может привести к тому, что время ожидания для всех узлов, находящихся ниже перехода OleTransactions, окажется больше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="b8896-125">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8896-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b8896-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b8896-127">Конфигурация транзакции ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b8896-127">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="b8896-128">Включение потока транзакций</span><span class="sxs-lookup"><span data-stu-id="b8896-128">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="b8896-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="b8896-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b8896-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b8896-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b8896-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b8896-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
