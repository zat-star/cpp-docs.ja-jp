---
title: "CMFCRibbonCheckBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCheckBox
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCheckBox class
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
caps.latest.revision: 30
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
ms.openlocfilehash: 9efe04a8e79835b8e51b7045cb86ab2dba68b675
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox クラス
`CMFCRibbonCheckBox` クラスは、リボン パネル、クイック アクセス ツール バー、またはポップアップ メニューに追加できるチェック ボックスを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(上書き[CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize))。|  
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(上書き[CMFCRibbonButton::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize))。|  
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(上書き[CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize))。|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(`CMFCRibbonButton::IsDrawTooltipImage` をオーバーライドします)。|  
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(上書き[CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw))。|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(上書き[CMFCRibbonBaseElement::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage))。|  
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(`CMFCRibbonButton::OnDrawOnList` をオーバーライドします)。|  
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(上書き[CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata))。|  
  
## <a name="remarks"></a>コメント  
 `CMFCRibbonCheckBox` をアプリケーションで使用するには、次のコンストラクターをコードに追加します。  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
ここで、`nID` はチェック ボックスのコマンド ID を示し、`lpszText` はチェック ボックスのテキスト ラベルを示します。  
  
 チェック ボックスをリボン パネルに追加するにを使用して[CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribboncheckbox.h  
  
##  <a name="a-namecmfcribboncheckboxa--cmfcribboncheckboxcmfcribboncheckbox"></a><a name="cmfcribboncheckbox"></a>CMFCRibbonCheckBox::CMFCRibbonCheckBox  
 リボンのチェック ボックス オブジェクトのコンス トラクター  
  
```  
CMFCRibbonCheckBox(
    UINT nID,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コマンド ID を指定します  
  
 [入力] `lpszText`  
 テキスト ラベルを指定します。  
  
### <a name="return-value"></a>戻り値  
 リボンのチェック ボックス オブジェクトを構築します。  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCRibbonCheckBox`クラスです。  
  
 [!code-cpp[NVC_MFC_RibbonApp&17;](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]  
  
##  <a name="a-namegetcompactsizea--cmfcribboncheckboxgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonCheckBox::GetCompactSize  
 オーバーライドされた場合、チェック ボックスのコンパクトなサイズを取得します。  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ポインター、`CDC`チェック ボックスをオンに関連付けられています。  
  
### <a name="return-value"></a>戻り値  
 返します。、 `CSize` 、チェック ボックスのコンパクトなサイズを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 オーバーライドされていない場合は、チェック ボックスの中間のサイズを返します。  
  
##  <a name="a-namegetintermediatesizea--cmfcribboncheckboxgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonCheckBox::GetIntermediateSize  
 チェック ボックスの中間のサイズを取得します。  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ポインター、`CDC`このチェック ボックスに関連付けられています。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`チェック ボックスの中間のサイズを表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 オーバーライドされていない場合は、既定のチェック ボックスのサイズとして中間のサイズを計算 ( `AFX_CHECK_BOX_DEFAULT_SIZE`) さらに、テキストのサイズと余白。  
  
##  <a name="a-namegetregularsizea--cmfcribboncheckboxgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonCheckBox::GetRegularSize  
 チェック ボックスの標準のサイズを取得します。  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ポインター、`CDC`このチェック ボックスに関連付けられているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。、 `CSize` 、チェック ボックスの標準のサイズを格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 オーバーライドされていない場合は、チェック ボックスの中間のサイズを返します。  
  
##  <a name="a-nameisdrawtooltipimagea--cmfcribboncheckboxisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFCRibbonCheckBox::IsDrawTooltipImage  
 チェック ボックスに関連付けられているツールヒント イメージがあるかどうかを示します。  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。 `TRUE` 、チェック ボックスをオンに関連付けられているツールヒント イメージがある場合または`FALSE`かどうか。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawa--cmfcribboncheckboxondraw"></a><a name="ondraw"></a>CMFCRibbonCheckBox::OnDraw  
 指定したデバイス コンテキストを使用して、チェック ボックスを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ポインター、`CDC`チェック ボックスを描画するためのです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawmenuimagea--cmfcribboncheckboxondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMFCRibbonCheckBox::OnDrawMenuImage  
 チェック ボックスのメニュー画像を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CDC*`  
 ポインター、`CDC`チェック ボックスをオンに関連付けられています。  
  
 [入力] `CRect`  
 A `CRect`  メニューのイメージを描画する四角形を指定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`イメージが描画された場合、または`FALSE`かどうか。  
  
### <a name="remarks"></a>コメント  
 オーバーライドされていない場合に返す`FALSE`します。  
  
##  <a name="a-nameondrawonlista--cmfcribboncheckboxondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonCheckBox::OnDrawOnList  
 コマンドのリスト ボックスで、チェック ボックスを描画するためにフレームワークによって呼び出されます。  
  
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
 [入力] `pDC`  
 チェック ボックスを描画するためのデバイス コンテキストへのポインター。  
  
 [入力] `strText`  
 表示テキスト。  
  
 [入力] `nTextOffset`  
 間隔 (ピクセル単位) テキストを表示するリスト ボックスの左側にありますから。  
  
 [入力] `rect`  
 チェック ボックスを表示する四角形。  
  
 [入力] `bIsSelected`  
 `TRUE`チェック ボックスが選択されている場合、または`FALSE`かどうか。  
  
 [入力] `bHighlighted`  
 `TRUE`チェック ボックスが強調表示されている場合、または`FALSE`かどうか。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetaccdataa--cmfcribboncheckboxsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonCheckBox::SetACCData  
 チェック ボックスのユーザー補助データを設定します。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParent`  
 チェック ボックスの親ウィンドウです。  
  
 `data`  
 チェック ボックスのユーザー補助データ。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 既定ではこのメソッドを設定、チェック ボックスをオンにし、常にユーザー補助データを返します。`TRUE`します。 アクセシビリティ データを設定し、成功または失敗を示す値を返すようにするには、このメソッドをオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel クラス](../../mfc/reference/cmfcribbonpanel-class.md)

