---
title: "CRichEditDoc クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- document/view architecture, rich edit controls
- OLE containers, rich edit
- documents, rich edit
- rich edit controls, OLE container
- CRichEditDoc class
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7233c27c92c6dc689853e1913bb26f0bb5941fa
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditdoc-class"></a>CRichEditDoc クラス
[CRichEditView](../../mfc/reference/cricheditview-class.md)と[関数](../../mfc/reference/cricheditcntritem-class.md)MFC のドキュメント ビュー アーキテクチャのコンテキスト内でのリッチ エディット コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|ドキュメントのクリーンアップを実行するには、呼び出されます。|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|ストリーム入力と出力が書式設定情報を含めるかどうかを示します。|  
|[CRichEditDoc::GetView](#getview)|取得、関連付けられている[CRichEditView](../../mfc/reference/cricheditview-class.md)オブジェクトです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditDoc::m_bRTF](#m_brtf)|ストリーム入出力が書式設定を含めるかどうかを示します。|  
  
## <a name="remarks"></a>コメント  
 「リッチ エディット コントロール」は、ウィンドウで、ユーザーは入力し、テキストの編集です。 テキストは、文字および段落の書式設定に割り当てることができるし、OLE 埋め込みオブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストを書式設定するためのプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーが使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView`テキストとテキストの書式設定特性を保持します。 `CRichEditDoc`ビューに含まれるクライアント アイテムの一覧を保持します。 `CRichEditCntrItem`コンテナー側 OLE クライアント アイテムへのアクセスを提供します。  
  
 この Windows コモン コントロール (つまり、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)および関連クラス) は以降 Windows 95/98 および Windows NT version 3.51 の下で実行されているプログラムにのみ使用できます。  
  
 リッチ エディット ドキュメントを使用して MFC アプリケーションでの例は、次を参照してください。、[ワードパッド](../../visual-cpp-samples.md)サンプル アプリケーションです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [直接](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrich.h  
  
##  <a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 作成するには、この関数を呼び出して、`CRichEditCntrItem`オブジェクトし、このドキュメントに追加します。  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *preo*  
 ポインター、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE アイテムを記述する構造体。 新しい`CRichEditCntrItem`この OLE アイテム オブジェクトを構築します。 場合*preo*は**NULL**、新しい項目のクライアントが空です。  
  
### <a name="return-value"></a>戻り値  
 新しいへのポインター[関数](../../mfc/reference/cricheditcntritem-class.md)このドキュメントに追加されたオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数では、OLE の初期化は実行されません。  
  
 詳細については、次を参照してください。、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 この関数では、豊富な編集のコンテンツをストリーミング用のテキスト形式を決定します。  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 次のフラグのいずれかです。  
  
- `SF_TEXT`リッチ エディット コントロールの書式情報を保持しないことを示します。  
  
- `SF_RTF`リッチ エディット コントロールでの書式情報は保持することを示します。  
  
### <a name="remarks"></a>コメント  
 戻り値がに基づいて、 [m_bRTF](#m_brtf)データ メンバーです。 この関数を返します`SF_RTF`場合`m_bRTF`は**TRUE**。 そうしないと、`SF_TEXT`です。  
  
##  <a name="getview"></a>CRichEditDoc::GetView  
 アクセスするには、この関数を呼び出して、 [CRichEditView](../../mfc/reference/cricheditview-class.md)オブジェクトに関連付けられた`CRichEditDoc`オブジェクトです。  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CRichEditView`ドキュメントに関連付けられているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 テキストと書式情報に含まれる、`CRichEditView`オブジェクトです。 `CRichEditDoc`オブジェクトはシリアル化のための OLE アイテムを保持します。 1 つだけあります`CRichEditView`各`CRichEditDoc`します。  
  
##  <a name="m_brtf"></a>CRichEditDoc::m_bRTF  
 **TRUE**、ことを示します[CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin)と[CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout)段落と文字の書式設定特性を格納する必要があります。  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>関連項目  
 [ワードパッドの MFC サンプル](../../visual-cpp-samples.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)   
 [関数のクラス](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl クラス](../../mfc/reference/cricheditctrl-class.md)

