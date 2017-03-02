---
title: "CMFCToolBarFontComboBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontComboBox
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontComboBox class
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
caps.latest.revision: 29
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
ms.openlocfilehash: 50b22e19cab4f434ec53383c8a170344e89cbab0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox クラス
ユーザーがシステム フォントの一覧からフォントを選択できるコンボ ボックス コントロールを含むツール バー ボタンです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|`CMFCToolBarFontComboBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|ポインターを返す、`CMFCFontInfo`コンボ ボックスで指定したインデックスのオブジェクト。|  
|[CMFCToolBarFontComboBox::SetFont](#setfont)|フォントの名前、またはフォントのプレフィックスと文字セットは、いずれかに従って、フォント コンボ ボックスのフォントを選択します。|  
  
### <a name="data-members"></a>データ メンバー  
 [CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)  
 フォント コンボ ボックス内の文字の高さ。  
  
## <a name="remarks"></a>コメント  
 フォント コンボ ボックス ボタンをツールバーに追加するには、次の手順を実行します。  
  
1.  親ツール バー リソースでボタンのダミー リソース ID を予約します。  
  
2.  `CMFCToolBarFontComboBox` オブジェクトを構築します。  
  
3.  処理するメッセージ ハンドラーで、`AFX_WM_RESETTOOLBAR`メッセージを使用して、元のボタンを新しいコンボ ボックス ボタンに置き換える[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)します。  
  
4.  同期を使用して、ドキュメント内のフォントを使用してコンボ ボックスで選択したフォント、 [CMFCToolBarFontComboBox::SetFont](#setfont)メソッドです。  
  
 コンボ ボックスで選択したフォントを使用して、ドキュメントのフォントを同期する使用、 [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)選択したフォントの属性を取得し、それらの属性を使用して作成する方法、 [CFont クラス](../../mfc/reference/cfont-class.md)オブジェクトです。  
  
 フォント コンボ ボックス ボタンは、Win32 関数を呼び出して[EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620)をシステムで使用可能な画面およびプリンターのフォントを決定します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbarfontcombobox.h  
  
##  <a name="a-namecmfctoolbarfontcomboboxa--cmfctoolbarfontcomboboxcmfctoolbarfontcombobox"></a><a name="cmfctoolbarfontcombobox"></a>CMFCToolBarFontComboBox::CMFCToolBarFontComboBox  
 構築、 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)オブジェクトです。  
  
```  
public:  
CMFCToolBarFontComboBox(
    UINT uiID,  
    int iImage,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    DWORD dwStyle = CBS_DROPDOWN,  
    int iWidth = 0,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);

 
protected:  
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,  
    int nFontType,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily);  
  
CMFCToolBarFontComboBox();
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 コンボ ボックスのコマンド ID。  
  
 [入力] `iImage`  
 ツール バー イメージの&0; から始まるインデックス。 イメージが格納されて、 [CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)オブジェクトを[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)クラスを保持します。  
  
 [入力] `nFontType`  
 コンボ ボックスに表示されるフォントの種類。 このパラメーターは、次の値の組み合わせ (論理 OR) を指定できます。  
  
 DEVICE_FONTTYPE  
  
 RASTER_FONTTYPE  
  
 TRUETYPE_FONTTYPE  
  
 [入力] `nCharSet`  
 場合は DEFAULT_CHARSET、コンボ ボックスに設定するには、すべての文字セット内のすべて一意にという名前のフォントが含まれています。 (同じ名前の&2; つのフォントがある場合は、コンボ ボックスが含まれていますうちの&1; つです。)場合は、コンボ ボックスの有効な文字セット値に設定するには、指定された文字セットで複数のフォントのみが含まれています。 参照してください[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)可能な文字の一覧を設定します。  
  
 [入力] `dwStyle`  
 コンボ ボックスのスタイル。 (参照[コンボ ボックス スタイル](../../mfc/reference/combo-box-styles.md))  
  
 [入力] `iWidth`  
 エディット コントロールのピクセル単位の幅。  
  
 [入力] `nPitchAndFamily`  
 場合は DEFAULT_PITCH、コンボ ボックスに設定するには、声の高さに関係なくフォントが含まれています。 かどうか FIXED_PITCH または VARIABLE_PITCH に設定すると、コンボ ボックス フォントのみを含む、ピッチ タイプにします。 フォント ファミリに基づくフィルター処理は現在サポートされていません。  
  
 [出力] `pLstFontsExternal`  
 ポインター、 [CObList クラス](../../mfc/reference/coblist-class.md)利用可能なフォントを格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 通常、`CMFCToolBarFontComboBox`オブジェクトは、単一の共有に使用できるフォントの一覧を格納`CObList`オブジェクトです。 コンス トラクターの&2; つ目のオーバー ロードを使用する有効なポインターを提供していて`pLstFontsExternal`、その`CMFCToolBarFontComboBox`オブジェクトにより値が代わりに、`CObList`を`pLstFontsExternal`利用可能なフォントが指しています。  
  
### <a name="example"></a>例  
 次の例では、構築、`CMFCToolBarFontComboBox`オブジェクトです。 このコード スニペットの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#7;](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]  
  
##  <a name="a-namegetfontdesca--cmfctoolbarfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFCToolBarFontComboBox::GetFontDesc  
 ポインターを返す、`CMFCFontInfo`コンボ ボックスで指定したインデックスのオブジェクト。  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 コンボ ボックスの項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMFCFontInfo`オブジェクトです。 場合`iIndex`有効なアイテムのインデックスが指定されていない戻り値は`NULL`です。  
  
##  <a name="a-namemnfontheighta--cmfctoolbarfontcomboboxmnfontheight"></a><a name="m_nfontheight"></a>CMFCToolBarFontComboBox::m_nFontHeight  
 コンボ ボックスのオーナー描画スタイルの場合、フォント コンボ ボックス内の文字のピクセルで高さを指定します。  
  
```  
static int m_nFontHeight  
```  
  
### <a name="remarks"></a>コメント  
 場合、`m_nFontHeight`変数が 0 の高さは、コンボ ボックスの既定のフォントに従って自動的に計算されます場合、。 高さには、ベースラインを超えた文字のアセントとベースラインの下にある文字のディセントの両方が含まれています。  
  
##  <a name="a-namesetfonta--cmfctoolbarfontcomboboxsetfont"></a><a name="setfont"></a>CMFCToolBarFontComboBox::SetFont  
 フォント、フォント名と文字に従ってフォント コンボ ボックスで設定を選択しますが、パラメーターで指定されます。  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BOOL bExact=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszName`  
 フォントの名前またはプレフィックスを指定します。  
  
 [入力] `nCharSet`  
 文字セットを指定します。  
  
 [入力] `bExact`  
 指定するかどうか`lpszName`フォント名またはフォントのプレフィックスが含まれています。  
  
### <a name="return-value"></a>戻り値  
 フォントが正常に選択されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`bExact`は`TRUE`、このメソッドに指定した名前と一致するフォントを選択する`lpszName`です。 場合`bExact`は`FALSE`、このメソッドは、先頭として指定したテキストにフォントを選択します。`lpszName`として指定した文字セットを使用すると`nCharSet`です。 場合`nCharSet`設定されている DEFAULT_CHARSET、する文字セットは無視されるのみする`lpszName`フォントを選択するために使用されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [チュートリアル: ツールバーへのコントロールを配置します。](../../mfc/walkthrough-putting-controls-on-toolbars.md)




