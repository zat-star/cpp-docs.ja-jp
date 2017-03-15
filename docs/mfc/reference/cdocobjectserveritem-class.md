---
title: "CDocObjectServerItem クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
dev_langs:
- C++
helpviewer_keywords:
- document object server
- CDocObjectServerItem class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 06cf873512fbf43b729d9a70f185582a4e48cafc
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem クラス
OLE サーバー動詞を DocObject サーバー用に実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|`CDocObjectServerItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|項目を含むドキュメントへのポインターを取得します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|フレームワーク DocObject アイテムを非表示にしようとする場合は、例外をスローします。|  
|[CDocObjectServerItem::OnShow](#onshow)|DocObject アイテムの埋め込みを行うために、フレームワークによって呼び出されるアクティブです。 項目がない場合、DocObject、呼び出します[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)します。|  
  
## <a name="remarks"></a>コメント  
 `CDocObjectServerItem`オーバーライド可能なメンバー関数を定義します。 [OnHide](#onhide)、 [OnOpen](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd)、および[OnShow](#onshow)します。  
  
 使用する`CDocObjectServerItem`、されるようにする、 [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)でオーバーライド、 `COleServerDoc`-派生クラスの新しい返します`CDocObjectServerItem`オブジェクトです。 機能で、項目を変更する必要がある場合は、独自の新しいインスタンスを作成できます`CDocObjectServerItem`-クラスを派生します。  
  
 DocObjects については、次を参照してください。[関数](../../mfc/reference/cdocobjectserver-class.md)と[COleCmdUI](../../mfc/reference/colecmdui-class.md)で、 *『 MFC リファレンス*します。 参照してください[インターネットの最初の手順: アクティブなドキュメント](../../mfc/active-documents-on-the-internet.md)と[アクティブ ドキュメント](../../mfc/active-documents-on-the-internet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [実際](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdocob.h  
  
##  <a name="a-namecdocobjectserveritema--cdocobjectserveritemcdocobjectserveritem"></a><a name="cdocobjectserveritem"></a>CDocObjectServerItem::CDocObjectServerItem  
 `CDocObjectServerItem` オブジェクトを構築します。  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 `pServerDoc`  
 新しい DocObject アイテムを格納するドキュメントへのポインター。  
  
 `bAutoDelete`  
 リンクがリリースされたときに、オブジェクトを削除するかどうかを示します。 引数に設定します**FALSE**場合、`CDocObjectServerItem`オブジェクトは、ドキュメントのデータに不可欠な要素です。 設定**TRUE**オブジェクトが、ドキュメントのデータを削除するには、フレームワークを内の範囲を識別するために使用されるセカンダリ構造体である場合。  
  
##  <a name="a-namegetdocumenta--cdocobjectserveritemgetdocument"></a><a name="getdocument"></a>CDocObjectServerItem::GetDocument  
 項目を含むドキュメントへのポインターを取得します。  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アイテムを保持するドキュメントへのポインター**NULL**場合は、項目は、ドキュメントの一部ではありません。  
  
### <a name="remarks"></a>コメント  
 これは、引数として渡された server ドキュメントへのアクセス、 [CDocObjectServerItem](#cdocobjectserveritem)コンス トラクターです。  
  
##  <a name="a-nameonhidea--cdocobjectserveritemonhide"></a><a name="onhide"></a>CDocObjectServerItem::OnHide  
 アイテムを非表示にするために、フレームワークによって呼び出されます。  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装では、項目が DocObject は例外をスローします。 ビュー全体を受け取るのでは、アクティブな DocObject アイテムを非表示にすることはできません。 非表示にする DocObject アイテムを非アクティブ化する必要があります。 アイテムが DocObject でない場合は、既定の実装を呼び出す[COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide)します。  
  
##  <a name="a-nameonshowa--cdocobjectserveritemonshow"></a><a name="onshow"></a>CDocObjectServerItem::OnShow  
 サーバー アプリケーションは、アイテムの埋め込みを DocObject に実行を指示するために、フレームワークによって呼び出されますアクティブです。  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>コメント  
 アイテムが DocObject でない場合は、既定の実装を呼び出す[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen)します。 特別な DocObject アイテムを開くときの処理を実行する場合は、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [実際のクラス](../../mfc/reference/coleserveritem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cdocobjectserver-class.md)   
 [関数のクラス](../../mfc/reference/coledocobjectitem-class.md)

