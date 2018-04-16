---
title: "印刷 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01ee396a7866179bd140f203192d1bdcbfb4681e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="printing"></a>印刷
Microsoft Windows では、デバイスに依存しないディスプレイを実装します。 MFC では、つまり、同じの描画呼び出しで、`OnDraw`ビュー クラスのメンバー関数は、表示にし、プリンターなどの他のデバイスに描画します。 印刷プレビューは、ターゲット デバイスは、表示するためのシミュレートされたプリンターの出力です。  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>フレームワークの役割と印刷でのロール  
 ビュー クラスには、次の責任があります。  
  
-   ページ数が、ドキュメントでは、フレームワークに伝えます。  
  
-   指定したページを印刷するメッセージが表示されたら、ドキュメントの部分を描画します。  
  
-   割り当て、フォントまたは印刷に必要なその他のグラフィックス デバイス インターフェイス (GDI) リソースを解放します。  
  
-   必要に応じて、いずれかの送信モードを変更する、プリンターなど、特定のページを印刷する前に、ページ単位で印刷の向きを変更するために必要なコードをエスケープします。  
  
 フレームワークの役割は次のとおりです。  
  
-   表示、**印刷** ダイアログ ボックス。  
  
-   作成、 [CDC](../mfc/reference/cdc-class.md)プリンターのオブジェクト。  
  
-   呼び出す、 [StartDoc](../mfc/reference/cdc-class.md#startdoc)と[EndDoc](../mfc/reference/cdc-class.md#enddoc)のメンバー関数は、`CDC`オブジェクト。  
  
-   繰り返し呼び出し、 [StartPage](../mfc/reference/cdc-class.md#startpage)のメンバー関数、`CDC`オブジェクト、ページを印刷するか、および呼び出しビュー クラスを通知、 [EndPage](../mfc/reference/cdc-class.md#endpage)のメンバー関数、`CDC`オブジェクト。  
  
-   適切な時点で、ビューでは、オーバーライド可能な関数を呼び出します。  
  
 次の記事では、フレームワークで印刷と印刷プレビューをサポートする方法について説明します。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [既定の印刷を実行する方法](../mfc/how-default-printing-is-done.md)  
  
-   [マルチページ ドキュメント](../mfc/multipage-documents.md)  
  
-   [ヘッダーとフッター](../mfc/headers-and-footers.md)  
  
-   [印刷用 GDI リソースの割り当てください。](../mfc/allocating-gdi-resources.md)  
  
-   [印刷プレビュー](../mfc/print-preview-architecture.md)  
  
## <a name="see-also"></a>参照  
 [[印刷と印刷プレビュー]](../mfc/printing-and-print-preview.md)

