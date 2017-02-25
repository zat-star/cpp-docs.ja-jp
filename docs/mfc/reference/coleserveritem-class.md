---
title: "COleServerItem クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleServerItem クラス"
  - "OLE サーバー アプリケーション, 管理 (サーバー ドキュメントの)"
  - "OLE サーバー アプリケーション, サーバー インターフェイス"
  - "OLE サーバー ドキュメント"
  - "サーバー, OLE"
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleServerItem クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE アイテムへのサーバー インターフェイスが用意されています。  
  
## 構文  
  
```  
class COleServerItem : public CDocItem  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleServerItem::COleServerItem](../Topic/COleServerItem::COleServerItem.md)|`COleServerItem` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleServerItem::AddOtherClipboardData](../Topic/COleServerItem::AddOtherClipboardData.md)|`COleDataSource` の場所の表示および変換形式を追加します。|  
|[COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md)|項目をクリップボードにコピーします。|  
|[COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md)|ドラッグ アンド ドロップ操作を実行します。|  
|[COleServerItem::GetClipboardData](../Topic/COleServerItem::GetClipboardData.md)|データ転送に使用するデータ ソースを取得します \(ドラッグ アンド ドロップまたはクリップボード\)。|  
|[COleServerItem::GetDocument](../Topic/COleServerItem::GetDocument.md)|項目を含むサーバーのドキュメントを返します。|  
|[COleServerItem::GetEmbedSourceData](../Topic/COleServerItem::GetEmbedSourceData.md)|OLE アイテムの **CF\_EMBEDSOURCE** データを取得します。|  
|[COleServerItem::GetItemName](../Topic/COleServerItem::GetItemName.md)|項目の名前を返します。  リンクされた成果物のみに使用されます。|  
|[COleServerItem::GetLinkSourceData](../Topic/COleServerItem::GetLinkSourceData.md)|OLE アイテムの `CF_LINKSOURCE` データを取得します。|  
|[COleServerItem::GetObjectDescriptorData](../Topic/COleServerItem::GetObjectDescriptorData.md)|OLE アイテムの **CF\_OBJECTDESCRIPTOR** データを取得します。|  
|[COleServerItem::IsConnected](../Topic/COleServerItem::IsConnected.md)|項目が現在アクティブなコンテナーにアタッチされているかどうかを示します。|  
|[COleServerItem::IsLinkedItem](../Topic/COleServerItem::IsLinkedItem.md)|項目がリンク OLE アイテムを表すかどうかを示します。|  
|[COleServerItem::NotifyChanged](../Topic/COleServerItem::NotifyChanged.md)|自動更新リンクの更新があるすべてのコンテナーを更新します。|  
|[COleServerItem::OnDoVerb](../Topic/COleServerItem::OnDoVerb.md)|動詞を実装するために呼び出されます。|  
|[COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)|が呼び出されるとコンテナーの項目を描画要求; 必要な実装。|  
|[COleServerItem::OnDrawEx](../Topic/COleServerItem::OnDrawEx.md)|特化された項目の描画のために呼び出されます。|  
|[COleServerItem::OnGetClipboardData](../Topic/COleServerItem::OnGetClipboardData.md)|クリップボードにコピーされたデータを取得するために、フレームワークによって呼び出されます。|  
|[COleServerItem::OnGetExtent](../Topic/COleServerItem::OnGetExtent.md)|OLE アイテムのサイズを取得するために、フレームワークによって呼び出されます。|  
|[COleServerItem::OnInitFromData](../Topic/COleServerItem::OnInitFromData.md)|指定されたデータ転送のオブジェクトの内容を使用して OLE アイテムを初期化するために、フレームワークによって呼び出されます。|  
|[COleServerItem::OnQueryUpdateItems](../Topic/COleServerItem::OnQueryUpdateItems.md)|どの項目リンクが更新が必要かどうかを判断するために呼び出されます。|  
|[COleServerItem::OnRenderData](../Topic/COleServerItem::OnRenderData.md)|遅延レンダリングの一部として取得します。|  
|[COleServerItem::OnRenderFileData](../Topic/COleServerItem::OnRenderFileData.md)|`CFile` へのデータを取得は遅延レンダリングの一部としてオブジェクトを指定します。|  
|[COleServerItem::OnRenderGlobalData](../Topic/COleServerItem::OnRenderGlobalData.md)|遅延レンダリングの一部として `HGLOBAL` にデータを取得します。|  
|[COleServerItem::OnSetColorScheme](../Topic/COleServerItem::OnSetColorScheme.md)|項目の配色を設定します。|  
|[COleServerItem::OnSetData](../Topic/COleServerItem::OnSetData.md)|項目のデータが設定されます。|  
|[COleServerItem::OnSetExtent](../Topic/COleServerItem::OnSetExtent.md)|OLE アイテムのサイズを設定するために、フレームワークによって呼び出されます。|  
|[COleServerItem::OnUpdate](../Topic/COleServerItem::OnUpdate.md)|ドキュメントの部分が属する項目という変更されます。|  
|[COleServerItem::OnUpdateItems](../Topic/COleServerItem::OnUpdateItems.md)|サーバー上のドキュメントのすべての項目の表示のキャッシュを更新するために呼び出されます。|  
|[COleServerItem::SetItemName](../Topic/COleServerItem::SetItemName.md)|項目の名前を設定します。  リンクされた成果物のみに使用されます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleServerItem::GetDataSource](../Topic/COleServerItem::GetDataSource.md)|ストアの変換形式にオブジェクトを使用するを取得します。|  
|[COleServerItem::OnHide](../Topic/COleServerItem::OnHide.md)|OLE アイテムを非表示にするために、フレームワークによって呼び出されます。|  
|[COleServerItem::OnOpen](../Topic/COleServerItem::OnOpen.md)|独自のトップレベル ウィンドウの OLE アイテムを表示するために、フレームワークによって呼び出されます。|  
|[COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md)|を呼び出したときに項目コンテナーの要求を示す。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleServerItem::m\_sizeExtent](../Topic/COleServerItem::m_sizeExtent.md)|表示されるか OLE アイテムの量に関するサーバーに通知します。|  
  
## 解説  
 リンク項目は、サーバー上のドキュメントの一部またはすべてを表すことができます。  埋め込みアイテムは、サーバー全体のドキュメントを常に表します。  
  
 `COleServerItem` のクラスは、コンテナー アプリケーションからの要求に対して OLE システムのダイナミック リンク ライブラリ \(DLLs\) によって呼び出されます複数のオーバーライド可能なメンバー関数は、通常は定義します。  これらのメンバー関数は、を表示するかによって、アクションを実行したり、さまざまな形式のデータを取得するなど、さまざまな方法で項目を、間接的に処理するコンテナー アプリケーションができます。  
  
 `COleServerItem`を使用するには、からクラスを派生し、[OnDraw](../Topic/COleServerItem::OnDraw.md) と [シリアル化します。](../Topic/CObject::Serialize.md) のメンバー関数を実装します。  `OnDraw` 関数は、コンテナー アプリケーションで複合ドキュメントを開くときに、項目のメタファイルの表現を提供し、表示されるようにします。  `CObject` の `Serialize` 関数はネイティブの項目を表示し、サーバーとコンテナー アプリケーションの間で転送されるように、埋め込みアイテムができます。  [OnGetExtent](../Topic/COleServerItem::OnGetExtent.md) は、コンテナーに項目の自然なサイズを提供し、項目のサイズを変更するためにコンテナーを有効にします。  
  
 サーバーと関連トピックに関する詳細については、" "および「" [サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md) 作成 [コンテナー: 高度な機能](../../mfc/containers-advanced-features.md)のコンテナー\/サーバー アプリケーション」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC HIERSVR サンプル](../../top/visual-cpp-samples.md)   
 [CDocItem クラス](../../mfc/reference/cdocitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc クラス](../Topic/COleServerDoc%20Class.md)   
 [COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)