---
title: "ATL サービス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL サービス"
  - "COM オブジェクト, ATL"
  - "CServiceModule クラス"
  - "サービス, ATL"
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL サービス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

サービスで実行できるように、ATL COM を、ATL プロジェクト ウィザードのサーバーの選択肢のリストから単純にサービスを選択します \(EXE\) オブジェクト参照を作成するには、  ウィザードは、サービスを実行するに `CAtlServiceModuleT` から派生クラスを作成します。  
  
 ATL COM オブジェクトがサービスとしてビルドすると、ローカル サーバーとしてのみ登録され、コントロール パネルのサービスの一覧に表示されません。  これは、サービスとしてでローカル サーバーとしてサービスのデバッグを簡単にするためです。  サービスとしてインストールするには、コマンド プロンプトで次を実行します:  
  
 `YourEXE` `.exe /Service`  
  
 拡張機能をアンインストールするには、次を実行します:  
  
 `YourEXE` `.exe /UnregServer`  
  
 このセクションの最初の 4 種類のトピックでは `CAtlServiceModuleT` のメンバー関数の実行中に発生するアクションについて説明します。  これらのトピックでは、通常、関数が呼び出されると同じ順序で表示されます。  これらのトピックの理解を深めるするには、参照として ATL プロジェクト ウィザードが生成するソース・コードを使用することをお勧めします。  この最初の 4 種類のトピックでは、次のとおりです:  
  
-   [CAtlServiceModuleT::Start 関数](../atl/catlservicemodulet-start-function.md)  
  
-   [CAtlServiceModuleT::ServiceMain 関数](../atl/catlservicemodulet-servicemain-function.md)  
  
-   [CAtlServiceModuleT::Run 関数](../atl/catlservicemodulet-run-function.md)  
  
-   [CAtlServiceModuleT::Handler 関数](../Topic/CAtlServiceModuleT::Handler%20Function.md)  
  
 最後の 3 回のトピックでは、サービスの開発に関連する概念について説明します:  
  
-   ATL サービスの[レジストリ エントリ](../atl/registry-entries.md)  
  
-   [DCOMCNFG](../Topic/DCOMCNFG.md)  
  
-   ATL サービスの[デバッグのヒント](../atl/debugging-tips.md)  
  
## 参照  
 [概念](../atl/active-template-library-atl-concepts.md)