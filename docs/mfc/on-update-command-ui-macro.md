---
title: "ON_UPDATE_COMMAND_UI マクロ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_UPDATE_COMMAND_UI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ハンドラー マクロ"
  - "ON_UPDATE_COMMAND_UI マクロ"
  - "更新ハンドラー"
  - "更新 (ユーザー インターフェイス オブジェクトを)"
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ON_UPDATE_COMMAND_UI マクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コマンドターゲット オブジェクトの更新コマンド ハンドラーへのユーザー インターフェイス オブジェクトを接続するために **\[プロパティ\]** ウィンドウを使用します。  これは `ON_UPDATE_COMMAND_UI` マクロに自動的にインターフェイス オブジェクトの ID を接続して、更新を処理するオブジェクトにハンドラーを作成します。  詳細については、" [関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md) を参照してください。  
  
 たとえば、Clear を更新するため、プログラムのすべてのコマンドがメニューを編集し、選択したクラスのメッセージ マップ エントリ、クラス宣言の `OnUpdateEditClearAll` と呼ばれるコマンド更新ハンドラーの関数宣言とクラスの実装ファイルの空の関数テンプレートを追加するには **\[プロパティ\]** ウィンドウを使用します。  関数プロトタイプの例を次に示します。:  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/CPP/on-update-command-ui-macro_1.h)]  
  
 すべてのハンドラーと同じように、関数は **afx\_msg** キーワードを示します。  すべての更新ハンドラーと同様に、1 個の引数、`CCmdUI` オブジェクトへのポインターを受け取ります。  
  
## 参照  
 [ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)