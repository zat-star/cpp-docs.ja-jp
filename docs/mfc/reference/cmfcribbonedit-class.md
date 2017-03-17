---
title: "CMFCRibbonEdit クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonEdit class
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
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
ms.openlocfilehash: 03eb96bf971b53a2100e6f93bac2f0641f0298e1
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit クラス
リボン バーに配置されるエディット コントロールを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|示すかどうかの高さ、`CMFCRibbonEdit`コントロールは、リボンの行の高さを縦に拡大できます。|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` オブジェクトを構築します。|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|指定した状態をコピー`CMFCRibbonEdit`現在オブジェクト`CMFCRibbonEdit`オブジェクトです。|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|新しいテキスト ボックスを作成、`CMFCRibbonEdit`オブジェクトです。|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|`CMFCRibbonEdit` オブジェクトを破棄します。|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|リスト ボックスの一覧を削除します。|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|有効にし、テキスト ボックスのスピン ボタンの範囲を設定します。|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|コンパクトなサイズを取得、`CFMCRibbonEdit`オブジェクトです。|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|テキスト ボックス内のテキストを取得します。|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|中間のサイズを取得、`CMFCRibbonEdit`オブジェクトです。|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|テキスト ボックス内のテキストの配置を取得します。|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|幅 (ピクセル単位) を取得、`CMFCRibbonEdit`コントロールです。|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|示しますのサイズを表示するかどうか、`CMFCRibbonEdit`コントロールをコンパクトにすることができます。|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|示すかどうか、`CMFCRIbbonEdit`コントロールにフォーカスがあります。|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|示しますのサイズを表示するかどうか、`CMFCRibbonEdit`コントロールが大きくなることができます。|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|スピン ボタンがテキスト ボックスにあるかどうかを示します。|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|示すかどうか、`CMFCRibbonEdit`コントロールを強調表示します。|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|フレームワークによって呼び出されますときに表示する四角形のサイズ、`CMFCRibbonEdit`コントロールの変更。|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|描画するフレームワークによって呼び出され、`CMFCRibbonEdit`コントロールです。|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|イメージのラベルを描画およびフレームワークによって呼び出され、`CMFCRibbonEdit`コントロールです。|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|描画するためにフレームワークによって呼び出される、`CMFCRibbonEdit`コマンドのリスト ボックス内のコントロールです。|  
|[CMFCRibbonEdit::OnEnable](#onenable)|有効または無効にするフレームワークによって呼び出され、`CMFCRibbonEdit`コントロールです。|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|ポインターか、またはの境界から出たときに、フレームワークによって呼び出されます、`CMFCRibbonEdit`コントロールです。|  
|[CMFCRibbonEdit::OnKey](#onkey)|Keytip を押したときに、フレームワークによって呼び出され、`CMFCRibbonEdit`コントロールにフォーカスがあります。|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|更新するためにフレームワークによって呼び出される、`CMFCRibbonEdit`ユーザーがコントロールにマウスの左ボタンを押したときを制御します。|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|マウスの左ボタンを離したときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|更新するためにフレームワークによって呼び出される、`CMFCRibbonEdit`レイアウトの方向変更されたときを制御します。|  
|[CMFCRibbonEdit::OnShow](#onshow)|表示/非表示にフレームワークによって呼び出され、`CMFCRibbonEdit`コントロールです。|  
|[CMFCRibbonEdit::Redraw](#redraw)|表示を更新、`CMFCRibbonEdit`コントロールです。|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|ユーザー補助データを設定、`CMFCRibbonEdit`オブジェクトです。|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|テキスト ボックスにテキストを設定します。|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|テキスト ボックスのテキストの配置を設定します。|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|テキスト ボックスの幅を設定、`CMFCRibbonEdit`コントロールです。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="example"></a>例  
 次の例では、構築、`CMFCRibbonEdit`オブジェクト、エディット コントロールの横にあるスピン ボタンの表示および編集コントロールのテキストを設定します。 このコード スニペットの一部である、 [MS Office 2007 デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#7;](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>CMFCRibbonEdit::CanBeStretched  
 示すかどうかの高さ、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールは、リボンの行の高さを縦に拡大できます。  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cmfcribbonedit"></a>CMFCRibbonEdit::CMFCRibbonEdit  
 構築、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトです。  
  
```  
CMFCRibbonEdit(
    UINT nID,  
    int nWidth,  
    LPCTSTR lpszLabel = NULL,  
    int nImage = -1);

CMFCRibbonEdit();
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コマンドの ID、`CMFCRibbonEdit`コントロールです。  
  
 [入力] `nWidth`  
 幅 (ピクセル単位) のテキスト ボックス、`CMFCRibbonEdit`コントロールです。  
  
 [入力] `lpszLabel`  
 ラベル、`CMFCRibbonEdit`コントロールです。  
  
 [入力] `nImage`  
 小さいイメージのインデックス番号を使用する、`CMFCRibbonEdit`コントロールです。 小さいイメージのコレクションは、親のリボン カテゴリによって管理されます。  
  
