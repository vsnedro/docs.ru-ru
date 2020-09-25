---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c4e5cbac24e2c72791c2f5c0faed0703363c99e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201425"
---
# \<transactionFlow>

<span data-ttu-id="fd228-101">Задает поддержку потока транзакций для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="fd228-101">Specifies transaction flow support for the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**  
  
## <a name="syntax"></a><span data-ttu-id="fd228-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd228-102">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd228-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fd228-103">Attributes and Elements</span></span>  

 <span data-ttu-id="fd228-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fd228-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd228-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fd228-105">Attributes</span></span>  
  
|<span data-ttu-id="fd228-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fd228-106">Attribute</span></span>|<span data-ttu-id="fd228-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fd228-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd228-108">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="fd228-108">transactionProtocol</span></span>|<span data-ttu-id="fd228-109">Задает используемый протокол транзакций.</span><span class="sxs-lookup"><span data-stu-id="fd228-109">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="fd228-110">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="fd228-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fd228-111">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="fd228-111">-   OleTransactions</span></span><br /><span data-ttu-id="fd228-112">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="fd228-112">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="fd228-113">Значение по умолчанию - OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="fd228-113">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="fd228-114">Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="fd228-114">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd228-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fd228-115">Child Elements</span></span>  

 <span data-ttu-id="fd228-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fd228-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd228-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fd228-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fd228-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="fd228-118">Element</span></span>|<span data-ttu-id="fd228-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fd228-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="fd228-120">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="fd228-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd228-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="fd228-121">Remarks</span></span>  

 <span data-ttu-id="fd228-122">Этот элемент позволяет включить или отключить входящий поток транзакций в параметрах привязки конечной точки, а также задать необходимый формат протокола для входящих транзакций.</span><span class="sxs-lookup"><span data-stu-id="fd228-122">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="fd228-123">Дополнительные сведения об использовании этого элемента конфигурации см. в разделе [Конфигурация транзакций ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) и [Включение потока транзакций](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="fd228-123">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="fd228-124">При использовании протокола `OleTransactions` для реализации потока транзакций от одной конечной точки к другой время ожидания транзакции может быть потеряно, если целевая конечная точка попытается запустить поток снова, используя любой протокол, отличный от `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="fd228-124">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="fd228-125">Это может привести к тому, что время ожидания для всех узлов, находящихся ниже перехода OleTransactions, окажется больше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="fd228-125">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd228-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fd228-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fd228-127">Конфигурация транзакции ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fd228-127">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="fd228-128">Включение потока транзакций</span><span class="sxs-lookup"><span data-stu-id="fd228-128">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="fd228-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="fd228-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fd228-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="fd228-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fd228-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="fd228-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
