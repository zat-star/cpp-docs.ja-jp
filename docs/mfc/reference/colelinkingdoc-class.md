---
title: "直接クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinkingDoc
dev_langs:
- C++
helpviewer_keywords:
- OLE containers, client items
- COleLinkingDoc class
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: 24
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
ms.openlocfilehash: acdfde1413d5ff93efc63dbbf211881f71cf624e
ms.lasthandoff: 02/24/2017

---
# <a name="colelinkingdoc-class"></a>直接クラス
OLE コンテナー ドキュメントの基底クラスです。OLE コンテナー ドキュメントは、ドキュメントが保持する埋め込みアイテムへのリンクをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|`COleLinkingDoc` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|OLE システム Dll をドキュメントを登録します。|  
|[COleLinkingDoc::Revoke](#revoke)|ドキュメントの登録を取り消します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|指定した埋め込みアイテムを検索します。|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|指定したリンク アイテムを検索します。|  
  
## <a name="remarks"></a>コメント  
 埋め込みアイテムへのリンクをサポートしているコンテナー アプリケーションは「リンク コンテナー」と呼ばれる [OCLIENT](../../visual-cpp-samples.md)サンプル アプリケーションは、リンクのコンテナーの例を示します。  
  
 リンクされた項目のソースが別のドキュメントに埋め込まれたアイテムの場合は、そのを含むドキュメントを編集しようとする埋め込みアイテムの順序で読み込む必要があります。 このため、リンクのコンテナーは、ユーザーがリンクされた項目のソースを編集するときに別のコンテナー アプリケーションを起動できる必要があります。 アプリケーションを使用する必要がありますも、[関数](../../mfc/reference/coletemplateserver-class.md)クラスのプログラムを使用して起動したときにドキュメントを作成できるようにします。  
  
 リンク コンテナーするために、コンテナーからドキュメント クラスを派生させる`COleLinkingDoc`の代わりに[COleDocument](../../mfc/reference/coledocument-class.md)します。 その他の OLE コンテナーと同様、アプリケーションのネイティブ データだけでなく埋め込みまたはリンクされた項目を格納するため、クラスを設計する必要があります。 また、ネイティブのデータを格納するためのデータ構造を設計する必要があります。 定義する場合、`CDocItem`の派生クラスをアプリケーションのネイティブ データによって定義されたインターフェイスを使用して`COleDocument`OLE データや、ネイティブ データの保存にします。  
  
 別のコンテナーでプログラムを使用して起動されるようにアプリケーションを許可するように宣言、`COleTemplateServer`のアプリケーションのメンバーとしてオブジェクト`CWinApp`-クラスを派生します。  
  
 [!code-cpp[NVC_MFCOleContainer 第&23;](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 `InitInstance`のメンバー関数、 `CWinApp`-派生クラスでは、ドキュメント テンプレートを作成し、指定、 `COleLinkingDoc`-ドキュメント クラスとクラスを派生します。  
  
 [!code-cpp[NVC_MFCOleContainer #&24;](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 接続、`COleTemplateServer`オブジェクト、オブジェクトを呼び出すことによって、ドキュメント テンプレートを`ConnectTemplate`メンバー関数とレジスタを呼び出して OLE システム オブジェクトをすべてクラス**COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer&#25;](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 サンプルについては`CWinApp`-派生したクラスの定義と`InitInstance`関数の OCLIENT を参照してください。H および OCLIENT します。MFC のサンプルでは CPP [OCLIENT](../../visual-cpp-samples.md)します。  
  
 使用する方法について`COleLinkingDoc`、記事を参照して[コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md)と[コンテナー: 高度な機能](../../mfc/containers-advanced-features.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-namecolelinkingdoca--colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a>COleLinkingDoc::COleLinkingDoc  
 構築、 `COleLinkingDoc` OLE システム Dll との通信を開始せずオブジェクトです。  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります、 `Register` OLE ドキュメントが開いていることを通知するメンバー関数。  
  
##  <a name="a-nameonfindembeddeditema--colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a>COleLinkingDoc::OnFindEmbeddedItem  
 ドキュメントに指定された名前で埋め込み OLE アイテムが含まれるかどうかを確認するためにフレームワークによって呼び出されます。  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszItemName`  
 埋め込み OLE アイテムの名前へのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定した項目へのポインター**NULL**場合は、項目は見つかっていません。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、指定した名前 (名前の比較では大文字小文字を区別) を持つ項目の埋め込みアイテムの一覧を検索します。 埋め込み OLE アイテムの名前を付ける格納方法や、独自のメソッドがある場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameongetlinkeditema--colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a>COleLinkingDoc::OnGetLinkedItem  
 ドキュメントに指定した名前のリンク サーバーの項目が含まれているかどうか確認するためにフレームワークによって呼び出されます。  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszItemName`  
 リンクされている OLE アイテムの名前へのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定した項目へのポインター**NULL**場合は、項目は見つかっていません。  
  
### <a name="remarks"></a>コメント  
 既定値`COleLinkingDoc`実装は常に返します**NULL**します。 この関数は、派生クラスでオーバーライドされる`COleServerDoc`(名前の比較では大文字小文字を区別) 指定した名前のリンクされた項目を OLE サーバー アイテムのリストを検索します。 リンク サーバーのアイテムを取得する格納方法や、独自のメソッドを実装している場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameregistera--colelinkingdocregister"></a><a name="register"></a>COleLinkingDoc::Register  
 ドキュメントが開かれている OLE システム Dll を通知します。  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFactory*  
 OLE ファクトリ オブジェクトへのポインター (できます**NULL**)。  
  
 `lpszPathName`  
 コンテナー ドキュメントの完全修飾パスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ドキュメントが正常に登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 作成または OLE システム Dll にドキュメントを登録する名前付きのファイルを開くときは、この関数を呼び出します。 ドキュメントが埋め込まれたアイテムを表している場合は、この関数を呼び出す必要はありません。  
  
 使用している場合`COleTemplateServer`、アプリケーションで`Register`によって呼び出されます`COleLinkingDoc`の実装の`OnNewDocument`、 `OnOpenDocument`、および`OnSaveDocument`です。  
  
##  <a name="a-namerevokea--colelinkingdocrevoke"></a><a name="revoke"></a>COleLinkingDoc::Revoke  
 OLE システム Dll にドキュメントが開いていないことが通知されます。  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>コメント  
 OLE システム Dll にドキュメントの登録を取り消すには、この関数を呼び出します。  
  
 名前付きのファイルを閉じるときに、この関数を呼び出す必要がありますが、する通常必要はありませんメソッドを直接呼び出す。 `Revoke`によって呼び出されます`COleLinkingDoc`の実装の`OnCloseDocument`、 `OnNewDocument`、 `OnOpenDocument`、および`OnSaveDocument`です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)

