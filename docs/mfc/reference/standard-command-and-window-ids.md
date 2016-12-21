---
title: "標準コマンド ID とウィンドウ ID | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "標準コマンドと Window ID"
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 標準コマンド ID とウィンドウ ID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Class ライブラリには Afxres.h の標準コマンド ID とウィンドウ ID を定義します。  これらの ID は、リソース エディターとプロパティ ウィンドウ内で最もよく使用されますハンドラー関数にメッセージをマップするために使用します。  すべての標準コマンドに **ID\_** が付きます。  たとえば、メニュー エディターを使用すると、標準 `ID_FILE_OPEN` コマンド ID には、ファイルを開くメニュー項目をバインドします  
  
 ほとんどの標準コマンドに対して、アプリケーション コードはフレームワーク自体が主要フレームワーク クラス \(`CWinThread`、`CWinApp`、`CView`、**CDocument**など\) のメッセージ マップを通じてコマンドを処理するため、コマンド ID を参照する必要はありません。  
  
 標準コマンド ID に加えて、**AFX\_ID**プレフィックスを持つ他の標準 ID が定義されます。  これらの ID は標準の Windows ID \(プレフィックス **AFX\_IDW\_**\)、文字列の ID \(prefix **AFX\_IDS\_**\) を含む、複数の型を選択します。  
  
 **AFX\_ID** のプレフィックスで始まる ID は、プログラマによって頻繁にオーバーライド フレームワークが機能する場合は、**AFX\_ID**s.を示すこれらの ID を示す必要があります。使用されません。  
  
 ID は、この参照で個別については説明しません。  テクニカル ノート [20](../../mfc/tn020-id-naming-and-numbering-conventions.md)、[21](../../mfc/tn021-command-and-message-routing.md)と [22](../../mfc/tn022-standard-commands-implementation.md)の詳細な情報を確認できます。  
  
> [!NOTE]
>  ヘッダー ファイル Afxres.h は Afxwin.h に間接的に含まれます。  アプリケーションのリソース スクリプト \(.rc\) ファイルに明示的に次のステートメントを追加する必要があります:  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/CPP/standard-command-and-window-ids_1.h)]  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)