---
title: "印刷および印刷プレビュー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bedcf1ecf851ed6d9dd396ee6a82d6d2c058930b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="printing-and-print-preview"></a>印刷および印刷プレビュー
MFC クラスを使用して、プログラムのドキュメントの印刷と印刷プレビューをサポートしています[CView](../mfc/reference/cview-class.md)です。 基本的な印刷と印刷プレビューでは、単に上書きビュー クラスの[OnDraw](../mfc/reference/cview-class.md#ondraw)メンバー関数を行うことができます。 その関数が実際のプリンターのプリンター デバイス コンテキストを画面上の表示を描画できるまたは画面にプリンターをシミュレートするデバイス コンテキストにします。  
  
 マルチページ ドキュメントの印刷とプレビュー、およびそれらにヘッダーとページ フッターを追加する、印刷されたドキュメントを改ページ調整を管理するためのコードを追加することもできます。  
  
 この一連のトピックでは、印刷の Microsoft Foundation Class ライブラリ (MFC) を実装する方法と、フレームワークに既に組み込まれている印刷のアーキテクチャを活用する方法について説明します。 アーティクルは、方法 MFC をサポートします。 印刷プレビュー機能の簡単な実装を使用し、その機能を変更する方法も説明します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [印刷](../mfc/printing.md)  
  
-   [印刷プレビューのアーキテクチャ](../mfc/print-preview-architecture.md)  
  
-   [サンプル](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
