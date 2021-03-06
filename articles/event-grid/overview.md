---
title: Azure Event Grid の概要
description: Azure Event Grid とその概念について説明します。
services: event-grid
author: banisadr
manager: timlt
ms.service: event-grid
ms.topic: overview
ms.date: 08/17/2018
ms.author: babanisa
ms.openlocfilehash: 90e8d6a3ef093046c5ee6324f6e6590e59124da7
ms.sourcegitcommit: f057c10ae4f26a768e97f2cb3f3faca9ed23ff1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2018
ms.locfileid: "42022417"
---
# <a name="an-introduction-to-azure-event-grid"></a>Azure Event Grid の概要

Azure Event Grid では、イベント ベースのアーキテクチャを備えたアプリケーションを簡単に作成することができます。 最初にサブスクライブ対象の Azure リソースを選択して、イベントの送信先となるイベント ハンドラーまたは Webhook エンドポイントを指定します。 Event Grid には、Storage Blob やリソース グループなどの Azure サービスから送信されるイベントに対するサポートが組み込まれています。 さらに Event Grid では、カスタム トピックを使用した独自のイベントもサポートされます。 

フィルターを使用することで、特定のイベントをさまざまなエンドポイントにルーティングしたり、複数のエンドポイントにマルチキャストしたり、イベントを確実に配信したりできます。

現在、Azure Event Grid はすべてのパブリック リージョンで使用できます。 まだ、Azure Germany、Azure China、Azure Government クラウドでは使用できません。

この記事では、Azure Event Grid の概要を示します。 Event Grid の使用をすぐに開始するには、「[Azure Event Grid を使ったカスタム イベントの作成とルーティング](custom-event-quickstart.md)」を参照してください。 

![Event Grid 機能モデル](./media/overview/functional-model.png)

注意: この図は、Event Grid によってソースとハンドラーが接続されるようすを示すもので、サポートされる統合の包括的な一覧ではありません。

## <a name="event-sources"></a>イベント ソース

各ソースの機能の完全な詳細のほか、関連記事については、[イベント ソース](event-sources.md)に関する記事を参照してください。 現在、次の Azure サービスは Event Grid へのイベントの送信をサポートしています。

* Azure サブスクリプション (管理操作)
* Container Registry
* カスタム トピック
* Event Hubs
* IoT Hub
* Media Services
* リソース グループ (管理操作)
* Service Bus
* ストレージ BLOB
* ストレージ汎用 v2 (GPv2)

## <a name="event-handlers"></a>イベント ハンドラー

各ハンドラーの機能の完全な詳細のほか、関連記事については、[イベント ハンドラー](event-handlers.md)に関する記事を参照してください。 現在、次の Azure サービスは Event Grid からのイベントの処理をサポートしています。 

* Azure Automation
* Azure Functions
* Event Hubs
* ハイブリッド接続と
* Logic Apps
* Microsoft Flow
* Queue Storage
* WebHook

## <a name="concepts"></a>概念

Azure Event Grid には、作業開始にあたり理解する必要がある、5 つの概念があります。

* **イベント** - 発生内容
* **イベント ソース** - イベントの発生元
* **トピック** - 発行元がイベントを送信するエンドポイント
* **イベント サブスクリプション** - イベントを (時には複数のハンドラーに) ルーティングするエンドポイントまたは組み込みメカニズム サブスクリプションは、受信イベントをインテリジェントにフィルター処理するために、ハンドラーによっても使用されます。
* **イベント ハンドラー** - イベントに反応するアプリまたはサービス

これらの概念の詳細については、「[Azure Event Grid の概念](concepts.md)」を参照してください。

## <a name="capabilities"></a>機能

Azure Event Grid の主要な特長を次に示します。

