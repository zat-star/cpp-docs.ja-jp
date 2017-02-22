---
title: "ActiveX コントロール コンテナー : ActiveX コントロールとメンバー変数の関連付け | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール コンテナー [C++], アクセス (ActiveX コントロールに)"
  - "ActiveX コントロール コンテナー [C++], ActiveX コントロール (メンバー変数)"
  - "ActiveX コントロール [C++], アクセス"
  - "ActiveX コントロール [C++], メンバー変数 (プロジェクトの)"
  - "接続 (ActiveX コントロールとコンテナー メンバー変数を)"
  - "メンバー変数 [C++], ActiveX コントロール (プロジェクトの)"
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ActiveX コントロール コンテナー : ActiveX コントロールとメンバー変数の関連付け
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロール コンテナー アプリケーション内から ActiveX コントロールにアクセスする最も簡単な方法は、コントロールを含むダイアログ クラスのメンバー変数と ActiveX コントロールを関連付けます。  
  
> [!NOTE]
>  これは内部アクセスする唯一の方法は、コンテナー クラスから埋め込みコントロールではありませんが、ここではこれで十分です。  
  
### ダイアログ クラスにメンバー変数を追加できます。  
  
1.  クラス ビューから、ショートカット メニューを開き、メイン ダイアログ クラスを右クリックします。  たとえば、`CContainerDlg` のようにします。  
  
2.  このコマンドをショートカット メニューから、**追加** と **\[変数の追加\]** をクリックします。  
  
3.  メンバー変数の追加ウィザードで、**コントロール変数\(O\)**をクリックします。  
  
4.  **コントロール ID** のリスト ボックスで、埋め込まれたな ActiveX コントロールのコントロール ID を選択します。  たとえば、`IDC_CIRCCTRL1` のようにします。  
  
5.  **変数名** ボックスに名前を入力します。  
  
     たとえば、`m_circctl` のようにします。  
  
6.  選択を受け入れ、メンバー変数の追加ウィザードを終了するに **完了** をクリックします。  
  
## 参照  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)