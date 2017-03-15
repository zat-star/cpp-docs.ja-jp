---
title: "DDX_DHtml ヘルパー マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- DDX_DHtml
dev_langs:
- C++
helpviewer_keywords:
- macros, exchanging data with HMTL pages
- DDX macros
- HTML pages, helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros, DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
caps.latest.revision: 14
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
ms.openlocfilehash: d3c5136b52206a1ec67e1e1fc78ec291a2954faf
ms.lasthandoff: 02/24/2017

---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml ヘルパー マクロ
DDX_DHtml ヘルパー マクロでは、HTML ページ上のコントロールの一般的に使用されるプロパティに簡単にアクセスできるようにします。  
  
### <a name="data-exchange-macros"></a>データ交換マクロ  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|設定または選択したコントロールの Value プロパティを取得します。|  
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|設定または現在の要素の開始と終了タグの間のテキストを取得します。|  
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|設定または現在の要素の開始と終了タグの間の HTML を取得します。|  
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|設定または参照先の URL またはアンカー ポイントを取得します。|  
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|設定またはターゲット ウィンドウまたはフレームを取得します。|  
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|設定または画像またはドキュメント内のビデオ クリップの名前を取得します。|  
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|設定または関連するフレームの URL を取得します。|  
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|設定または関連するフレームの URL を取得します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdhtml.h  

## <a name="a-nameddxdhtmlanchorhrefa-ddxdhtmlanchorhref"></a><a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href
設定または参照先の URL またはアンカー ポイントを取得します。  
  
  
  
```  
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `name`  
 HTML コントロールの ID パラメーターに指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLANCHORELEMENT_HREF を使用して関数のディスパッチ id。

## <a name="a-nameddxdhtmlanchortargeta--ddxdhtmlanchortarget"></a><a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target
 設定またはターゲット ウィンドウまたはフレームを取得します。  
    
```  
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `name`  
 HTML コントロールの ID パラメーターに指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLANCHORELEMENT_TARGET を使用して関数のディスパッチ id。  

## <a name="a-nameddxdhtmlelementinnerhtmla--ddxdhtmlelementinnerhtml"></a><a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml
 設定または現在の要素の開始と終了タグの間の HTML を取得します。  
  
  
  
```  
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `name`  
 HTML コントロールの ID パラメーターに指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLELEMENT_INNERHTML を使用して関数のディスパッチ id。  
  

## <a name="a-nameddxdhtmlelementinnertexta--ddxdhtmlelementinnertext"></a><a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText
設定または現在の要素の開始と終了タグの間のテキストを取得します。  
  
  
  
```  
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `name`  
 HTML コントロールの ID パラメーターに指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLELEMENT_INNERTEXT を使用して関数のディスパッチ id。 

## <a name="a-nameddxdhtmlelementvaluea-ddxdhtmlelementvalue"></a><a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue  
設定または選択したコントロールの Value プロパティを取得します。  
 
```  
DDX_DHtml_ElementValue(
    CDataExchange* dx,  
    LPCTSTR name,
    var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `name`  
 HTML コントロールの ID パラメーターに指定した値。  
  
 `var`  
 交換される値。 参照してください*値*で[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)します。  
  
## <a name="remarks"></a>コメント  
 このマクロは、値プロパティを持つコントロール上で実行時にのみ成功します。 値プロパティを持つコントロールには、エディット ボックス、リスト ボックスやコンボ ボックスが含まれます。  
  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_A_VALUE を使用して関数のディスパッチ id。  

## <a name="a-nameddxdhtmlframesrca-ddxdhtmlframesrc"></a><a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src
設定または関連するフレームの URL を取得します。  
  
```  
DDX_DHtml_Frame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `name`  
 HTML コントロールの ID パラメーターに指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLFRAMEBASE_SRC を使用して関数のディスパッチ id。  

## <a name="a-nameddxdhtmliframesrca-ddxdhtmliframesrc"></a><a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src
設定または関連するフレームの URL を取得します。  
  
  
  
```  
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `name`  
 HTML コントロールの ID パラメーターに指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLFRAMEBASE_SRC を使用して関数のディスパッチ id。 

## <a name="a-nameddxdhtmlimgsrcaddxdhtmlimgsrc"></a><a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src
取得または画像またはドキュメント内のビデオ クリップの名前を取得します。  
  
```  
DDX_DHtml_Img_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `name`  
 HTML コントロールの ID パラメーターに指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 使用する場合、`DDX_DHtml_Img_Src`マクロ IMAGE 要素、Internet Explorer のイメージ オブジェクトの src プロパティを取得するには、イメージ ソースの完全にエスケープされた URL が返されます。 たとえば、使用する場合、 `DDX_DHtml_Img_Src` 「興味深い図によって、」文字列に画像の要素の src プロパティを設定するマクロをそのプロパティを取得すると Internet Explorer によって、文字列"res://d:\myapplication\myapp.exe/some%20interesting%20picture"が返されます  
  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLIMGELEMENT_SRC を使用して関数のディスパッチ id。  

  
## <a name="see-also"></a>関連項目  
 [CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)