### <a name="remarks"></a>コメント  
 `CMFCRibbonEdit`コントロールは大きなイメージを使用していません。  
  
##  <a name="copyfrom"></a>CMFCRibbonEdit::CopyFrom  
 指定した状態をコピー [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)現在オブジェクト[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトです。  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 ソース `CMFCRibbonEdit` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `src`パラメーターは、型でなければなりません`CMFCRibbonEdit`します。  
  
##  <a name="createedit"></a>CMFCRibbonEdit::CreateEdit  
 新しいテキスト ボックスを作成、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトです。  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウへのポインター、`CMFCRibbonEdit`オブジェクトです。  
  
 [入力] `dwEditStyle`  
 テキスト ボックスのスタイルを指定します。 「解説」セクションに示されているウィンドウ スタイルを組み合わせることができます、[コントロールのスタイルを編集](http://msdn.microsoft.com/library/windows/desktop/bb775464)Windows sdk に記載されていますいます。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、新しいテキスト ボックスへのポインターそれ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>コメント  
 カスタムのテキスト ボックスを作成する派生クラスでは、このメソッドをオーバーライドします。  
  
 次を適用する[ウィンドウ スタイル](../../mfc/reference/window-styles.md)テキスト ボックスにします。  
  
- **WS_CHILD**  
  
- **WS_VISIBLE**  
  
- **WS_DISABLED**  
  
- **WS_GROUP**  
  
- **WS_TABSTOP**  
  
##  <a name="destroyctrl"></a>CMFCRibbonEdit::DestroyCtrl  
 破棄、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトです。  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dropdownlist"></a>CMFCRibbonEdit::DropDownList  
 リスト ボックスの一覧を削除します。  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは何もしません。 ドロップダウン リスト ボックスには、このメソッドをオーバーライドします。  
  
##  <a name="enablespinbuttons"></a>CMFCRibbonEdit::EnableSpinButtons  
 有効にし、テキスト ボックスのスピン ボタンの範囲を設定します。  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMin`  
 スピン ボタンの最小値。  
  
 [入力] `nMax`  
 スピン ボタンの最大値。  
  
### <a name="remarks"></a>コメント  
 スピン ボタンは、表示し、下矢印をクリックと、値の固定セット間を移動できます。  
  
##  <a name="getcompactsize"></a>CMFCRibbonEdit::GetCompactSize  
 コンパクトなサイズを取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトです。  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 Compact のサイズ、`CMFCRibbonEdit`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getedittext"></a>CMFCRibbonEdit::GetEditText  
 テキスト ボックス内のテキストを取得します。  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 テキスト ボックス内のテキスト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getintermediatesize"></a>CMFCRibbonEdit::GetIntermediateSize  
 中間のサイズを取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトです。  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 中間のサイズ、`CMFCRibbonEdit`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettextalign"></a>CMFCRibbonEdit::GetTextAlign  
 テキスト ボックス内のテキストの配置を取得します。  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>戻り値  
 テキストの配置の列挙値。 指定できる値については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 返される値は、次の編集コントロールのスタイルのいずれかです。  
  
- **ES_LEFT**左詰め  
  
- **ES_CENTER**の中央揃え  
  
- **ES_RIGHT**右揃え  
  
 これらのスタイルの詳細については、次を参照してください。[コントロールのスタイルの編集](http://msdn.microsoft.com/library/windows/desktop/bb775464)します。  
  
##  <a name="getwidth"></a>CMFCRibbonEdit::GetWidth  
 幅 (ピクセル単位) を取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールです。  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bInFloatyMode`  
 `TRUE`場合、`CMFCRibbonEdit`コントロールがフローティング モードです。 それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 幅 (ピクセル単位) の`CMFCRibbonEdit`コントロールです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hascompactmode"></a>CMFCRibbonEdit::HasCompactMode  
 示しますのサイズを表示するかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールをコンパクトにすることができます。  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 既定ではこのメソッドは常`TRUE`します。 表示サイズを圧縮できるかどうかを示すためには、このメソッドをオーバーライドします。  
  
##  <a name="hasfocus"></a>CMFCRibbonEdit::HasFocus  
 示すかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールにフォーカスがあります。  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合、`CMFCRibbonEdit`コントロールにフォーカスがある。 そうしないと`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="haslargemode"></a>CMFCRibbonEdit::HasLargeMode  
 示しますのサイズを表示するかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールが大きくなることができます。  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 既定ではこのメソッドは常`FALSE`します。 表示サイズが大きくなる可能性があるかどうかを示すためには、このメソッドをオーバーライドします。  
  
##  <a name="hasspinbuttons"></a>CMFCRibbonEdit::HasSpinButtons  
 スピン ボタンがテキスト ボックスにあるかどうかを示します。  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`テキスト ボックスに、スピン ボタンがある場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ishighlighted"></a>CMFCRibbonEdit::IsHighlighted  
 示すかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールを強調表示します。  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合、`CMFCRibbonEdit`コントロールが強調表示されている以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onafterchangerect"></a>CMFCRibbonEdit::OnAfterChangeRect  
 フレームワークによって呼び出されますときに表示する四角形のサイズ、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)変更を制御します。  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロールです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondraw"></a>CMFCRibbonEdit::OnDraw  
 描画するフレームワークによって呼び出され、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールです。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロールです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawlabelandimage"></a>CMFCRibbonEdit::OnDrawLabelAndImage  
 イメージのラベルを描画およびフレームワークによって呼び出され、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールです。  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロールです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawonlist"></a>CMFCRibbonEdit::OnDrawOnList  
 描画するためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コマンドのリスト ボックス内のコントロールです。  
  
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
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロールです。  
  
 [入力] `strText`  
 表示テキスト[](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit class")します。  
  
 [入力] `nTextOffset`  
 距離 (ピクセル単位) テキストを表示するリスト ボックスの左側にありますから。  
  
 [入力] `rect`  
 表示する四角形、`CMFCRibbonEdit`コントロールです。  
  
 [入力] `bIsSelected`  
 このパラメーターは使用されません。  
  
 [入力] `bHighlighted`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
 コマンドのリスト ボックスには、クイック アクセス ツールバーをカスタマイズできるようにリボン コントロールが表示されます。  
  
##  <a name="onenable"></a>CMFCRibbonEdit::OnEnable  
 有効または無効にするフレームワークによって呼び出され、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールです。  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`コントロールを有効にするには`FALSE`制御を無効にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onhighlight"></a>CMFCRibbonEdit::OnHighlight  
 ポインターか、またはの境界から出たときに、フレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールです。  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHighlight`  
 `TRUE`ポインターがの境界内にある場合、`CMFCRibbonEdit`コントロール。 それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onkey"></a>CMFCRibbonEdit::OnKey  
 Keytip を押したときに、フレームワークによって呼び出され、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールにフォーカスがあります。  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsMenuKey`  
 `TRUE`keytip がポップアップ メニューが表示された場合それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 イベントが処理された場合は、`TRUE`、それ以外の場合は、`FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onlbuttondown"></a>CMFCRibbonEdit::OnLButtonDown  
 更新するためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)ユーザーがコントロールにマウスの左ボタンを押したときを制御します。  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onlbuttonup"></a>CMFCRibbonEdit::OnLButtonUp  
 マウスの左ボタンを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onrtlchanged"></a>CMFCRibbonEdit::OnRTLChanged  
 更新するためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)レイアウトの方向変更されたときを制御します。  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsRTL`  
 `TRUE`レイアウトが右から左である場合`FALSE`レイアウトは左から右へ記述する場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshow"></a>CMFCRibbonEdit::OnShow  
 表示/非表示にフレームワークによって呼び出され、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールです。  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE`コントロールを表示するには`FALSE`コントロールを非表示にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="redraw"></a>CMFCRibbonEdit::Redraw  
 表示を更新、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールです。  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを表示する四角形を再描画、`CMFCRibbonEdit`オブジェクトを直接呼び出していない[CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)で、 `RDW_INVALIDATE`、 `RDW_ERASE`、および`RDW_UPDATENOW`フラグを設定します。  
  
