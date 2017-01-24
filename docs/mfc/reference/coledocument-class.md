---
title: "COleDocument クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDocument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDocument クラス"
  - "ドキュメント, OLE"
  - "OLE コンテナー, クライアント アイテム"
  - "OLE ドキュメント"
  - "OLE ドキュメント, 基本クラス"
  - "ビジュアル編集, OLE ドキュメントの基本クラス"
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDocument クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ビジュアル編集をサポートする OLE ドキュメントの基本クラスです。  
  
## 構文  
  
```  
class COleDocument : public CDocument  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleDocument::COleDocument](../Topic/COleDocument::COleDocument.md)|`COleDocument` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDocument::AddItem](../Topic/COleDocument::AddItem.md)|ドキュメントによって保持される項目のリストに項目を追加します。|  
|[COleDocument::ApplyPrintDevice](../Topic/COleDocument::ApplyPrintDevice.md)|ドキュメントのすべてのクライアント項目の印刷対象デバイスを設定します。|  
|[COleDocument::EnableCompoundFile](../Topic/COleDocument::EnableCompoundFile.md)|OLE で保存します。のドキュメントはストレージのファイル形式を構成しました。|  
|[COleDocument::GetInPlaceActiveItem](../Topic/COleDocument::GetInPlaceActiveItem.md)|現在埋め込み先編集が有効な OLE アイテムを返します。|  
|[COleDocument::GetNextClientItem](../Topic/COleDocument::GetNextClientItem.md)|反復の次のクライアント項目を取得します。|  
|[COleDocument::GetNextItem](../Topic/COleDocument::GetNextItem.md)|反復の次のドキュメント アイテムを取得します。|  
|[COleDocument::GetNextServerItem](../Topic/COleDocument::GetNextServerItem.md)|反復の次のサーバー項目を取得します。|  
|[COleDocument::GetPrimarySelectedItem](../Topic/COleDocument::GetPrimarySelectedItem.md)|ドキュメントの主要選択された OLE アイテムを返します。|  
|[COleDocument::GetStartPosition](../Topic/COleDocument::GetStartPosition.md)|最初の位置をイテレーションを開始するを取得します。|  
|[COleDocument::HasBlankItems](../Topic/COleDocument::HasBlankItems.md)|ドキュメントの空白の項目の確認。|  
|[COleDocument::OnShowViews](../Topic/COleDocument::OnShowViews.md)|ドキュメントの表示または非表示になったときに呼び出されます。|  
|[COleDocument::RemoveItem](../Topic/COleDocument::RemoveItem.md)|ドキュメントによって保持される項目のリストから項目を削除します。|  
|[COleDocument::UpdateModifiedFlag](../Topic/COleDocument::UpdateModifiedFlag.md)|含まれている OLE アイテムのいずれかが変更された場合、変更されるように、ドキュメントをマークします。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDocument::OnEditChangeIcon](../Topic/COleDocument::OnEditChangeIcon.md)|変更のアイコンのメニュー コマンドのイベントを処理します。|  
|[COleDocument::OnEditConvert](../Topic/COleDocument::OnEditConvert.md)|1 種類の間で埋め込まれるか、リンクされたオブジェクトの変換を行います。|  
|[COleDocument::OnEditLinks](../Topic/COleDocument::OnEditLinks.md)|リンクのイベントを処理するには、\[編集\]メニューにコマンド。|  
|[COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)|ドキュメントを添付してメール メッセージを送信します。|  
|[COleDocument::OnUpdateEditChangeIcon](../Topic/COleDocument::OnUpdateEditChangeIcon.md)|編集または変更のアイコンのメニュー オプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|  
|[COleDocument::OnUpdateEditLinksMenu](../Topic/COleDocument::OnUpdateEditLinksMenu.md)|リンクの編集\]メニュー オプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|  
|[COleDocument::OnUpdateObjectVerbMenu](../Topic/COleDocument::OnUpdateObjectVerbMenu.md)|編集\/*ObjectName* メニューのオプションおよび編集\/*要素*からアクセス動詞のサブメニューのコマンド UI を更新するために、フレームワークによって呼び出されます。|  
|[COleDocument::OnUpdatePasteLinkMenu](../Topic/COleDocument::OnUpdatePasteLinkMenu.md)|貼り付け、特別なメニュー オプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|  
|[COleDocument::OnUpdatePasteMenu](../Topic/COleDocument::OnUpdatePasteMenu.md)|\[貼り付け\]メニュー オプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|  
  
## 解説  
 `COleDocument` はから派生します **CDocument**、Microsoft Foundation Class ライブラリに用意されているドキュメント\/ビュー アーキテクチャを使用するように OLE アプリケーションができます。  
  
 `COleDocument` は、ハンドルの OLE アイテムへの [CDocItem](../../mfc/reference/cdocitem-class.md) のオブジェクトのコレクションとしてドキュメントを処理します。  ドキュメントが OLE アイテムを含める必要があるため、コンテナーとサーバー アプリケーションは両方とも、このようなアーキテクチャが必要です。  [COleServerItem](../../mfc/reference/coleserveritem-class.md) と [COleClientItem](../../mfc/reference/coleclientitem-class.md) のクラスは、`CDocItem`両方から派生したアプリケーションと OLE の項目間の対話を管理します。  
  
 単純なコンテナー アプリケーションを作成したら、`COleDocument`からドキュメント クラスを派生します。  ドキュメントに含まれる埋め込みアイテムへのリンクをサポートするコンテナー アプリケーションを作成したら [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)からドキュメント クラスを派生します。  サーバー アプリケーションまたは組み合わせのコンテナー\/サーバーを作成する場合、[COleServerDoc](../Topic/COleServerDoc%20Class.md)からドキュメント クラスを派生します。  `COleLinkingDoc` と `COleServerDoc` は `COleDocument`から派生しているため、これらのクラスは `COleDocument` と **CDocument**で使用できるすべてのサービスを継承します。  
  
 `COleDocument`を使用するには、からクラスを派生し、アプリケーションの非 OLE のデータ、または埋め込みまたはリンクされた項目を管理する機能を追加します。  \- `CDocItem`ネイティブ データ定義すると、格納する派生クラスを、OLE と非 OLE のデータを格納する `COleDocument` で定義されている既定の実装を使用できます。  また、非 OLE のデータを OLE アイテムとは別に格納するための独自のデータ構造をデザインできます。  詳細については、" "を参照してください。[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md)。  
  
 **CDocument** がメールのサポート \(MAPI\) がある場合は、メールしてドキュメントの送信をサポートします。  `COleDocument` は複合ドキュメントを正しく処理するに [OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md) を更新しました。  詳細については、" " [MAPI](../../mfc/mapi.md) と [MFC の MAPI のサポート](../../mfc/mapi-support-in-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocument](../Topic/CDocument%20Class.md)  
  
 `COleDocument`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC コンテナーのサンプル](../../top/visual-cpp-samples.md)   
 [MFC MFCBIND サンプル](../../top/visual-cpp-samples.md)   
 [CDocument クラス](../Topic/CDocument%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)