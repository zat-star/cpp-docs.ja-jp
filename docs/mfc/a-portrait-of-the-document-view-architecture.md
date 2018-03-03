---
title: "ドキュメント/ビュー アーキテクチャの全体像 |Microsoft ドキュメント"
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
- documents [MFC], views
- multiple views [MFC], updating from document
- document/view architecture [MFC]
- views [MFC], and user input
- documents [MFC], accessing data from view
- views [MFC], updating
- input [MFC], view class
- documents [MFC], multiple views
- document/view architecture [MFC], accessing data from view
- document/view architecture [MFC], about document/view architecture
- views [MFC], accessing document data from
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ceadc55945a31e4787287beb6943897784aeaad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="a-portrait-of-the-documentview-architecture"></a>ドキュメント/ビュー アーキテクチャの全体像
ドキュメントとビューは一般的な MFC アプリケーション内の組で使用します。 ドキュメントでデータが格納されますが、ビューのデータにアクセスする権限がします。 ドキュメントのビューからの分離は、その表示から、記憶域とデータのメンテナンスを区切ります。  
  
## <a name="gaining-access-to-document-data-from-the-view"></a>ドキュメント ビューからデータにアクセスします。  
 ビュー データにアクセスする、ドキュメントのいずれかで、 [GetDocument](../mfc/reference/cview-class.md#getdocument)関数は、ドキュメント、または C++ のクラス ビューをすることで、ポインターが返されます`friend`ドキュメント クラスのです。 ビューは、このデータへのアクセスを使用して描画またはそれ以外の場合を操作するのに準備ができたときにデータを取得します。  
  
 たとえば、ビューから[OnDraw](../mfc/reference/cview-class.md#ondraw)メンバー関数、ビューを使用して**GetDocument**ドキュメント ポインターを取得します。 そのポインターを使用してアクセスするし、`CString`ドキュメント内のデータ メンバーです。 ビューは、文字列を渡します、`TextOut`関数。 この例のコードを参照してください[ビューの描画](../mfc/drawing-in-a-view.md)です。  
  
## <a name="user-input-to-the-view"></a>ビューにユーザー入力  
 ビューの選択またはデータの編集のいずれかとしてそれ自体のマウス クリック解釈できます。 同様にデータを入力または編集としてキーストロークを解釈が可能性があります。 テキストを管理するビューで、ユーザーの種類を文字列とします。 ビューは、ドキュメントへのポインターを取得し、ポインターを使用して、ドキュメントでは、いくつかのデータ構造に格納する新しいデータを渡します。  
  
## <a name="updating-multiple-views-of-the-same-document"></a>同じドキュメントの複数のビューの更新  
 同じドキュメントの複数のビューを持つアプリケーションに — などのテキスト エディターで分割ウィンドウ: ビューが最初に、新しいデータをドキュメントに渡します。 ドキュメントの呼び出し、 [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)メンバー関数を新しいデータを反映して更新するには、ドキュメントのすべてのビューが示されます。 これは、ビューを同期します。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ドキュメント/ビュー アーキテクチャの利点](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [ドキュメント/ビュー アーキテクチャの代替手段](../mfc/alternatives-to-the-document-view-architecture.md)  
  
## <a name="see-also"></a>参照  
 [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

