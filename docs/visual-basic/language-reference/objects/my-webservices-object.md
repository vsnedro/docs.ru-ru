---
title: Объект My.WebServices
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 0b63b44c2cd9d55094fb83fed6c04e4de528a25c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867199"
---
# <a name="mywebservices-object"></a><span data-ttu-id="17f59-102">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="17f59-102">My.WebServices Object</span></span>

<span data-ttu-id="17f59-103">Предоставляет свойства для создания и доступа к одному экземпляру каждой веб-службы XML, на которую ссылается текущий проект.</span><span class="sxs-lookup"><span data-stu-id="17f59-103">Provides properties for creating and accessing a single instance of each XML Web service referenced by the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17f59-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="17f59-104">Remarks</span></span>  

 <span data-ttu-id="17f59-105">Объект `My.WebServices` предоставляет экземпляр каждой веб-службы, на которую ссылается текущий проект.</span><span class="sxs-lookup"><span data-stu-id="17f59-105">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="17f59-106">Каждый экземпляр создается по запросу.</span><span class="sxs-lookup"><span data-stu-id="17f59-106">Each instance is instantiated on demand.</span></span> <span data-ttu-id="17f59-107">Доступ к этим веб-службам можно получить через свойства объекта `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="17f59-107">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="17f59-108">Имя свойства совпадает с именем веб-службы, к которой обращается свойство.</span><span class="sxs-lookup"><span data-stu-id="17f59-108">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="17f59-109">Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>, является веб-службой.</span><span class="sxs-lookup"><span data-stu-id="17f59-109">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span> <span data-ttu-id="17f59-110">Сведения о добавлении веб-служб в проект см. в разделе [доступ к веб-службам приложений](../../developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="17f59-110">For information about adding Web services to a project, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="17f59-111">`My.WebServices`Объект предоставляет только веб-службы, связанные с текущим проектом.</span><span class="sxs-lookup"><span data-stu-id="17f59-111">The `My.WebServices` object exposes only the Web services associated with the current project.</span></span> <span data-ttu-id="17f59-112">Он не предоставляет доступ к веб-службам, объявленным в упоминаемых в них библиотеках DLL.</span><span class="sxs-lookup"><span data-stu-id="17f59-112">It does not provide access to Web services declared in referenced DLLs.</span></span> <span data-ttu-id="17f59-113">Для доступа к веб-службе, предоставляемой библиотекой DLL, необходимо использовать полное имя веб-службы в формате *dllname*. *WebServiceName*.</span><span class="sxs-lookup"><span data-stu-id="17f59-113">To access a Web service that a DLL provides, you must use the qualified name of the Web service, in the form *DllName*.*WebServiceName*.</span></span> <span data-ttu-id="17f59-114">Дополнительные сведения см. в разделе [доступ к веб-службам приложений](../../developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="17f59-114">For more information, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="17f59-115">Объект и его свойства недоступны для веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="17f59-115">The object and its properties are not available for Web applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="17f59-116">Свойства</span><span class="sxs-lookup"><span data-stu-id="17f59-116">Properties</span></span>  

 <span data-ttu-id="17f59-117">Каждое свойство `My.WebServices` объекта предоставляет доступ к экземпляру веб-службы, на которую ссылается текущий проект.</span><span class="sxs-lookup"><span data-stu-id="17f59-117">Each property of the `My.WebServices` object provides access to an instance of a Web service referenced by the current project.</span></span> <span data-ttu-id="17f59-118">Имя свойства совпадает с именем веб-службы, к которой обращается свойство, а тип свойства совпадает с типом веб-службы.</span><span class="sxs-lookup"><span data-stu-id="17f59-118">The name of the property is the same as the name of the Web service that the property accesses, and the property type is the same as the Web service's type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17f59-119">При конфликте имен имя свойства для доступа к веб-службе — *RootNamespace*_*Namespace* \_ *ServiceName*.</span><span class="sxs-lookup"><span data-stu-id="17f59-119">If there is a name collision, the property name for accessing a Web service is *RootNamespace*_*Namespace*\_*ServiceName*.</span></span> <span data-ttu-id="17f59-120">Например, рассмотрим две веб-службы с именем `Service1` .</span><span class="sxs-lookup"><span data-stu-id="17f59-120">For example, consider two Web services named `Service1`.</span></span> <span data-ttu-id="17f59-121">Если одна из этих служб находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1` , доступ к этой службе будет осуществляться с помощью `My.WebServices.WindowsApplication1_Namespace1_Service1` .</span><span class="sxs-lookup"><span data-stu-id="17f59-121">If one of these services is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that service by using `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span></span>  
  
 <span data-ttu-id="17f59-122">При первом доступе к одному из `My.WebServices` свойств объекта он создает новый экземпляр веб-службы и сохраняет его.</span><span class="sxs-lookup"><span data-stu-id="17f59-122">When you first access one of the `My.WebServices` object's properties, it creates a new instance of the Web service and stores it.</span></span> <span data-ttu-id="17f59-123">Последующие обращения к этому свойству возвращают этот экземпляр веб-службы.</span><span class="sxs-lookup"><span data-stu-id="17f59-123">Subsequent accesses of that property return that instance of the Web service.</span></span>  
  
 <span data-ttu-id="17f59-124">Вы можете удалить веб-службу, назначив ей `Nothing` свойство для этой веб-службы.</span><span class="sxs-lookup"><span data-stu-id="17f59-124">You can dispose of a Web service by assigning `Nothing` to the property for that Web service.</span></span> <span data-ttu-id="17f59-125">Метод задания свойства присваивает `Nothing` хранимому значению.</span><span class="sxs-lookup"><span data-stu-id="17f59-125">The property setter assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="17f59-126">Если присвоить значение, отличное от `Nothing` свойства, метод задания выдаст <xref:System.ArgumentException> исключение.</span><span class="sxs-lookup"><span data-stu-id="17f59-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="17f59-127">Можно проверить `My.WebServices` , сохраняет ли свойство объекта экземпляр веб-службы с помощью `Is` `IsNot` оператора или.</span><span class="sxs-lookup"><span data-stu-id="17f59-127">You can test whether a property of the `My.WebServices` object stores an instance of the Web service by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="17f59-128">С помощью этих операторов можно проверить, имеет ли свойство значение `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="17f59-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17f59-129">Как правило, `Is` `IsNot` оператор или должен считывать значение свойства для выполнения сравнения.</span><span class="sxs-lookup"><span data-stu-id="17f59-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="17f59-130">Однако если текущее свойство хранится `Nothing` , свойство создает новый экземпляр веб-службы, а затем возвращает этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="17f59-130">However, if the property currently stores `Nothing`, the property creates a new instance of the Web service and then returns that instance.</span></span> <span data-ttu-id="17f59-131">Однако компилятор Visual Basic обрабатывает свойства `My.WebServices` объекта особым образом и позволяет `Is` `IsNot` оператору или проверить состояние свойства без изменения его значения.</span><span class="sxs-lookup"><span data-stu-id="17f59-131">However, the Visual Basic compiler treats the properties of the `My.WebServices` object specially, and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17f59-132">Пример</span><span class="sxs-lookup"><span data-stu-id="17f59-132">Example</span></span>  

 <span data-ttu-id="17f59-133">В этом примере вызывается `FahrenheitToCelsius` метод `TemperatureConverter` веб-службы XML и возвращается результат.</span><span class="sxs-lookup"><span data-stu-id="17f59-133">This example calls the `FahrenheitToCelsius` method of the `TemperatureConverter` XML Web service, and returns the result.</span></span>  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 <span data-ttu-id="17f59-134">Чтобы этот пример работал, проект должен ссылаться на веб-службу с именем `Converter` , и эта веб-служба должна предоставлять `ConvertTemperature` метод.</span><span class="sxs-lookup"><span data-stu-id="17f59-134">For this example to work, your project must reference a Web service named `Converter`, and that Web service must expose the `ConvertTemperature` method.</span></span> <span data-ttu-id="17f59-135">Дополнительные сведения см. в разделе [доступ к веб-службам приложений](../../developing-apps/programming/accessing-application-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="17f59-135">For more information, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="17f59-136">Этот код не работает в проекте веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="17f59-136">This code does not work in a Web application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17f59-137">Требования</span><span class="sxs-lookup"><span data-stu-id="17f59-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="17f59-138">Доступность по типу проекта</span><span class="sxs-lookup"><span data-stu-id="17f59-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="17f59-139">Тип проекта</span><span class="sxs-lookup"><span data-stu-id="17f59-139">Project type</span></span>|<span data-ttu-id="17f59-140">Доступно</span><span class="sxs-lookup"><span data-stu-id="17f59-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="17f59-141">Приложение Windows</span><span class="sxs-lookup"><span data-stu-id="17f59-141">Windows Application</span></span>|<span data-ttu-id="17f59-142">**Да**</span><span class="sxs-lookup"><span data-stu-id="17f59-142">**Yes**</span></span>|  
|<span data-ttu-id="17f59-143">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="17f59-143">Class Library</span></span>|<span data-ttu-id="17f59-144">**Да**</span><span class="sxs-lookup"><span data-stu-id="17f59-144">**Yes**</span></span>|  
|<span data-ttu-id="17f59-145">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="17f59-145">Console Application</span></span>|<span data-ttu-id="17f59-146">**Да**</span><span class="sxs-lookup"><span data-stu-id="17f59-146">**Yes**</span></span>|  
|<span data-ttu-id="17f59-147">Библиотека элементов управления Windows</span><span class="sxs-lookup"><span data-stu-id="17f59-147">Windows Control Library</span></span>|<span data-ttu-id="17f59-148">**Да**</span><span class="sxs-lookup"><span data-stu-id="17f59-148">**Yes**</span></span>|  
|<span data-ttu-id="17f59-149">Библиотека веб-элементов управления</span><span class="sxs-lookup"><span data-stu-id="17f59-149">Web Control Library</span></span>|<span data-ttu-id="17f59-150">**Да**</span><span class="sxs-lookup"><span data-stu-id="17f59-150">**Yes**</span></span>|  
|<span data-ttu-id="17f59-151">Службы Windows</span><span class="sxs-lookup"><span data-stu-id="17f59-151">Windows Service</span></span>|<span data-ttu-id="17f59-152">**Да**</span><span class="sxs-lookup"><span data-stu-id="17f59-152">**Yes**</span></span>|  
|<span data-ttu-id="17f59-153">Веб-сайт</span><span class="sxs-lookup"><span data-stu-id="17f59-153">Web Site</span></span>|<span data-ttu-id="17f59-154">Нет</span><span class="sxs-lookup"><span data-stu-id="17f59-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17f59-155">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="17f59-155">See also</span></span>

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [<span data-ttu-id="17f59-156">Доступ к веб-службам приложения</span><span class="sxs-lookup"><span data-stu-id="17f59-156">Accessing Application Web Services</span></span>](../../developing-apps/programming/accessing-application-web-services.md)
