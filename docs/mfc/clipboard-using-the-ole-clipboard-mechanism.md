---
title: "クリップボード : OLE クリップボード機構の使用方法 | Microsoft Docs"
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
  - "アプリケーション [OLE], クリップボードのトピック"
  - "クリップボード [C++], OLE 形式"
  - "書式 [C++], クリップボード (OLE の)"
  - "OLE クリップボード"
  - "OLE クリップボード, 書式"
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# クリップボード : OLE クリップボード機構の使用方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クリップボードを使用してデータを転送するための OLE 使用の標準書式と、OLE 固有の形式。  
  
 アプリケーションのデータを切り取りまたはコピーする場合、データは貼り付け操作で使用するクリップボードに格納されます。  このデータは、さまざまな形式です。  ユーザーがクリップボードからデータを貼り付けることを選択すると、アプリケーションは使用する形式を選択できます。  ユーザーが特定の形式を明確に要求されない限り、貼り付けを使用して多くの情報を提供する形式を選択するために記述する必要があります。  次に、[データ オブジェクトとデータ ソース \(OLE\)](../mfc/data-objects-and-data-sources-ole.md) のトピックを読み込むこともできます。  これらは、データ転送の動作とアプリケーションでそれらを実装する方法について説明します。またはの基礎です。  
  
 Windows は、クリップボードを通じてデータの転送に使用できる一連の標準の書式を定義します。  このメタファイルは、テキスト、ビットマップなどが含まれます。  OLE 多数の OLE 固有の形式も定義します。  これらの標準形式で指定されているよりも多くの詳細を必要とするアプリケーションの場合、独自のカスタム クリップボード形式を登録することをお勧めします。  これを行うには、Win32 API 関数 [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) を使用します。  
  
 たとえば、Microsoft Excel は、スプレッドシートのカスタム書式を登録します。  この形式は、ビットマップがよりも多くの情報をやり取りします。  このデータがスプレッドシート形式をサポートするアプリケーションに貼り付けると、スプレッドシートからすべての式と値が保存され、必要に応じて更新することができます。  Microsoft Excel が開き、形式でクリップボードに OLE アイテムとして渡すことができるようにデータを配置します。  どの OLE コンテナー ドキュメントが埋め込まれたアイテムとしてこの情報を貼り付けることができます。  この埋め込まれたアイテムは Microsoft Excel を使用して変更できます。  クリップボードは、スプレッドシートの選択範囲のイメージの簡単なビットマップが含まれます。  これは、OLE コンテナー ドキュメントまたは描画のようなビットマップ エディターに貼り付けることができます。  ただし、ビットマップの場合は、スプレッドシートとしてデータを処理する方法はありません。  
  
 クリップボードから情報の最大値を取得するには、アプリケーションでこれらのカスタム書式がクリップボードからデータを貼り付ける前に確認する必要があります。  
  
 たとえば、切り取りコマンドを有効にするには、ハンドラーに次のように記述した場合:  
  
 [!CODE [NVC_MFCListView#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCListView#3)]  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [データのコピーと貼り付け](../Topic/Clipboard:%20Copying%20and%20Pasting%20Data.md)  
  
-   [そのほかの形式の追加](../mfc/clipboard-adding-other-formats.md)  
  
-   [Windows クリップボードを使用する](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
-   [OLE データ オブジェクトとデータ ソースと汎用データ転送](../mfc/data-objects-and-data-sources-ole.md)  
  
## 参照  
 [クリップボードのトピック](../mfc/clipboard.md)