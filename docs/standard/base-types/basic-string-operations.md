---
title: Базовые операции со строками в .NET
description: Дополнительные сведения о базовых операциях, которые можно выполнять со строками.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 4ab087435880c6a5357bc161899cd585982622f4
ms.sourcegitcommit: ffd4d5e824db6c5f0c3521c0e802fd9e8f0edcbe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "93342609"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="a9541-103">Базовые операции со строками в .NET</span><span class="sxs-lookup"><span data-stu-id="a9541-103">Basic string operations in .NET</span></span>

<span data-ttu-id="a9541-104">Многие приложения взаимодействуют с пользователями, формируя сообщения, основанные на данных, введенных пользователями.</span><span class="sxs-lookup"><span data-stu-id="a9541-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="a9541-105">Например, веб-сайты зачастую приветствуют вошедших пользователей персональным приветствием, содержащим его имя.</span><span class="sxs-lookup"><span data-stu-id="a9541-105">For example, it is not uncommon for websites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span>

<span data-ttu-id="a9541-106">Ряд методов в классах <xref:System.String?displayProperty=nameWithType> и <xref:System.Text.StringBuilder?displayProperty=nameWithType> позволяют динамически создавать настраиваемые строки для отображения в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="a9541-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="a9541-107">С помощью этих методов также можно выполнять базовые операции со строками — например, создание новых строк из байтовых массивов, сравнение значений строк и изменение существующих строк.</span><span class="sxs-lookup"><span data-stu-id="a9541-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a9541-108">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a9541-108">Related sections</span></span>

<span data-ttu-id="a9541-109">[Преобразование типов в .NET](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="a9541-109">[Type Conversion in .NET](type-conversion.md)</span></span>\
<span data-ttu-id="a9541-110">Описывает преобразование одних типов в другие.</span><span class="sxs-lookup"><span data-stu-id="a9541-110">Describes how to convert one type into another type.</span></span>

<span data-ttu-id="a9541-111">[Типы форматирования](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="a9541-111">[Formatting Types](formatting-types.md)</span></span>\
<span data-ttu-id="a9541-112">Описывает форматирование строк с использованием описателей формата.</span><span class="sxs-lookup"><span data-stu-id="a9541-112">Describes how to format strings using format specifiers.</span></span>
