---
title: "CMFCRibbonSeparator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator class
- GetThisClass method
- CreateObject method
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
caps.latest.revision: 21
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
ms.openlocfilehash: 98a58d43b5e6299f26521d873caec06d4581f7b3
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator クラス
リボンの区分線を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|`CMFCRibbonSeparator` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|区分線を追加、**コマンド**リストに、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox))。|  
|`CMFCRibbonSeparator::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonSeparator::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|別のオブジェクトから区切り記号のメンバー変数を設定するコピー メソッド。|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|区切り記号のサイズを返します。|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|これが、区切り記号であるかどうかを示します。|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|タブ ストップであるかどうかを示します。|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|リボンまたはクイック アクセス ツールバーに区分線を描画する、システムによって呼び出されます。|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|区分線を描画する、システムによって呼び出さ、**コマンド** ボックスの一覧です。|  
  
## <a name="remarks"></a>コメント  
 リボンの区分線は、水平または垂直の行を論理的に分離リボン要素です。 リボン コントロール、アプリケーションのメイン メニューのリボン ステータス バー、およびクイック アクセス ツールバーに区分線を描画できます。  
  
 アプリケーションで、区切り記号を使用するには、新しいオブジェクトを構築し、次のように、アプリケーションのメイン メニューに追加します。  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
呼び出す[CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator)リボン パネルに区切り記号を追加します。 区切り記号が割り当てられ、内部で追加、`AddSeparator`メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxbaseribbonelement.h  
  
##  <a name="addtolistbox"></a>CMFCRibbonSeparator::AddToListBox  
 区分線を追加、**コマンド**リストに、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndListBox`  
 ポインター、**コマンド**区切り記号が追加された一覧です。  
  
 [入力] `bDeep`  
 無視されます。  
  
### <a name="return-value"></a>戻り値  
 0 から始まるインデックスで指定されたリスト ボックス内の文字列に`pWndListBox`します。  
  
##  <a name="cmfcribbonseparator"></a>CMFCRibbonSeparator::CMFCRibbonSeparator  
 `CMFCRibbonSeparator` オブジェクトを構築します。  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsHoriz`  
 場合`TRUE`、区切り記号は水平方向場合`FALSE`、区切り文字は垂直に表示します。  
  
### <a name="remarks"></a>コメント  
 水平方向の区切り記号は、アプリケーションのメニューで使用されます。 垂直方向の区切り記号は、ツールバーで使用されます。  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCRibbonSeparator`クラスです。  
  
 [!code-cpp[NVC_MFC_RibbonApp&#19;](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="copyfrom"></a>CMFCRibbonSeparator::CopyFrom  
 別のオブジェクトから区切り記号のメンバー変数を設定するコピー メソッド。  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `Src`  
 コピー元ソース リボン要素。  
  
##  <a name="getregularsize"></a>CMFCRibbonSeparator::GetRegularSize  
 区切り記号のサイズを返します。  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイスのコンテンツへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定したデバイス コンテキストで区切り記号のサイズ。  
  
##  <a name="isseparator"></a>CMFCRibbonSeparator::IsSeparator  
 これが、区切り記号であるかどうかを示します。  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に`TRUE`このクラスにします。  
  
##  <a name="istabstop"></a>CMFCRibbonSeparator::IsTabStop  
 タブ ストップであるかどうかを示します。  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に`FALSE`このクラスにします。  
  
### <a name="remarks"></a>コメント  
 リボンの区切り記号は、タブ ストップではありません。  
  
##  <a name="ondraw"></a>CMFCRibbonSeparator::OnDraw  
 リボンまたはクイック アクセス ツールバーに区分線を描画する、システムによって呼び出されます。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
##  <a name="ondrawonlist"></a>CMFCRibbonSeparator::OnDrawOnList  
 区分線を描画する、システムによって呼び出さ、**コマンド** ボックスの一覧です。  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDC`|デバイス コンテキストへのポインター。|  
|[入力] `strText`|一覧に表示されるテキスト。|  
|[入力] `nTextOffset`|テキストと外接する四角形の左端の間の間隔。|  
|[入力] `rect`|外接する四角形を指定します。|  
|[入力] `bIsSelected`|無視されます。|  
|[入力] `bHighlighted`|無視されます。|  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

