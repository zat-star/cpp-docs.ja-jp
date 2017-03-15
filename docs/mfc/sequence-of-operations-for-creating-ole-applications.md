---
title: "OLE アプリケーションの作成手順 | Microsoft Docs"
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
  - "アプリケーション [OLE]"
  - "アプリケーション [OLE], 作成"
  - "OLE アプリケーション [C++]"
  - "OLE アプリケーション [C++], 作成"
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE アプリケーションの作成手順
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は、OLE リンクと埋め込みアプリケーション作成のロールおよびフレームワークの役割を示しています。  これらの手順では、シーケンスの代わりに使用できるオプションを表します。  
  
### OLE アプリケーションの作成  
  
|タスク|プログラマの作業|フレームワークの働き|  
|---------|--------------|----------------|  
|COM コンポーネントを作成します。|MFC アプリケーション ウィザードを実行します。  **複合ドキュメント サポート** タブの **フル サーバー** または **Mini\-server** を選択します。|フレームワークは、有効な COM コンポーネントの機能のスケルトン アプリケーションを作成します。  COM 機能はすべて、わずかな変更のみを使用して既存のアプリケーションに転送できます。|  
|コンテナー アプリケーションを最初から作成します。|MFC アプリケーション ウィザードを実行します。  **複合ドキュメント サポート** タブの **コンテナー** を選択します。  クラス ビューを使用して、ソース・コード エディターに移動します。  COM のハンドラー関数のコードを入力します。|フレームワークは COM コンポーネント \(サーバー\) のアプリケーションで作成された COM オブジェクトを挿入するスケルトン アプリケーションを作成します。|  
|最初からオートメーションをサポートするアプリケーションを作成します。|MFC アプリケーション ウィザードを実行します。  **\[高度な機能\]** タブから **オートメーション** をクリックします。  オートメーションのアプリケーションのメソッドとプロパティを公開するには、クラス ビューを使用してください。|フレームワークは、他のアプリケーションによってアクティブ化、自動化できるスケルトン アプリケーションを作成します。|  
  
## 参照  
 [フレームワークを使ったアプリケーションの作成](../mfc/building-on-the-framework.md)   
 [MFC アプリケーションの作成手順](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [ActiveX コントロールの作成手順](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [データベース アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-database-applications.md)