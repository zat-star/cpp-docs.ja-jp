---
title: "OLE コンテナー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df809971ecf8bdd8700217cf6a1965e2973de754
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ole-container-classes"></a>OLE コンテナー クラス
これらのクラスは、コンテナー アプリケーションによって使用されます。 両方`COleLinkingDoc`と`COleDocument`のコレクションを管理`COleClientItem`オブジェクト。 ドキュメント クラスの派生ではなく**CDocument**から派生します`COleLinkingDoc`または`COleDocument`文書に埋め込まれているオブジェクトへのリンクでサポートが必要かどうかによって異なります。  
  
 使用して、`COleClientItem`別のドキュメントから埋め込むまたは別のドキュメントへのリンクは、ドキュメント内の各 OLE 項目を表すオブジェクト。  
  
 [関数](../mfc/reference/coledocobjectitem-class.md)  
 Active ドキュメント コンテインメントをサポートしています。  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 複合ドキュメントの実装、および基本的なコンテナー サポートに対して使用されます。 派生したクラスのコンテナーとして機能する`CDocItem`です。 このクラスは、文書化しの基本クラスは、コンテナーの基底クラスとして使用できる`COleServerDoc`です。  
  
 [直接](../mfc/reference/colelinkingdoc-class.md)  
 派生したクラス`COleDocument`をリンクするため、インフラストラクチャを提供します。 代わりにこのクラスから、コンテナー アプリケーションのドキュメント クラスを派生させる必要があります`COleDocument`埋め込みオブジェクトへのリンクをサポートするようにする場合。  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 リッチ エディット コントロールに含まれる OLE クライアント アイテムの一覧を保持します。 と共に使用[CRichEditView](../mfc/reference/cricheditview-class.md)と[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)です。  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 抽象基本クラスの`COleClientItem`と`COleServerItem`です。 派生したクラスのオブジェクトを`CDocItem`文書の一部を表します。  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 埋め込みまたはリンクされている OLE アイテムへの接続のクライアント側を表すクライアント アイテム クラスです。 クライアント アイテムは、このクラスから派生します。  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 クライアント側のアクセスは、項目で使用する場合は、リッチ エディット コントロールに格納されている OLE`CRichEditView`と`CRichEditDoc`です。  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE の処理中のエラーによる例外。 このクラスは、コンテナーとサーバーの両方で使用されます。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../mfc/class-library-overview.md)

