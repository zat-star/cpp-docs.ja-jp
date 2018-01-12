---
title: "ATL サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CServiceModule
dev_langs: C++
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d13eebbe96ba57c82e3bf1c360b0cb471a6bd975
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-services"></a>ATL サービス
サービスで実行されるように、ATL COM オブジェクトを作成するには、ATL プロジェクト ウィザードでのサーバー オプションの一覧からサービス (EXE) を選択します。 ウィザードはから派生するクラスを作成し、`CAtlServiceModuleT`してサービスを実装します。  
  
 ATL COM オブジェクトをサービスとしてビルドするとき、のみ、ローカル サーバーとして登録され、コントロール パネルの サービスの一覧には表示されません。 これは、サービスとしてよりもローカル サーバーとサービスをデバッグしやすくなっているためです。 サービスとしてインストールするには、コマンド プロンプトで、次を実行します。  
  
 `YourEXE` `.exe /Service`  
  
 これをアンインストールするには次の手順を実行します。  
  
 `YourEXE` `.exe /UnregServer`  
  
 このセクションの最初の 4 つのトピックの実行中に発生するアクションを説明する`CAtlServiceModuleT`メンバー関数。 これらのトピックは、関数が呼び出されて通常と同じ順序で表示されます。 これらのトピックの理解を深めるためには参照として ATL プロジェクト ウィザードで生成されたソース コードを使用することをお勧めします。 これらの最初の 4 つのトピックは次のとおりです。  
  

-   [CAtlServiceModuleT::Start 関数](../atl/reference/catlservicemodulet-class.md#start)  
  
-   [CAtlServiceModuleT::ServiceMain 関数](../atl/reference/catlservicemodulet-class.md#servicemain)  
  
-   [主要な関数](../atl/reference/catlservicemodulet-class.md#run)  
  
-   [CAtlServiceModuleT::Handler 関数](../atl/reference/catlservicemodulet-class.md#handler)  
  
 最後の 3 つのトピックでは、サービスの開発に関連する概念について説明します。  
  
-   [レジストリ エントリ](../atl/registry-entries.md)ATL サービス  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [デバッグのヒント](../atl/debugging-tips.md)ATL サービス  
  
## <a name="see-also"></a>参照  
 [概念](../atl/active-template-library-atl-concepts.md)

