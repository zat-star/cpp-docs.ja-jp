---
title: "COleClientItem クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleClientItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クライアント アイテムと OLE コンテナー"
  - "COleClientItem クラス"
  - "コンテナー インターフェイス クラス"
  - "OLE クライアント アイテム クラス"
  - "OLE コンテナー, クライアント アイテム"
  - "OLE コンテナー, インターフェイス クラス"
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleClientItem クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE アイテムへのコンテナー インターフェイスを定義します。  
  
## 構文  
  
```  
class COleClientItem : public CDocItem  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleClientItem::COleClientItem](../Topic/COleClientItem::COleClientItem.md)|`COleClientItem` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleClientItem::Activate](../Topic/COleClientItem::Activate.md)|操作の OLE アイテムを開き、指定した動詞を実装します。|  
|[COleClientItem::ActivateAs](../Topic/COleClientItem::ActivateAs.md)|異なる型として項目をアクティブにします。|  
|[COleClientItem::AttachDataObject](../Topic/COleClientItem::AttachDataObject.md)|OLE オブジェクトのデータにアクセスします。|  
|[COleClientItem::CanCreateFromData](../Topic/COleClientItem::CanCreateFromData.md)|コンテナー アプリケーションに埋め込みオブジェクトを作成できるかどうかを示します。|  
|[COleClientItem::CanCreateLinkFromData](../Topic/COleClientItem::CanCreateLinkFromData.md)|コンテナー アプリケーションがリンクされたオブジェクトを作成できるかどうかを示します。|  
|[COleClientItem::CanPaste](../Topic/COleClientItem::CanPaste.md)|クリップボードは embeddable または静的 OLE アイテムが含まれているかどうかを示します。|  
|[COleClientItem::CanPasteLink](../Topic/COleClientItem::CanPasteLink.md)|クリップボードは連結できる OLE アイテムが含まれているかどうかを示します。|  
|[COleClientItem::Close](../Topic/COleClientItem::Close.md)|リンクをサーバーに閉じましたりただし、OLE アイテムを破棄しません。|  
|[COleClientItem::ConvertTo](../Topic/COleClientItem::ConvertTo.md)|別の型に変換します。|  
|[COleClientItem::CopyToClipboard](../Topic/COleClientItem::CopyToClipboard.md)|OLE アイテムをクリップボードにコピーします。|  
|[COleClientItem::CreateCloneFrom](../Topic/COleClientItem::CreateCloneFrom.md)|既存の項目の複製を作成します。|  
|[COleClientItem::CreateFromClipboard](../Topic/COleClientItem::CreateFromClipboard.md)|クリップボードから埋め込みアイテムを作成します。|  
|[COleClientItem::CreateFromData](../Topic/COleClientItem::CreateFromData.md)|データ オブジェクトから埋め込みアイテムを作成します。|  
|[COleClientItem::CreateFromFile](../Topic/COleClientItem::CreateFromFile.md)|ファイルの埋め込みアイテムを作成します。|  
|[COleClientItem::CreateLinkFromClipboard](../Topic/COleClientItem::CreateLinkFromClipboard.md)|クリップボードからリンク項目を作成します。|  
|[COleClientItem::CreateLinkFromData](../Topic/COleClientItem::CreateLinkFromData.md)|データ オブジェクトからリンク項目を作成します。|  
|[COleClientItem::CreateLinkFromFile](../Topic/COleClientItem::CreateLinkFromFile.md)|ファイルからリンク項目を作成します。|  
|[COleClientItem::CreateNewItem](../Topic/COleClientItem::CreateNewItem.md)|サーバー アプリケーションを起動して新しい埋め込みアイテムを作成します。|  
|[COleClientItem::CreateStaticFromClipboard](../Topic/COleClientItem::CreateStaticFromClipboard.md)|クリップボードから静的な項目を作成します。|  
|[COleClientItem::CreateStaticFromData](../Topic/COleClientItem::CreateStaticFromData.md)|データ オブジェクトの静的な項目を作成します。|  
|[COleClientItem::Deactivate](../Topic/COleClientItem::Deactivate.md)|項目を非アクティブ化します。|  
|[COleClientItem::DeactivateUI](../Topic/COleClientItem::DeactivateUI.md)|元の状態にコンテナー アプリケーションのユーザー インターフェイスを復元します。|  
|[COleClientItem::Delete](../Topic/COleClientItem::Delete.md)|これは、リンクされた成果物 OLE アイテムを削除するか、閉じます。|  
|[COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)|ドラッグ アンド ドロップ操作を実行します。|  
|[COleClientItem::DoVerb](../Topic/COleClientItem::DoVerb.md)|指定した動詞を実装します。|  
|[COleClientItem::Draw](../Topic/COleClientItem::Draw.md)|OLE アイテムを描画します。|  
|[COleClientItem::GetActiveView](../Topic/COleClientItem::GetActiveView.md)|項目がアクティブになるビューを取得します。|  
|[COleClientItem::GetCachedExtent](../Topic/COleClientItem::GetCachedExtent.md)|OLE アイテムの四角形を返します。|  
|[COleClientItem::GetClassID](../Topic/COleClientItem::GetClassID.md)|現在の項目のクラス ID を取得します|  
|[COleClientItem::GetClipboardData](../Topic/COleClientItem::GetClipboardData.md)|クリップボードに `CopyToClipboard` のメンバー関数を呼び出すことによって設定されたデータを取得します。|  
|[COleClientItem::GetDocument](../Topic/COleClientItem::GetDocument.md)|現在の項目を含む `COleDocument` のオブジェクトを返します。|  
|[COleClientItem::GetDrawAspect](../Topic/COleClientItem::GetDrawAspect.md)|表示の項目の現在のビューを取得します。|  
|[COleClientItem::GetExtent](../Topic/COleClientItem::GetExtent.md)|OLE アイテムの四角形を返します。|  
|[COleClientItem::GetIconFromRegistry](../Topic/COleClientItem::GetIconFromRegistry.md)|Retrives 特定の CLSID のサーバーに関連付けられているアイコンへのハンドル。|  
|[COleClientItem::GetIconicMetafile](../Topic/COleClientItem::GetIconicMetafile.md)|メタファイルの項目のアイコンを描画するために使用するを取得します。|  
|[COleClientItem::GetInPlaceWindow](../Topic/COleClientItem::GetInPlaceWindow.md)|項目の埋め込み先編集ウィンドウへのポインターを返します。|  
|[COleClientItem::GetItemState](../Topic/COleClientItem::GetItemState.md)|項目の現在の状態を取得します。|  
|[COleClientItem::GetLastStatus](../Topic/COleClientItem::GetLastStatus.md)|最後の OLE 操作の状態を返します。|  
|[COleClientItem::GetLinkUpdateOptions](../Topic/COleClientItem::GetLinkUpdateOptions.md)|リンクされた成果物 \(高度な機能\) の更新モードを返します。|  
|[COleClientItem::GetType](../Topic/COleClientItem::GetType.md)|OLE アイテムの種類 \(、リンク、静的埋め込まれた\) 返します。|  
|[COleClientItem::GetUserType](../Topic/COleClientItem::GetUserType.md)|アイテムの種類を示す文字列を取得します。|  
|[COleClientItem::IsInPlaceActive](../Topic/COleClientItem::IsInPlaceActive.md)|項目が埋め込み先編集を有効 `TRUE` アクティブな場合はを返します。|  
|[COleClientItem::IsLinkUpToDate](../Topic/COleClientItem::IsLinkUpToDate.md)|リンク アイテムをソース ドキュメントと最新の場合 **\[真\]** を返します。|  
|[COleClientItem::IsModified](../Topic/COleClientItem::IsModified.md)|最後に保存されてから項目が変更された場合 `TRUE` を返します。|  
|[COleClientItem::IsOpen](../Topic/COleClientItem::IsOpen.md)|項目がサーバー アプリケーションで現在開いている `TRUE` を返します。|  
|[COleClientItem::IsRunning](../Topic/COleClientItem::IsRunning.md)|項目のサーバー アプリケーションの実行中 `TRUE` を返します。|  
|[COleClientItem::OnActivate](../Topic/COleClientItem::OnActivate.md)|アクティブ化項目を通知するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnActivateUI](../Topic/COleClientItem::OnActivateUI.md)|アクティブになり、ユーザー インターフェイスを持つ必要があること項目を通知するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnChange](../Topic/COleClientItem::OnChange.md)|サーバーが OLE アイテムを変更するときに呼び出されます。  必要な実装。|  
|[COleClientItem::OnDeactivate](../Topic/COleClientItem::OnDeactivate.md)|項目が非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDeactivateUI](../Topic/COleClientItem::OnDeactivateUI.md)|サーバーが埋め込み先編集のユーザー インターフェイスが削除されたときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnGetClipboardData](../Topic/COleClientItem::OnGetClipboardData.md)|データをクリップボードにコピーする取得するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnInsertMenus](../Topic/COleClientItem::OnInsertMenus.md)|複合のメニューを作成するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnRemoveMenus](../Topic/COleClientItem::OnRemoveMenus.md)|複合のメニューからコンテナーのメニューにするために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnSetMenu](../Topic/COleClientItem::OnSetMenu.md)|複合のメニューをインストール、削除するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnShowControlBars](../Topic/COleClientItem::OnShowControlBars.md)|コントロール バーを表示または非表示にするために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnUpdateFrameTitle](../Topic/COleClientItem::OnUpdateFrameTitle.md)|フレーム ウィンドウのタイトル バーを更新するために、フレームワークによって呼び出されます。|  
|[COleClientItem::ReactivateAndUndo](../Topic/COleClientItem::ReactivateAndUndo.md)|項目を再アクティブ化して、最後の埋め込み先編集操作を元に戻します。|  
|[COleClientItem::Release](../Topic/COleClientItem::Release.md)|開いている場合は、OLE でリンクされた成果物への接続を解放し、閉じます。  クライアント項目を破棄しません。|  
|[COleClientItem::Reload](../Topic/COleClientItem::Reload.md)|`ActivateAs`の呼び出し後に項目を再度読み込みます。|  
|[COleClientItem::Run](../Topic/COleClientItem::Run.md)|項目に関連付けられたアプリケーションを実行します。|  
|[COleClientItem::SetDrawAspect](../Topic/COleClientItem::SetDrawAspect.md)|表示の項目の現在の表示を設定します。|  
|[COleClientItem::SetExtent](../Topic/COleClientItem::SetExtent.md)|OLE アイテムの外接する四角形を設定します。|  
|[COleClientItem::SetHostNames](../Topic/COleClientItem::SetHostNames.md)|サーバーに表示される名前を設定します。OLE アイテムを編集するとき。|  
|[COleClientItem::SetIconicMetafile](../Topic/COleClientItem::SetIconicMetafile.md)|項目のアイコンを描画するために使用されたメタファイルをキャッシュします。|  
|[COleClientItem::SetItemRects](../Topic/COleClientItem::SetItemRects.md)|項目の外接する四角形を設定します。|  
|[COleClientItem::SetLinkUpdateOptions](../Topic/COleClientItem::SetLinkUpdateOptions.md)|リンクされた成果物 \(高度な機能\) の更新モードを設定します。|  
|[COleClientItem::SetPrintDevice](../Topic/COleClientItem::SetPrintDevice.md)|このクライアント項目の印刷対象デバイスを設定します。|  
|[COleClientItem::UpdateLink](../Topic/COleClientItem::UpdateLink.md)|項目の表示のキャッシュを更新します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleClientItem::CanActivate](../Topic/COleClientItem::CanActivate.md)|埋め込み先編集の有効化を許可するかどうかを判断するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnChangeItemPosition](../Topic/COleClientItem::OnChangeItemPosition.md)|項目の位置が変更されたときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDeactivateAndUndo](../Topic/COleClientItem::OnDeactivateAndUndo.md)|アクティブ化の後に元に戻すために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDiscardUndoState](../Topic/COleClientItem::OnDiscardUndoState.md)|項目を破棄するために、フレームワークによって呼び出されます。状態情報を元に戻します。|  
|[COleClientItem::OnGetClipRect](../Topic/COleClientItem::OnGetClipRect.md)|項目のクリッピング四角形を取得するために、フレームワークによって呼び出されます。調整します。|  
|[COleClientItem::OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md)|ビューに関連する項目の位置を取得するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnGetWindowContext](../Topic/COleClientItem::OnGetWindowContext.md)|項目がアクティブになるときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnScrollBy](../Topic/COleClientItem::OnScrollBy.md)|スクロールしてために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnShowItem](../Topic/COleClientItem::OnShowItem.md)|OLE アイテムを表示するために、フレームワークによって呼び出されます。|  
  
## 解説  
 OLE アイテムは、ユーザーが単一ドキュメントのようになるようにドキュメントに含まれる「」でシームレスなサーバー アプリケーションによって作成および管理されるデータを表します。  結果は OLE アイテムと含むドキュメントの作成された複合ドキュメント「」です。  
  
 OLE アイテムが埋め込まれたまたはリンクできます。  これが埋め込まれる場合、データは複合ドキュメントの一部として格納されます。  これは、リンク データは、サーバー アプリケーションで作成された個々のファイルの一部として格納され、そのファイルへのリンクのみ複合ドキュメントに格納されます。  すべての OLE アイテムは、編集するために呼び出す必要があるサーバー アプリケーションを指定する情報が含まれています。  
  
 `COleClientItem` は、サーバー アプリケーションからの要求に対して呼ばれるいくつかのオーバーライド可能な関数を定義します; これらのあるオーバーライド可能な関数は、通常、通知として機能します。  これは、ユーザーがコンテナーに変更を行うと OLE アイテムを編集する通知、または編集時に必要な情報を取得するサーバー アプリケーションができます。  
  
 `COleClientItem` は [COleDocument](../../mfc/reference/coledocument-class.md)、[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)、または [COleServerDoc](../Topic/COleServerDoc%20Class.md) のクラスで使用できます。  `COleClientItem`を使用するには、からクラスを派生し、コンテナーが行われた項目への変更に応答を定義する [OnChange](../Topic/COleClientItem::OnChange.md) のメンバー関数を実装します。  埋め込み先編集の有効化をサポートするには、[OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md) のメンバー関数をオーバーライドします。  この関数は、OLE アイテムの表示位置に関する情報を提供します。  
  
 コンテナー インターフェイスの使用方法の詳細については、" " [コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md) と [&#91;アクティブ化&#93;](../../mfc/activation-cpp.md)を参照してください。  
  
> [!NOTE]
>  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] は「オブジェクト」として埋め込まれているため、項目をリンクし、「クラスとして項目の種類を示します」。C\+\+ クラスと OLE カテゴリを区別するために対応する C\+\+ オブジェクトと OLE エンティティを識別する参照では、この用語「項目」という用語「型」。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC MFCBIND サンプル](../../top/visual-cpp-samples.md)   
 [MFC の OCLIENT サンプル](../../top/visual-cpp-samples.md)   
 [CDocItem クラス](../../mfc/reference/cdocitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)