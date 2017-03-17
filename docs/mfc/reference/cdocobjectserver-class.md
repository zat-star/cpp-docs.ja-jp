---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
dev_langs:
- C++
helpviewer_keywords:
- document object server
- CDocObjectServer class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 75fb0ba49d105a673e862ed3044e85ac9e990e9c
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserver-class"></a>関数のクラス
標準の `COleDocument` サーバーを完全な DocObject サーバーにするために必要な、 `IOleDocument`、 `IOleDocumentView`、 `IOleCommandTarget`、 `IPrint`などの追加 OLE インターフェイスを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|`CDocObjectServer` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|オブジェクトのドキュメントのサーバーがアクティブになりますが、表示されません。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|DocObject ビューを表示します。|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|DocObject ビューの状態に戻します。|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|DocObject ビューの状態を保存します。|  
  
## <a name="remarks"></a>コメント  
 `CDocObjectServer`派生した`CCmdTarget`と密接に連携し、`COleServerDoc`インターフェイスが公開します。  
  
 DocObject サーバー ドキュメントを含めることができます[CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) DocObject 項目へのサーバー インターフェイスを表すオブジェクト。  
  
 DocObject サーバーをカスタマイズするからクラスを派生`CDocObjectServer`とそのビュー セットアップ関数をオーバーライド[OnActivateView](#onactivateview)、 [OnApplyViewState](#onapplyviewstate)、および[OnSaveViewState](#onsaveviewstate)します。 Framework 呼び出しに応答クラスの新しいインスタンスを提供する必要があります。  
  
 DocObjects については、次を参照してください。 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)と[COleCmdUI](../../mfc/reference/colecmdui-class.md)で、 *『 MFC リファレンス*します。 参照してください[インターネットの最初の手順: アクティブなドキュメント](../../mfc/active-documents-on-the-internet.md)と[アクティブ ドキュメント](../../mfc/active-documents-on-the-internet.md)します。  
  
 また、次のサポート技術情報の記事を参照してください。  
  
-   Q247382: PRB: ActiveX ドキュメント コンテナーで ActiveX ドキュメント サーバーでのコントロールのツールヒントに表示されません  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdocob.h  
  
##  <a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject  
 この関数をドキュメント オブジェクト サーバーをアクティブ化 (は表示されません)。  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>コメント  
 `ActivateDocObject`呼び出し`IOleDocumentSite`の**ActivateMe**メソッドを設定およびへの呼び出しで指定されたビューを表示する方法についての特定の待機しているため、ビューを表示しない[CDocObjectServer::OnActivateView](#onactivateview)します。  
  
 同時に、`ActivateDocObject`と`OnActivateView`をアクティブ化し、DocObject ビューを表示します。 その他の OLE 埋め込み DocObject アクティブ化とは異なります。 DocObject アクティベーション インプレース点線の枠と (サイズ変更ハンドル) などのオブジェクトの表示要素を省略するには、オブジェクトの拡張機能、および (通常、インプレース アクティブ化) と同様に、その四角形の外側に描画するのではなく四角形の表示内のスクロール バーを描画します。  
  
##  <a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer  
 `CDocObjectServer` オブジェクトを構築して初期化します。  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pOwner*  
 DocObject サーバー用のクライアントは、クライアント サイトのドキュメントへのポインター。  
  
 `pDocSite`  
 ポインター、`IOleDocumentSite`コンテナーによって実装されるインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 クライアント サイト OLE インターフェイスの DocObject がアクティブである場合 ( `IOleDocumentSite`) は DocObject サーバーがクライアント (コンテナー) と通信することができます。 DocObject サーバーがアクティブになることはまず、コンテナーによって実装されている、`IOleDocumentSite`インターフェイスです。 必要な場合は、 [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver)コンテナー DocObjects でサポートされているかどうかに呼び出されます。 既定では、`GetDocObjectServer`返します**NULL**します。 オーバーライドする必要があります`COleServerDoc::GetDocObjectServer`新しいを作成する`CDocObjectServer`オブジェクトまたはへのポインターを使用して独自の派生オブジェクト、`COleServerDoc`コンテナーとその`IOleDocumentSite`コンス トラクターへの引数としてインターフェイスです。  
  
##  <a name="onactivateview"></a>CDocObjectServer::OnActivateView  
 DocObject ビューを表示するには、この関数を呼び出します。  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>戻り値  
 エラーまたは警告の値を返します。 既定では、次のように返されます。 **NOERROR**成功した場合は、 **E_FAIL**します。  
  
### <a name="remarks"></a>コメント  
 この関数で埋め込み先フレーム ウィンドウを作成するには、ビュー内のスクロール バーの描画、サーバー コンテナーが共有、フレーム コントロールの追加、アクティブなオブジェクトを設定し、最後に埋め込み先フレーム ウィンドウを示していますおよびフォーカスを設定メニューを設定します。  
  
##  <a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState  
 DocObject ビューの状態を復元するには、この関数をオーバーライドします。  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`ビュー ステートをシリアル化するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初に、インスタンス化した後、ビューが表示されるときに、この関数が呼び出されます。 `OnApplyViewState`データに基づいて再初期化するためのビューに指示、`CArchive`以前に保存されているオブジェクト[OnSaveViewState](#onsaveviewstate)します。 ビューのデータを検証する必要があります、`CArchive`オブジェクトをコンテナーは任意の方法で、ビュー ステートのデータを解釈しようとはしません。  
  
 使用する`OnSaveViewState`ビューの状態を永続的な情報を格納します。 オーバーライドする場合は`OnSaveViewState`情報を格納するにはオーバーライドする`OnApplyViewState`情報を読み取り、新しくアクティブになったときに、ビューに適用します。  
  
##  <a name="onsaveviewstate"></a>CDocObjectServer::OnSaveViewState  
 DocObject ビューに関する特別な状態情報を保存するには、この関数をオーバーライドします。  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`ビュー ステートがシリアル化するオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 状態には、ビューの種類、ズームの倍率を挿入し、選択ポイントなどのプロパティが含まれます。 コンテナーは、通常、ビューを非アクティブ化する前にこの関数を呼び出します。 保存済みの状態はによって後で復元しなければ[OnApplyViewState](#onapplyviewstate)します。  
  
 使用する`OnSaveViewState`ビューの状態を永続的な情報を格納します。 オーバーライドする場合は`OnSaveViewState`情報を格納するにはオーバーライドする`OnApplyViewState`情報を読み取り、新しくアクティブになったときに、ビューに適用します。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem クラス](../../mfc/reference/cdocobjectserveritem-class.md)

