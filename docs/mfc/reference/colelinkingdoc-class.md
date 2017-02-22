---
title: "COleLinkingDoc クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleLinkingDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinkingDoc クラス"
  - "OLE コンテナー, クライアント アイテム"
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleLinkingDoc クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE コンテナー ドキュメントの基本クラスです。OLE コンテナー ドキュメントは、ドキュメントが保持する埋め込みアイテムへのリンクをサポートします。  
  
## 構文  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleLinkingDoc::COleLinkingDoc](../Topic/COleLinkingDoc::COleLinkingDoc.md)|`COleLinkingDoc` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleLinkingDoc::Register](../Topic/COleLinkingDoc::Register.md)|OLE システム DLL のドキュメントを登録します。|  
|[COleLinkingDoc::Revoke](../Topic/COleLinkingDoc::Revoke.md)|ドキュメントの登録を取り消します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleLinkingDoc::OnFindEmbeddedItem](../Topic/COleLinkingDoc::OnFindEmbeddedItem.md)|指定された埋め込みアイテムを検索します。|  
|[COleLinkingDoc::OnGetLinkedItem](../Topic/COleLinkingDoc::OnGetLinkedItem.md)|指定したリンク アイテムを検索します。|  
  
## 解説  
 埋め込みアイテムへのリンクをサポートするコンテナー アプリケーションは「リンク コンテナーと呼ばれます」。[OCLIENT](../../top/visual-cpp-samples.md) サンプル アプリケーションはリンク コンテナーの一例です。  
  
 リンクされた成果物のソースが別のドキュメントの埋め込みアイテムの場合、その含むドキュメントは編集する埋め込みアイテムに読み込む必要があります。  したがって、リンク コンテナーは、ユーザーがリンク項目のソースを編集する場合、別のコンテナー アプリケーションが起動する必要があります。  また、アプリケーションは、プログラムで起動時に文書を作成できるように [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) のクラスを使用する必要があります。  
  
 、コンテナーにリンク コンテナーを行うには、[COleDocument](../../mfc/reference/coledocument-class.md)の代わりに `COleLinkingDoc` からドキュメント クラスを派生します。  他の OLE コンテナーによって同様に、アプリケーションのネイティブ データ、または埋め込みまたはリンクされた項目を格納する、クラスをデザインする必要があります。  または、でネイティブ データを格納するためのデータ構造をデザインする必要があります。  \- `CDocItem`、ネイティブ データの派生クラス定義は、ネイティブ データは、OLE データを格納するために `COleDocument` で定義されているインターフェイスを使用できます。  
  
 アプリケーションが別のコンテナーがプログラムで起動するようにアプリケーションの `CWinApp`派生クラスのメンバーとして `COleTemplateServer` のオブジェクトを宣言する:  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/reference/codesnippet/CPP/colelinkingdoc-class_1.h)]  
  
 自分の `CWinApp`の `InitInstance` のメンバー関数の派生クラス、ドキュメント テンプレートを作成し、`COleLinkingDoc`を指定してください。ドキュメント クラスと派生クラス:  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/reference/codesnippet/CPP/colelinkingdoc-class_2.cpp)]  
  
 、のドキュメント テンプレートへの `COleTemplateServer` のオブジェクトをオブジェクトの `ConnectTemplate` のメンバー関数を呼び出して、接続し、**COleTemplateServer::RegisterAll**を呼び出して、OLE システムにあるすべてのクラス オブジェクトを登録する:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/reference/codesnippet/CPP/colelinkingdoc-class_3.cpp)]  
  
 サンプル `CWinApp`のは派生クラスの定義と `InitInstance` 関数は、MFC サンプル [OCLIENT](../../top/visual-cpp-samples.md)の OCLIENT.H と OCLIENT.CPP が表示されます。  
  
 `COleLinkingDoc`の使用の詳細については、" " [コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md) と [コンテナー: 高度な機能](../../mfc/containers-advanced-features.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocument](../Topic/CDocument%20Class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC の OCLIENT サンプル](../../top/visual-cpp-samples.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)