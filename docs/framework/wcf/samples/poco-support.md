---
title: Поддержка POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: d416f37e0add99fbe3d60982fd2298748ff78556
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259971"
---
# <a name="poco-support"></a><span data-ttu-id="04ff4-102">Поддержка POCO</span><span class="sxs-lookup"><span data-stu-id="04ff4-102">POCO Support</span></span>

<span data-ttu-id="04ff4-103">В этом образце демонстрируется поддержка сериализации непомеченных типов, т. е. типов, к которым не применены атрибуты сериализации. Иногда такие типы называют типами POCO (Plain Old CLR Object).</span><span class="sxs-lookup"><span data-stu-id="04ff4-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="04ff4-104">Объект <xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных для всех открытых непомеченных типов, имеющих конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="04ff4-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a parameterless constructor.</span></span> <span data-ttu-id="04ff4-105">Контракты данных позволяют передавать структурированные данные в службы и из служб.</span><span class="sxs-lookup"><span data-stu-id="04ff4-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="04ff4-106">Дополнительные сведения о непомеченных типах см. в разделе [сериализуемые типы](../feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="04ff4-106">For more information about unmarked types, see [Serializable Types](../feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="04ff4-107">Этот образец основан на [Начало работы](getting-started-sample.md), но использует комплексные числа, а не простые числовые типы.</span><span class="sxs-lookup"><span data-stu-id="04ff4-107">This sample is based on the [Getting Started](getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="04ff4-108">Он также похож на пример [базового контракта данных](basic-data-contract.md) , за исключением того, <xref:System.Runtime.Serialization.DataContractAttribute> что <xref:System.Runtime.Serialization.DataMemberAttribute> атрибуты и не используются.</span><span class="sxs-lookup"><span data-stu-id="04ff4-108">It is also similar to the [Basic Data Contract](basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="04ff4-109">Клиентом является консольное приложение (EXE), а служба размещается в службах Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="04ff4-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04ff4-110">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="04ff4-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="04ff4-111">Класс `ComplexNumber` используется классом `ServiceContract`.</span><span class="sxs-lookup"><span data-stu-id="04ff4-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="04ff4-112">У типа `ComplexNumber` нет атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="04ff4-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="04ff4-113">По умолчанию все открытые свойства и поля сериализуются.</span><span class="sxs-lookup"><span data-stu-id="04ff4-113">By default, all public properties and fields are serialized.</span></span>  
  
```csharp
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="04ff4-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="04ff4-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="04ff4-115">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="04ff4-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="04ff4-116">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="04ff4-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="04ff4-117">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="04ff4-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="04ff4-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="04ff4-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="04ff4-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="04ff4-119">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="04ff4-120">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="04ff4-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="04ff4-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="04ff4-121">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="04ff4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="04ff4-122">See also</span></span>

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [<span data-ttu-id="04ff4-123">Сериализуемые типы</span><span class="sxs-lookup"><span data-stu-id="04ff4-123">Serializable Types</span></span>](../feature-details/serializable-types.md)
