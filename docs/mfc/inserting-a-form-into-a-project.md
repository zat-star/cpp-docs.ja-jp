---
title: "プロジェクトへのフォームの挿入 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "フォーム, 追加 (プロジェクトに)"
  - "[新しい項目を挿入] ダイアログ ボックス"
  - "挿入 (フォームを)"
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロジェクトへのフォームの挿入
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フォームはコントロールに便利なコンテナーを提供します。  アプリケーションに限り、アプリケーションがサポートする MFC ライブラリ簡単に MFC ベースのフォームを挿入できます。  
  
### フォームをプロジェクトに追加するには  
  
1.  クラス ビューから、フォームを追加するグループを選択し、マウスの右ボタンをクリックして、プロジェクトを。  
  
2.  ショートカット メニューの \[追加\] をクリックし、さらに \[クラスの追加\] をクリックします。  
  
     **新しいフォーム** コマンドが使用できない場合、プロジェクトは Active Template Library \(ATL\) に基づいている場合があります。  最初にプロジェクトを作成するときの ATL プロジェクトにフォームを追加するには、[特定の設定を指定します。](../Topic/Application%20Settings,%20ATL%20Project%20Wizard.md) です。  
  
3.  **MFC\(M\)** フォルダーで、クリック **MFC クラス**。  
  
4.  MFC クラス ウィザードを使用して、新しいクラスを [CFormView](../mfc/reference/cformview-class.md)から派生させます。  
  
 Visual C\+\+ では、ダイアログ エディター内で開くアプリケーションにコントロールを追加し、全体的な設計を操作するためのフォームを追加します。  
  
 次の追加の手順が必要になる場合があります \(ダイアログ ベースのアプリケーションには適用できない\) 実行:  
  
1.  `OnUpdate` のメンバー関数をオーバーライドします。  
  
2.  ビューからドキュメントにデータを移動するためのメンバー関数を実装してください。  
  
3.  `OnPrint` メンバー関数を作成します。  
  
## 参照  
 [フォーム ビュー](../Topic/Form%20Views%20\(MFC\).md)