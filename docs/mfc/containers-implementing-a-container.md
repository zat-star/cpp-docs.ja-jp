---
title: "コンテナー : コンテナーの実装 | Microsoft Docs"
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
  - "アプリケーション [OLE], OLE コンテナー"
  - "OLE コンテナー, 実装"
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# コンテナー : コンテナーの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、コンテナーの実装に関する詳細な説明を提供するそのほかのトピックにコンテナーとポイントを実装するための手順を示します。  また、これらの機能を記述する文書実装したい場合がある省略可能な OLE 機能を説明します。  
  
#### CWinApp 派生されたクラスを準備するには  
  
1.  `InitInstance` のメンバー関数の **AfxOleInit** を呼び出して OLE ライブラリを初期化してください。  
  
2.  メニューを関連付けるに `InitInstance` の `CDocTemplate::SetContainerInfo` を呼び出すと埋め込まれたアイテム埋め込みがアクティブ化されたときに、アクセラレータのリソースが使用されます。  このトピックの詳細については、「[アクティブ化](../mfc/activation-cpp.md)」を参照してください。  
  
 これらの機能は、コンテナー アプリケーションを作成するには、MFC アプリケーション ウィザードを使用すると、自動的に提供されます。  [MFC EXE プログラムの作成](../Topic/MFC%20Application%20Wizard.md)を参照してください。  
  
#### ビュー クラスを準備するには  
  
1.  ポインターを保持すると、選択した項目を複数選択をサポートする場合、または選択した項目にポインターのリストを、追跡する。  `OnDraw` 関数はすべての OLE アイテムを描画しない必要があります。  
  
2.  このパラメーターに渡される項目が現在選択されているかどうかを確認するために `IsSelected` をオーバーライドします。  
  
3.  **Insert Object** ダイアログ ボックスを表示するに **OnInsertObject** のメッセージ ハンドラーを実装してください。  
  
4.  ビューから埋め込み先編集の OLE 埋め込まれたアイテムにフォーカスを移動するに `OnSetFocus` のメッセージ ハンドラーを実装してください。  
  
5.  含まれているビューの変更を反映するように四角形を変更する必要があります。OLE 埋め込まれたアイテムを通知するために `OnSize` のメッセージ ハンドラーを実装してください。  
  
 これらの機能の実装が 1 アプリケーションから次に大幅に異なるため、アプリケーション ウィザードは基本実装を提供します。  正しく機能するようにアプリケーションを取得するために、これらの関数をカスタマイズする必要があります。  この例については、[コンテナー](../top/visual-cpp-samples.md) サンプルを参照してください。  
  
#### 埋め込まれたとリンク アイテムを処理するには  
  
1.  [COleClientItem](../mfc/reference/coleclientitem-class.md)からクラスを派生してください。  このクラスのオブジェクトは、埋め込まれたまたは OLE ドキュメントにリンクされた項目を表します。  
  
2.  オーバーライド **OnChange**、`OnChangeItemPosition`と `OnGetItemPosition`。  これらの関数は、配置が埋め込まれた変更し、リンクされた項目のサイズ変更を処理します。  
  
 アプリケーション ウィザードによってクラスが派生しますが、その **OnChange** をオーバーライドする必要があり、もう一方は上記の手順 2 の動作と表示された機能します。  スケルトン実装はこれらの関数が 1 アプリケーションから次に異なる方法で実装されるため、ほとんどのアプリケーション用にカスタマイズする必要があります。  この例については、MFC サンプル [DRAWCLI](../top/visual-cpp-samples.md) と [コンテナー](../top/visual-cpp-samples.md)を参照してください。  
  
 コンテナー アプリケーションのメニュー構造に OLE をサポートするためにいくつかの項目を追加する必要があります。  これらの詳細については、「[メニューとリソース: コンテナーの追加](../mfc/menus-and-resources-container-additions.md)」を参照してください。  
  
 また、コンテナー アプリケーションの次の機能をサポートする必要があります:  
  
-   埋め込まれたアイテムを編集するときに、埋め込み先編集の有効化。  
  
     詳細については、「[アクティブ化](../mfc/activation-cpp.md)」を参照してください。  
  
-   サーバー アプリケーションから選択をドラッグ アンド ドロップして OLE アイテムの作成。  
  
     詳細については、「[ドラッグ アンド ドロップ \(OLE\)](../mfc/drag-and-drop-ole.md)」を参照してください。  
  
-   埋め込みオブジェクトまたは組み合わせのコンテナーとサーバー アプリケーションへのリンクを示します。  
  
     詳細については、「[コンテナー: 高度な機能](../mfc/containers-advanced-features.md)」を参照してください。  
  
## 参照  
 [コンテナー](../mfc/containers.md)   
 [コンテナー : クライアント アイテム](../mfc/containers-client-items.md)