* **簡単** - Azure リソースから任意のイベント ハンドラーまたはエンドポイントまで、イベントにカーソルを合わせてクリックするだけで利用できます。
* **高度なフィルター処理** - イベントの種類またはイベント発行パスに基づいてフィルター処理することで、イベント ハンドラーが関連するイベントのみを受け取るようにできます。
* **ファンアウト** - 複数のエンドポイントを同じイベントにサブスクライブし、必要な数の場所にイベントのコピーを送信できます。
* **信頼性** - 指数バックオフによる 24 時間の再試行を活用して、確実にイベントが配信されるようにします。
* **イベントごとの支払** - Event Grid の使用量に対して料金を支払います。
* **高スループット** - 1 秒あたり数百万イベントをサポートして、Event Grid での大量ワークロードを作成できます。
* **組み込みイベント** - リソース定義の組み込みイベントにより、迅速に開始および実行できます。
* **カスタム イベント** - Event Grid ルートとフィルター処理を使用して、アプリで信頼性の高いカスタム イベント配信を実現します。

Event Grid、Event Hubs、および Service Bus の比較については、「[Choose between Azure services that deliver messages (メッセージを配信する Azure サービスの選択)](compare-messaging-services.md)」を参照してください。

## <a name="what-can-i-do-with-event-grid"></a>Event Grid でできること

Azure Event Grid は、サーバーレス、操作の自動化、および統合作業を大幅に向上する複数の機能を提供します。 

### <a name="serverless-application-architectures"></a>サーバーレス アプリケーション アーキテクチャ

![サーバーレス アプリケーション](./media/overview/serverless_web_app.png)

Event Grid はデータ ソースとイベント ハンドラーを接続します。 たとえば、Event Grid を使用すると、Blob Storage コンテナーに新しい写真が追加されるたびに画像分析を実行するサーバーレス関数を即時トリガーできます。 

### <a name="ops-automation"></a>操作の自動化

![操作の自動化](./media/overview/Ops_automation.png)

Event Grid を使用すると、自動化を迅速にして、ポリシーの適用を簡素化できます。 たとえば、仮想マシンが作成された場合や SQL Database がスピンアップされた場合、Event Grid は Azure Automation に通知できます。 これらのイベントを使用して、サービス構成が準拠していることの自動確認、操作ツールへのメタデータの配置、仮想マシンのタグ付け、作業項目を登録などを実行できます。

### <a name="application-integration"></a>アプリケーションの統合

![アプリケーションの統合](./media/overview/app_integration.png)

Event Grid はお客様のアプリを他のサービスにつなげます。 たとえば、お客様のアプリのイベント データを Event Grid に送信するカスタム トピックを作成すると、Event Grid の信頼性の高い配信、高度なルーティング、Azure との直接統合を利用できます。 また、Event Grid を Logic Apps と共に使用して、コードを作成することなく、場所を問わずにデータを処理することもできます。 

## <a name="how-much-does-event-grid-cost"></a>Event Grid のコスト

Azure Event Grid では、イベントごとに課金される価格モデルを使用しているため、使用した分だけお支払いいただきます。 毎月の最初の 100,000 操作は無料です。 操作は、イベント イングレス、サブスクリプション配信の試行、管理呼び出し、サブジェクト サフィックスによるフィルター処理と定義されます。 詳細については、[価格ページ](https://azure.microsoft.com/pricing/details/event-grid/)を参照してください。

## <a name="next-steps"></a>次の手順

* [Storage Blob のイベントをルーティングする](../storage/blobs/storage-blob-event-quickstart.md?toc=%2fazure%2fevent-grid%2ftoc.json)  
  Event Grid を使用して Storage Blob のイベントに応答します。
* [カスタム イベントを作成してサブスクライブする](custom-event-quickstart.md)  
  Azure Event Grid のクイックスタートを使用して、任意のエンドポイントへの独自のカスタム イベントの送信をすぐに始めることができます。
* [Logic Apps をイベント ハンドラーとして使用する](monitor-virtual-machine-changes-event-grid-logic-app.md)  
  Event Grid によってプッシュされるイベントに対応するアプリを Logic Apps を使用して作成するためのチュートリアルです。
* [ビッグ データをデータ ウェアハウスにストリーミングする](event-grid-event-hubs-integration.md)  
  Azure Functions を使用して Event Hubs から SQL Data Warehouse にデータをストリーミングするチュートリアルです。
* [Event Grid REST API リファレンス](/rest/api/eventgrid)  
  Azure Event Grid についての詳細な技術情報と、イベント サブスクリプション、ルーティング、フィルター処理を管理するためのリファレンスを提供します。