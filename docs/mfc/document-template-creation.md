---
title: "テンプレートの作成を文書化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04950601a74b1ed3e44b236e1d07dcdff997eca6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="document-template-creation"></a>ドキュメント テンプレートの作成
応答で、新しいドキュメントを作成するときに、`New`または**開く**コマンドを**ファイル**] メニューの [ドキュメント テンプレートも新しいフレーム ウィンドウを作成したドキュメントを表示します。  
  
 ドキュメント テンプレートのコンス トラクターは、ドキュメント、windows、およびビューを作成できるテンプレートの種類を指定します。 これは、ドキュメント テンプレートのコンス トラクターに渡す引数によって決まります。 次のコード例の作成、 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)サンプル アプリケーションについては。  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]  
  
 新しいポインター`CMultiDocTemplate`オブジェクトに渡す引数として使用[AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate)です。 引数、`CMultiDocTemplate`コンス トラクターは、ドキュメントの種類のメニューとアクセラレータに関連付けられているリソース ID を含めるしの 3 つを使用して、 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class)マクロです。 `RUNTIME_CLASS`返します、 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)引数としてという名前の C++ クラスのオブジェクト。 3 つ`CRuntimeClass`ドキュメント テンプレートのコンス トラクターに渡されたオブジェクトは、ドキュメントの作成プロセス中に、指定されたクラスの新しいオブジェクトを作成するために必要な情報を指定します。 作成するドキュメント テンプレートの作成の例、`CScribDoc`オブジェクトと`CScribView`接続されているオブジェクト。 ビューは、標準の MDI 子フレーム ウィンドウで囲まれます。  
  
## <a name="see-also"></a>参照  
 [ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [ドキュメント/ビューの作成](../mfc/document-view-creation.md)   
 [MFC オブジェクト間の関係](../mfc/relationships-among-mfc-objects.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../mfc/creating-new-documents-windows-and-views.md)