##  <a name="setaccdata"></a>CMFCRibbonEdit::SetACCData  
 ユーザー補助データを設定、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトです。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParent`  
 親ウィンドウへのポインター、`CMFCRibbonEdit`オブジェクトです。  
  
 `data`  
 ユーザー補助データを`CMFCRibbonEdit`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setedittext"></a>CMFCRibbonEdit::SetEditText  
 テキスト ボックスにテキストを設定します。  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strText`  
 テキスト ボックスのテキストです。  
  
##  <a name="settextalign"></a>CMFCRibbonEdit::SetTextAlign  
 テキスト ボックスのテキストの配置を設定します。  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nAlign`  
 テキストの配置の列挙値。 指定できる値については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 パラメーター`nAlign`コントロールのスタイルは、次の編集の&1; つ。  
  
- **ES_LEFT**左詰め  
  
- **ES_CENTER**の中央揃え  
  
- **ES_RIGHT**右揃え  
  
 これらのスタイルの詳細については、次を参照してください。[コントロールのスタイルの編集](http://msdn.microsoft.com/library/windows/desktop/bb775464)します。  
  
##  <a name="setwidth"></a>CMFCRibbonEdit::SetWidth  
 テキスト ボックスの幅を設定、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールです。  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nWidth`  
 テキスト ボックスのピクセル単位の幅。  
  
 `bInFloatyMode`  
 `TRUE`浮動小数点モードの幅を設定するには`FALSE`通常モードの幅を設定します。  
  
### <a name="remarks"></a>コメント  
 `CMFCRibbonEdit`コントロールの表示モードによっては&2; 分の幅がある: 浮動モードと通常モードです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
