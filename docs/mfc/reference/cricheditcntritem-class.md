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
- CRichEditCntrItem
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem class
- OLE items, in rich edit views
- rich edit controls, using
- rich edit controls, OLE items
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
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
ms.openlocfilehash: b29c7c3b80d24ef9ddb94e09c6b5c7bf2444bb4f
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditcntritem-class"></a>関数のクラス
[CRichEditView](../../mfc/reference/cricheditview-class.md)と[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)MFC のドキュメント ビュー アーキテクチャのコンテキスト内でのリッチ エディット コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|`CRichEditCntrItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|別の種類としては、アイテムをアクティブになります。|  
  
## <a name="remarks"></a>コメント  
 「リッチ エディット コントロール」は、ウィンドウで、ユーザーは入力し、テキストの編集です。 テキストは、文字および段落の書式設定に割り当てることができるし、OLE 埋め込みオブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストを書式設定するためのプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーが使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView`テキストとテキストの書式設定特性を保持します。 `CRichEditDoc`ビューに含まれる OLE クライアント アイテムの一覧を保持します。 `CRichEditCntrItem`コンテナー側 OLE クライアント アイテムへのアクセスを提供します。  
  
 この Windows コモン コントロール (つまり、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)および関連クラス) は以降 Windows 95/98 および Windows NT version 3.51 の下で実行されているプログラムにのみ使用できます。  
  
 リッチ エディット コンテナー アイテムを使用して MFC アプリケーションでの例は、次を参照してください。、[ワードパッド](../../visual-cpp-samples.md)サンプル アプリケーションです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrich.h  
  
##  <a name="a-namecricheditcntritema--cricheditcntritemcricheditcntritem"></a><a name="cricheditcntritem"></a>CRichEditCntrItem::CRichEditCntrItem  
 作成するには、この関数を呼び出して、`CRichEditCntrItem`オブジェクトをコンテナー ドキュメントに追加します。  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *preo*  
 ポインター、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE アイテムを記述する構造体。 新しい`CRichEditCntrItem`この OLE アイテム オブジェクトを構築します。 場合*preo*は**NULL**クライアントのアイテムは空にします。  
  
 `pContainer`  
 この項目を格納するコンテナー ドキュメントへのポインター。 場合`pContainer`は**NULL**、明示的に呼び出す必要があります[COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem)ドキュメントにこのクライアント アイテムを追加します。  
  
### <a name="remarks"></a>コメント  
 この関数では、OLE の初期化は実行されません。  
  
 詳細については、次を参照してください。、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesynctoricheditobjecta--cricheditcntritemsynctoricheditobject"></a><a name="synctoricheditobject"></a>CRichEditCntrItem::SyncToRichEditObject  
 デバイスの側面を同期するには、この関数を呼び出す[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)、この**CRichEditCntrltem**によって指定される*reo*します。  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>パラメーター  
 *reo*  
 参照、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE アイテムを記述する構造体。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [ワードパッドの MFC サンプル](../../visual-cpp-samples.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)

