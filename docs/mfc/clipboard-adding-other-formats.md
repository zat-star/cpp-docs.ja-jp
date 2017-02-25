---
title: "クリップボード : その他のデータ形式の追加 | Microsoft Docs"
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
  - "クリップボードのトピック, 書式"
  - "カスタム クリップボード データの形式"
  - "カスタム形式"
  - "カスタム形式, 配置 (クリップボードに)"
  - "書式 [C++], クリップボードのトピック"
  - "登録 (カスタム クリップボード データ形式を)"
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# クリップボード : その他のデータ形式の追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、OLE サポートのサポートされている形式のリスト \(特に展開する方法について説明します。  トピック [クリップボード: データのコピーと貼り付け](../Topic/Clipboard:%20Copying%20and%20Pasting%20Data.md)、クリップボードからコピーと貼り付けをサポートするために必要な最小限の実装について説明します。  これはすべての場合、クリップボードに配置される唯一の形式です `CF_METAFILEPICT`、**CF\_EMBEDSOURCE**、**CF\_OBJECTDESCRIPTOR**可能性が `CF_LINKSOURCE`実装します。  ほとんどのアプリケーションでは、この 3 をクリップボードの形式が必要です。  
  
##  <a name="_core_registering_custom_formats"></a> カスタム書式の登録  
 独自のカスタム書式設定を作成するには、カスタム クリップボード形式を登録するときに使用するのと同じ手順に従います。: 形式の名前を **RegisterClipboardFormat** 関数に渡し、形式 ID として戻り値を使用します。  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> クリップボードの形式を指定できます。  
 データがネイティブであるコピーされるかどうかによってクリップボードに置くことによって多くの形式を追加するには、`COleClientItem` または `COleServerItem` から派生したクラスの `OnGetClipboardData` 関数をオーバーライドする必要があります。  この関数では、次の手順を実行する必要があります。  
  
#### クリップボードの形式に  
  
1.  `COleDataSource` オブジェクトを作成します。  
  
2.  サポートされる形式の一覧に `COleDataSource::CacheGlobalData`を呼び出してネイティブ データ形式を追加する関数にこのデータ ソースを渡します。  
  
3.  、サポートする各標準書式の `COleDataSource::CacheGlobalData` を呼び出して標準書式を追加します。  
  
 この方法は、MFC の OLE サンプル プログラム [HIERSVR](../top/visual-cpp-samples.md) で使用されます。**CServerItem** クラスの `OnGetClipboardData` メンバー関数を参照してください\)。  このサンプルの違いは HIERSVR が他の標準形式をサポートしないため、ステップ 3 が実装されないことです。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [OLE データ オブジェクトとデータ ソースと汎用データ転送](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## 参照  
 [クリップボード : OLE クリップボード機構の使用方法](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)