---
title: "ATL レジストラーのスクリプトを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3bda4043693d14451a2de14cbc71fbecdcdddba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts
レジストラー スクリプトは、システム レジストリへの API に基づくのではなく、データ ドリブンのアクセスを提供します。 データ ドリブンのアクセスは、レジストリ キーを追加するスクリプト内で 1 つまたは 2 つの行がかかるのでに通常より効率的です。  
  
 [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)COM サーバー用のレジストラー スクリプトを自動的に生成されます。 このスクリプトは、オブジェクトに関連付けられている .rgs ファイルで参照できます。  
  
 ATL レジストラーのスクリプト エンジンでは、実行時に、レジストラー スクリプトを処理します。 ATL は、サーバーのセットアップ中に、スクリプト エンジンを自動的に呼び出します。  
  
 この記事では、レジストラー スクリプトに関連する次のトピックについて説明します。  
  
-   [バッカス ナウア記法 (BNF) 構文を理解する](../atl/understanding-backus-nauer-form-bnf-syntax.md)  
  
-   [パース ツリーを理解する](../atl/understanding-parse-trees.md)  
  
-   [レジストリ スクリプトの例](../atl/registry-scripting-examples.md)  
  
-   [置き換え可能パラメーターの使用 (レジストラー プリプロセッサ)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
  
-   [スクリプトの呼び出し](../atl/invoking-scripts.md)  
  
## <a name="see-also"></a>参照  
 [レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)

