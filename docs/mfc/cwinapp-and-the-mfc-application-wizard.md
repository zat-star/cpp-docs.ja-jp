---
title: "CWinApp および MFC アプリケーション ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 603504025bf4069f7a56b705e50a176975dbf244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp および MFC アプリケーション ウィザード
MFC アプリケーション ウィザードでは、アプリケーション クラスから派生した宣言、スケルトン アプリケーションの作成時に[CWinApp](../mfc/reference/cwinapp-class.md)です。 MFC アプリケーション ウィザードでは、次の項目を含んでいる実装ファイルも生成します。  
  
-   アプリケーションのクラスのメッセージ マップです。  
  
-   空のクラスのコンス トラクターです。  
  
-   クラスのオブジェクトのみを宣言する変数です。  
  
-   標準的な実装、`InitInstance`メンバー関数。  
  
 アプリケーションのクラスは、プロジェクトのヘッダーとメインのソース ファイルに配置されます。 クラスと作成されるファイルの名前は、MFC アプリケーション ウィザードで指定されたプロジェクト名に基づきます。 これらのクラスのコードを表示する最も簡単な方法は、[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)です。  
  
 標準の実装および提供のメッセージ マップが多くの目的で、適切なものが、必要に応じて変更できます。 これらの実装の中で最も興味深いは、`InitInstance`メンバー関数。 通常、コードのスケルトンの実装を追加が`InitInstance`です。  
  
## <a name="see-also"></a>参照  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)   
 [オーバーライド可能な CWinApp のメンバー関数します。](../mfc/overridable-cwinapp-member-functions.md)   
 [CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)

