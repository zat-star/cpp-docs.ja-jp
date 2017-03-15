---
title: "DLL のエクスポート関数のエントリ ポイント | Microsoft Docs"
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
  - "エクスポート (DLL を), 関数"
  - "MFC, 管理 (状態データを)"
  - "状態管理, エクスポートされた DLL"
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# DLL のエクスポート関数のエントリ ポイント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL のエクスポート関数の場合は、DLL モジュールから呼び出し元のアプリケーションの DLL に切り替えると、適切なグローバル状態を維持するために [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) マクロを使用します。  
  
 呼び出されたときに、このマクロは関数のコンテナー スコープ内の残りの効果的なモジュール状態として `pModuleState`モジュールの `AFX_MODULE_STATE` を含む構造体のグローバル データへのポインターを設定します。  マクロを含むスコープを離れた上で前の効果的なモジュール状態が自動的に復元されます。  
  
 このスイッチは、スタックの **AFX\_MODULE\_STATE** クラスのインスタンスを構築することによって実現されます。  コンストラクターでは、このクラスは、現在のモジュール状態とストアにポインターをメンバー変数の名前を抽出し、新しい効果的なモジュール状態として `pModuleState` を設定します。  デストラクターでは、このクラスは、効果的なモジュール状態としてメンバー変数に格納されているポインターを復元します。  
  
 エクスポート関数がある場合、DLL ダイアログ ボックスを起動する 1 個などの関数の先頭に次のコードを追加する必要があります:  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/CPP/exported-dll-function-entry-points_1.cpp)]  
  
 これは、現在のスコープを閉じるまでの [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md) から返される状態を使用して、現在のモジュール状態を交換します。  
  
 DLL のリソースに問題が `AFX_MANAGE_STATE` マクロが使用されていない場合に発生します。  既定で、MFC はリソース テンプレートを読み込むメイン アプリケーションのリソース ハンドルを使用します。  このテンプレートは、DLL に実際に格納されます。  根本原因は、MFC のモジュール状態情報を `AFX_MANAGE_STATE` マクロで切替えられなかったことです。  リソース ハンドルは、MFC のモジュール状態を復元します。  モジュール状態の切り替えと、誤ったリソース ハンドルを使用します。  
  
 `AFX_MANAGE_STATE` は DLL 内の関数に入力する必要はありません。  たとえば、`InitInstance` は `AFX_MANAGE_STATE` せずにアプリケーションの MFC コードで MFC が `InitInstance` の前に自動的にモジュール状態にし、`InitInstance` が戻った後に切り替えるように呼び出すことができます。  これはすべてのメッセージ ハンドラーの場合も同様です。  レギュラー DLL にメッセージをルーティングする前に自動的にモジュール状態を切り替える特別なマスターのウィンドウ プロシージャがあります。  
  
## 参照  
 [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)