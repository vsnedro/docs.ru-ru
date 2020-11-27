---
title: Сбои при проверке безопасности и проверке подлинности
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 3bcc6111f322a3bd8169567e8f436871eb19f879
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253054"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="48e20-102">Сбои при проверке безопасности и проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="48e20-102">Security Validation and Authentication Failures</span></span>

<span data-ttu-id="48e20-103">Имя счетчика: Security Validation and Authentication Failures</span><span class="sxs-lookup"><span data-stu-id="48e20-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="48e20-104">Описание</span><span class="sxs-lookup"><span data-stu-id="48e20-104">Description</span></span>  

 <span data-ttu-id="48e20-105">Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="48e20-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="48e20-106">К таким проблемам относятся следующие.</span><span class="sxs-lookup"><span data-stu-id="48e20-106">Such problems include:</span></span>  
  
- <span data-ttu-id="48e20-107">Невозможно прочесть в этом сообщении маркер клиента.</span><span class="sxs-lookup"><span data-stu-id="48e20-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="48e20-108">Маркер клиента не прошел проверку подлинности (например, неправильный пароль).</span><span class="sxs-lookup"><span data-stu-id="48e20-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="48e20-109">Сбой при проверке подписи (например, сообщение было искажено).</span><span class="sxs-lookup"><span data-stu-id="48e20-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="48e20-110">Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="48e20-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="48e20-111">Произошел сбой при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="48e20-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="48e20-112">В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует отметка времени или зашифрованный блок данных).</span><span class="sxs-lookup"><span data-stu-id="48e20-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="48e20-113">Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="48e20-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
