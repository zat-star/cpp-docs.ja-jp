---
title: "レコード ビューのユーザー インターフェイスの更新 (MFC データ アクセス) | Microsoft Docs"
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
  - "メニュー, 更新 (コンテキスト変更に応じて)"
  - "レコード ビュー, ユーザー インターフェイス"
  - "ユーザー インターフェイス, 更新"
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# レコード ビューのユーザー インターフェイスの更新 (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CRecordView` および `CDaoRecordView` には、ナビゲーション コマンドに対する既定のユーザー インターフェイス更新ハンドラーも用意されています。  これらのハンドラーにより、ユーザー インターフェイス オブジェクト \(メニュー項目とツール バー ボタン\) の有効\/無効が自動的に切り替えられます。  アプリケーション ウィザードには標準的なメニューが用意されていますが、**\[ドッキング可能ツール バー\]** オプションを選択すると、コマンド用の一連のツール バー ボタンが表示されます。  `CRecordView` を使用してレコード ビュー クラスを作成する場合は、同じユーザー インターフェイス オブジェクトをアプリケーションに追加することが必要になることがあります。  
  
### エディター メニューを使用してメニュー リソースを作成するには  
  
1.  [メニュー エディター](../Topic/Menu%20Editor.md)の使用に関する情報を参照して、4 つの同じコマンドを含む独自のメニューを作成します。  
  
#### グラフィックス エディターを使用してツール バー ボタンを作成するには  
  
1.  「[ツール バー エディター](../mfc/toolbar-editor.md)」の使用に関する情報を参照し、ツール バー リソースを編集して、レコード移動コマンド用のツール バー ボタンを追加します。  
  
## 参照  
 [レコード ビュー内の移動](../Topic/Supporting%20Navigation%20in%20a%20Record%20View%20%20\(MFC%20Data%20Access\).md)   
 [レコード ビューの使用法](../data/using-a-record-view-mfc-data-access.md)