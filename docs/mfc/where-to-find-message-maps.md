---
title: "メッセージ マップの所在 | Microsoft Docs"
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
  - "検索 (メッセージ マップを)"
  - "マクロ, メッセージ マップ"
  - "メッセージ マップ, 検索"
  - "メッセージ マップ マクロ"
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メッセージ マップの所在
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーション ウィザードを使って新しいスケルトン アプリケーションを作成するときは、アプリケーション ウィザードでは、作成した各コマンドターゲット クラスにメッセージ マップを作成します。  これは、派生のアプリケーション、ドキュメント、ビュー、およびフレーム ウィンドウ クラスが含まれています。  これらのメッセージ マップの一部に既に特定のメッセージと定義されたコマンドのアプリケーション ウィザードで指定するエントリを持つ部分は、追加するハンドラーのプレースホルダーだけです。  
  
 クラスのメッセージ マップはクラスの .cpp ファイルにあります。  アプリケーション ウィザードで作成された基本的なメッセージ マップを使用してメッセージのエントリを追加するには、プロパティ ウィンドウを使用して、各クラスが処理するようにようにしました。  通常のメッセージ マップは次のようにエントリを追加するとなります。:  
  
 [!CODE [NVC_MFCMessageHandling#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#1)]  
  
 メッセージ マップは、マクロのコレクションで構成されます。  2 種類のマクロは、[BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) と [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md)は、メッセージ マップをかっこで囲んで指定します。  他のマクロは、`ON_COMMAND`など、メッセージ マップの内容を入力します。  
  
> [!NOTE]
>  メッセージ マップ マクロはセミコロンが続きます。  
  
 新しいクラスを作成するにクラス追加ウィザードを使用すると、クラスにメッセージ マップを提供します。  また、ソース・コード エディターを使用してメッセージ マップを手動で作成できます。  
  
## 参照  
 [フレームワークのメッセージ マップ検索方法](../mfc/how-the-framework-searches-message-maps.md)