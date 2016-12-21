---
title: "MFC プロジェクトへの ATL サポートの追加 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.adding.atl.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, MFC プロジェクト"
  - "MFC, ATL サポート"
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC プロジェクトへの ATL サポートの追加
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC ベースのアプリケーションを既に作成した場合は、MFC に ATL サポートを追加ウィザードを実行して、ATL \(Active Template Library\) のサポートを簡単に追加できます。  
  
> [!NOTE]
>  ATL と MFC は Visual Studio の Express Edition にはサポートされていません。  
  
> [!NOTE]
>  このサポートの適用対象は、MFC の実行可能ファイルまたは DLL プロジェクトに追加された単純な COM オブジェクトだけです。  ActiveX コントロールを含むほかの COM オブジェクトを MFC プロジェクトに追加することもできますが、その場合、オブジェクトが予測どおりに動作しないことがあります。  
  
### MFC プロジェクトに ATL サポートを追加するには  
  
1.  ソリューション エクスプローラーで、ATL サポートを追加するプロジェクトを右クリックします。  
  
2.  ショートカット メニューの \[追加\] をポイントし、\[クラスの追加\] をクリックします。  
  
3.  \[MFC に ATL サポートを追加\] アイコンを選択します。  
  
    > [!NOTE]
    >  このアイコンは、**\[カテゴリ\]** ペインの \[ATL\] フォルダーにあります。  
  
4.  ATL サポートを追加するかどうかをたずねるメッセージ ボックスが表示されたら、**\[はい\]** をクリックします。  
  
 ATL サポートの追加によって生じる MFC プロジェクトのコードの変化については、「[ATL ウィザードで追加した ATL サポートの詳細](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)」を参照してください。  
  
## 参照  
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../../ide/navigating-the-class-structure-visual-cpp.md)