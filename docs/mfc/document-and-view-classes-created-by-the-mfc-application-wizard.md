---
title: "文書化し、MFC アプリケーション ウィザードで作成したクラスの表示 |Microsoft ドキュメント"
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
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cddf8b72e9927a298cbd39d4f9790965e4b8f74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC のアプリケーション ウィザードで作成されるドキュメント クラスとビュー クラス
MFC アプリケーション ウィザードできますを簡単に開始プログラムの開発をスケルトンのドキュメントとビュー クラスを作成することで。 できます[コマンドとメッセージをこれらのクラスにマップ](../mfc/reference/mapping-messages-to-functions.md)およびそのメンバー関数を作成する Visual C ソース コード エディターを使用します。  
  
 MFC アプリケーション ウィザードによって作成されたドキュメント クラスがクラスから派生した[CDocument](../mfc/reference/cdocument-class.md)です。 ビュー クラスから派生[CView](../mfc/reference/cview-class.md)です。 アプリケーション ウィザード ダイアログ ボックスで指定すること、アプリケーションのウィザードは、これらのクラスとプロジェクト名に基づいてこれらを含むファイルの名前。 アプリケーション ウィザードで、既定の名前を変更するのにクラスの生成 ページを使用できます。  
  
 一部のアプリケーションには、1 つ以上のドキュメント クラス、ビュー クラス、またはフレーム ウィンドウ クラスを必要があります。 詳細については、次を参照してください。[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)します。  
  
## <a name="see-also"></a>参照  
 [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

