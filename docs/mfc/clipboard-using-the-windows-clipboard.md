---
title: "クリップボード : Windows クリップボードの使用方法 | Microsoft Docs"
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
  - "クリップボード [C++], コマンド"
  - "クリップボード [C++], Windows クリップボード API"
  - "クリップボード コマンド"
  - "クリップボード コマンド, 実装"
  - "コマンド [C++], 実装 (Edit を)"
  - "[切り取り]、[コピー]、[貼り付け] の各コマンドのハンドラー関数"
  - "ハンドラー関数, [切り取り]、[コピー]、[貼り付け] の各コマンド"
  - "Windows クリップボード [C++]"
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# クリップボード : Windows クリップボードの使用方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、MFC アプリケーション内の標準のクリップボード API を使用する方法について説明します。  
  
 Windows のほとんどのアプリケーションは Windows クリップボードに切断またはデータのコピーが、クリップボードからの貼り付けデータをサポートします。  クリップボード データ形式はアプリケーションの間で異なります。  フレームワークはクラスの限られた数のクリップボード形式の限られた数のみをサポートします。  —をビューの編集メニューの…、クリップボードに関するコマンド—切り取り、コピー、および貼り付けできます。実装します。  クラス ライブラリには、これらのコマンドのコマンド ID を定義します: **ID\_EDIT\_CUT**、**ID\_EDIT\_COPY**と **ID\_EDIT\_PASTE**。  メッセージ行のプロンプトも定義されています。  
  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md) は ハンドラー関数にメニュー コマンドで、アプリケーションのメニュー コマンドを処理する方法について説明します。  アプリケーションが編集メニューのクリップボードのハンドラー関数をそのままコマンド、無効に定義する場合。  切り取りとコピー コマンドでハンドラー関数を記述するには、アプリケーションの選択を実装してください。  貼り付けコマンドでハンドラー関数を記述するには、アプリケーションで使用できる形式のデータが含まれているかどうかを参照するようにようにクリップボードを呼び出します。  たとえば、コピー コマンドを有効にするには、ハンドラーに次のように記述した場合:  
  
 [!CODE [NVC_MFCListView#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCListView#2)]  
  
 切り取り、コピー、および貼り付けコマンドでは、特定のコンテキストでのみ有効です。  切り取りとコピー コマンドは何かがクリップボードにあるときに何かが選択されていると、貼り付けコマンドようにのみ有効になります。  コンテキストによってこれらのコマンドを有効にするか、無効にする更新ハンドラー関数を定義することで、この動作を実現できます。  詳細については、「[ユーザーインターフェイス オブジェクトを更新する方法](../mfc/how-to-update-user-interface-objects.md)」を参照してください。  
  
 Microsoft Foundation Class ライブラリには `CEdit` と `CEditView` クラスをテキスト編集にクリップボード サポートします。  OLE クラスは、OLE アイテムを含むクリップボード操作を実装することが簡単になります。  OLE クラスの詳細については、「[クリップボード: OLE のクリップボード機能を使用する](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)」を参照してください。  
  
 ほかの実装して戻す \(**ID\_EDIT\_UNDO**\) などのメニュー コマンドを編集して再実行 \(**ID\_EDIT\_REDO**\) は、行われます。  アプリケーションでこれらのコマンドをサポートする、Visual C\+\+ リソース エディターを使用してリソース ファイルから簡単に削除できます。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [データのコピーと貼り付け](../Topic/Clipboard:%20Copying%20and%20Pasting%20Data.md)  
  
-   [OLE のクリップボード機能を使用する](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## 参照  
 [クリップボードのトピック](../mfc/clipboard.md)