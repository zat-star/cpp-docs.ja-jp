---
title: "CMFCFontComboBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox::DrawItem method
- CMFCFontComboBox::PreTranslateMessage method
- CMFCFontComboBox::MeasureItem method
- CMFCFontComboBox class
- CMFCFontComboBox::CompareItem method
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1252f5ca102637e70cc384afd723464aec4144b4
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox クラス
`CMFCFontComboBox`クラスは、フォントの一覧を含むコンボ ボックス コントロールを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|`CMFCFontComboBox` オブジェクトを構築します。|  
|`CMFCFontComboBox::~CMFCFontComboBox`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|現在のフォント コンボ ボックス コントロールの並べ替えられたリスト ボックスに新しい項目の相対的な位置を決定するためにフレームワークによって呼び出されます。 (上書き[CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem))。|  
|`CMFCFontComboBox::DrawItem`|現在のフォント コンボ ボックス コントロールで、指定した項目を描画するためにフレームワークによって呼び出されます。 (上書き[CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem))。|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|現在選択されているフォントについての情報を取得します。|  
|`CMFCFontComboBox::MeasureItem`|現在のフォント コンボ ボックス コントロールのリスト ボックスの各次元の Windows に通知するためにフレームワークによって呼び出されます。 (上書き[CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem))。|  
|`CMFCFontComboBox::PreTranslateMessage`|ウィンドウのメッセージの変換にディスパッチされる前に、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 (上書き[CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage))。|  
|[CMFCFontComboBox::SelectFont](#selectfont)|フォント コンボ ボックスから、指定した条件に一致するフォントを選択します。|  
|[CMFCFontComboBox::Setup](#setup)|フォント コンボ ボックス内の項目の一覧を初期化します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|現在のフォント コンボ ボックス内の項目のラベルの描画に使用するフォントをフレームワークに指示します。|  
  
## <a name="remarks"></a>コメント  
 使用する、 `CMFCFontComboBox`  ダイアログ ボックス内のオブジェクトを追加、`CMFCFontComboBox`変数 ダイアログ ボックス クラスにします。 次に、 `OnInitDialog`  ダイアログ ボックス クラスの呼び出しのメソッド、 [CMFCFontComboBox::Setup](#setup)コンボ ボックス コントロールの項目の一覧を初期化します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxfontcombobox.h  
  
##  <a name="cmfcfontcombobox"></a>CMFCFontComboBox::CMFCFontComboBox  
 `CMFCFontComboBox` オブジェクトを構築します。  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getselfont"></a>CMFCFontComboBox::GetSelFont  
 現在選択されているフォントについての情報を取得します。  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)フォントを表すオブジェクト。 できます`NULL`コンボ ボックスにフォントが選択されていない場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_bdrawusingfont"></a>CMFCFontComboBox::m_bDrawUsingFont  
 現在のフォント コンボ ボックス内の項目のラベルの描画に使用するフォントをフレームワークに指示します。  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーを設定`TRUE`に同じフォントを使用して各項目のラベルを描画するようフレームワークに指示します。 このメンバーを設定`FALSE`フレームワークの名前は、ラベルと同じフォントを使用して各項目のラベルの描画に指示します。 このメンバーの既定値は`FALSE`です。  
  
##  <a name="selectfont"></a>CMFCFontComboBox::SelectFont  
 フォント コンボ ボックスから、指定した条件に一致するフォントを選択します。  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDesc`  
 フォントの説明オブジェクトへのポインター。  
  
 [入力] `lpszName`  
 フォント名を指定します。  
  
 [入力] `nCharSet`  
 文字セットを指定します。 既定値は、DEFAULT_CHARSET です。 詳細については、次を参照してください。、`lfCharSet`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フォント コンボ ボックス内の項目は、説明オブジェクトの指定したフォントまたはフォントの名前と charset; と一致する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、選択し、指定したフォントに対応するフォント コンボ ボックス内の項目までスクロールします。  
  
### <a name="example"></a>例  
 次の例では、使用して、`SelectFont`メソッドで、`CMFCFontComboBox`クラスです。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#35;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="setup"></a>CMFCFontComboBox::Setup  
 フォント コンボ ボックス内の項目の一覧を初期化します。  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFontType`  
 フォントの種類を指定します。 既定値は、DEVICE_FONTTYPE、RASTER_FONTTYPE、および TRUETYPE_FONTTYPE のビットごとの組み合わせ (OR です)。  
  
 [入力] `nCharSet`  
 フォントの文字セットを指定します。 既定値は、DEFAULT_CHARSET です。  
  
 [入力] `nPitchAndFamily`  
 フォントのピッチとファミリを指定します。 既定値は、DEFAULT_PITCH です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フォント コンボ ボックスが正常に初期化されていた場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、指定されたパラメーターと一致する現在インストールされているフォントを列挙して、フォント コンボ ボックスにそのフォント名を挿入する、フォント コンボ ボックスを初期化します。  
  
### <a name="example"></a>例  
 次の例では、使用して、`Setup`メソッドで、`CMFCFontComboBox`クラスです。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#36;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)

