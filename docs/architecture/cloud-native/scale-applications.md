---
title: Масштабирование облачных приложений
description: Масштабирование облачных приложений с помощью службы Azure Kubernetes и функций Azure для удовлетворения потребностей пользователей с учетом экономичного способа.
ms.date: 04/13/2020
ms.openlocfilehash: 91d925778e9dfcf8a1ec2486fe8961037409f207
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199948"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="03278-103">Масштабирование облачных приложений</span><span class="sxs-lookup"><span data-stu-id="03278-103">Scaling cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="03278-104">Одним из наиболее часто похвалу преимуществ перехода на облачную среду размещения является масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="03278-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="03278-105">Масштабируемость или возможность приложения принимать дополнительную нагрузку, не нарушая производительность каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="03278-105">Scalability, or the ability for an application to accept additional user load without compromising performance for each user.</span></span> <span data-ttu-id="03278-106">Чаще всего это достигается путем разбиения приложения на небольшие части, которые могут предоставлять все необходимые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="03278-106">It's most often achieved by breaking up an application into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="03278-107">Поставщики облачных решений обеспечивают широкие возможности масштабирования в любое время и в любой точке мира.</span><span class="sxs-lookup"><span data-stu-id="03278-107">Cloud vendors enable massive scalability anytime and anywhere in the world.</span></span>

 <span data-ttu-id="03278-108">В этой главе обсуждаются технологии, позволяющие выполнять масштабирование собственных приложений в облаке в соответствии с потребностями пользователей.</span><span class="sxs-lookup"><span data-stu-id="03278-108">In this chapter, we discuss technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="03278-109">Ниже приведены эти технологии.</span><span class="sxs-lookup"><span data-stu-id="03278-109">These technologies include:</span></span>

- <span data-ttu-id="03278-110">Контейнеры</span><span class="sxs-lookup"><span data-stu-id="03278-110">Containers</span></span>
- <span data-ttu-id="03278-111">Оркестраторы</span><span class="sxs-lookup"><span data-stu-id="03278-111">Orchestrators</span></span>
- <span data-ttu-id="03278-112">Бессерверные вычисления</span><span class="sxs-lookup"><span data-stu-id="03278-112">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="03278-113">[Назад](centralized-configuration.md)
>[Вперед](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="03278-113">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
