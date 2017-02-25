---
title: "メッセージ処理とコマンド ターゲット | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOleCommandTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ルーティング, コマンド ターゲット"
  - "コマンド ターゲット"
  - "IOleCommandTarget インターフェイス"
  - "メッセージ処理, アクティブ ドキュメント"
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# メッセージ処理とコマンド ターゲット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コマンド `IOleCommandTarget` ディスパッチ インターフェイスはやすく、拡張可能な機能をコマンドに対して、実行を定義します。  この機能は、コマンドの標準セットに完全に依存するため、オートメーション `IDispatch` ;より単純です。コマンドに対して引数がなく、型情報は複雑ではありません \(タイプ セーフはコマンド引数用に減少します。  
  
 コマンド ディスパッチ インターフェイス設計では、各コマンドは **GUID**自体で識別される「コマンド グループに属しています」。  したがって、だれでも新しいグループを定義し、Microsoft などの他の販売元も変更しなくても、そのグループ内のすべてのコマンドを定義できます。\(これは、オートメーション **dispIDs** と **dispinterface** は基本的に定義と同じ意味です。  このコマンド ルーティング機構がオートメーション ハンドルとしてコマンド ルーティングだけであり、またはプログラミング用スクリプト、大規模にですが、ここで重複があります\)。  
  
 `IOleCommandTarget` は 次のシナリオを処理します:  
  
-   オブジェクトが埋め込み先でアクティブにすると、オブジェクトのツール バーのみが通常表示され、オブジェクトのツール バーが **印刷**、**印刷 \[プレビュー\]**、**\[保存\]**、`New`、**\[ズーム\]** などのコンテナー コマンドの一部のボタンを持つ場合があります。埋め込み先編集の有効化の従来からオブジェクトが削除されます。ツール バーからこのようなボタンをお勧めしますが、少なくとも無効にします。  この方法は、そのコマンドが右側のハンドラーに有効になるようにが生じた場合にルーティングされるようにようになります\)。現在、コンテナーにこれらのコマンドをディスパッチするオブジェクトの機能はありません。  
  
-   アクティブ文書を Active ドキュメント コンテナー \(Office バインダーなど\) に埋め込まれている場合、コンテナーはアクティブ ドキュメントに含まれるコマンドにこのような **印刷**、**ページ セットアップ**、**\[プロパティ\]** などを送信する必要があります。  
  
 この単純なコマンド ルーティングは既存のオートメーション標準と `IDispatch`で処理できます。  ただし、ここであるため、`IOleCommandTarget` は同じ目標を達成する簡単な方法が用意されています。さらに、`IDispatch` とのオーバーヘッドです:  
  
 `interface IOleCommandTarget : IUnknown`  
  
 `{`  
  
 `HRESULT QueryStatus(`  
  
 `[in] GUID *pguidCmdGroup,`  
  
 `[in] ULONG cCmds,`  
  
 `[in,out][size_is(cCmds)] OLECMD *prgCmds,`  
  
 `[in,out] OLECMDTEXT *pCmdText);`  
  
 `HRESULT Exec(`  
  
 `[in] GUID *pguidCmdGroup,`  
  
 `[in] DWORD nCmdID,`  
  
 `[in] DWORD nCmdExecOpt,`  
  
 `[in] VARIANTARG *pvaIn,`  
  
 `[in,out] VARIANTARG *pvaOut);`  
  
 `}`  
  
 ここで `QueryStatus` のメソッドは、コマンドのセット、**GUID**で識別される設定がサポートされるかどうかをテストします。  この呼び出しは、コマンドまたはステータス情報の名前を記述するコマンド、または返されるテキストのサポートありボックスで **OLECMD** 値 \(構造体\) の配列を格納します。  呼び出し元がコマンドを起動する場合に戻る戻り値を取得するオプションと引数とともに **Exec** にコマンド \(および設定 **GUID**\) を渡すことができます。  
  
## 参照  
 [Active ドキュメント コンテナー](../mfc/active-document-containers.md)