---
title: REST API を使用して音声を認識する
description: Cognitive Services Speech サービスの Speech to Text API の使用方法について説明します。
titleSuffix: Microsoft Cognitive Services
services: cognitive-services
author: v-jerkin
ms.service: cognitive-services
ms.component: speech-service
ms.topic: article
ms.date: 07/16/2018
ms.author: v-jerkin
ms.openlocfilehash: eafec2dd262098bc4b7e485293818b79debe3d27
ms.sourcegitcommit: 2ad510772e28f5eddd15ba265746c368356244ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43126848"
---
# <a name="recognize-speech-by-using-the-rest-api"></a>REST API を使用して音声を認識する

[!INCLUDE [Selector](../../../includes/cognitive-services-speech-service-how-to-recognize-speech-selector.md)]

REST API を使用すると、HTTP POST 要求を使用して短い発話を認識できます。

この REST API は、[SDK](speech-sdk.md) でサポートされている言語を使用していない場合に、音声を認識する最も簡単な方法です。 サービス エンドポイントに HTTP POST 要求を行い、要求の本文で発話全体を渡します。 認識されたテキストが含まれる応答を受信します。

> [!NOTE]
> REST API を使用する場合、発話は 15 秒以下に制限されます。
> 長い発話の認識については、[Speech SDK](how-to-recognize-speech-csharp.md) に関するページをご覧ください。

**Speech to Text** REST API の詳細については、[REST API](rest-apis.md#speech-to-text) に関する記事をご覧ください。 API の動作を確認するには、GitHub から [REST API のサンプル](https://github.com/Azure-Samples/SpeechToText-REST)をダウンロードします。

## <a name="next-steps"></a>次の手順

- [REST API の概要](rest-apis.md)を確認する。
