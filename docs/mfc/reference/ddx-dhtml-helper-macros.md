---
title: "DDX_DHtml ヘルパー マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d5a69e08d06a53dcb2f3a4be58618e9829e8c8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml ヘルパー マクロ
DDX_DHtml ヘルパー マクロでは、一般的に使用される HTML ページ上のコントロールのプロパティに簡単にアクセスできるようにします。  
  
### <a name="data-exchange-macros"></a>データ交換マクロ  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|設定または選択コントロールからプロパティ値を取得します。|  
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|設定または現在の要素の開始と終了タグの間のテキストを取得します。|  
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|設定または現在の要素の開始と終了タグの間の HTML を取得します。|  
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|設定またはコピー先の URL またはアンカー ポイントを取得します。|  
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|設定またはターゲット ウィンドウまたはフレームを取得します。|  
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|設定またはイメージまたはドキュメント内のビデオ クリップの名前を取得します。|  
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|設定または関連するフレームの URL を取得します。|  
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|設定または関連するフレームの URL を取得します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdhtml.h  

## <a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href
設定またはコピー先の URL またはアンカー ポイントを取得します。  
  
  
  
```  
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `name`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLANCHORELEMENT_HREF を使用して関数のディスパッチ id。

## <a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target
 設定またはターゲット ウィンドウまたはフレームを取得します。  
    
```  
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `name`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLANCHORELEMENT_TARGET を使用して関数のディスパッチ id。  

## <a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml
 設定または現在の要素の開始と終了タグの間の HTML を取得します。  
  
  
  
```  
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `name`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLELEMENT_INNERHTML を使用して関数のディスパッチ id。  
  

## <a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText
設定または現在の要素の開始と終了タグの間のテキストを取得します。  
  
  
  
```  
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `name`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLELEMENT_INNERTEXT を使用して関数のディスパッチ id。 

## <a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue  
設定または選択コントロールからプロパティ値を取得します。  
 
```  
DDX_DHtml_ElementValue(
    CDataExchange* dx,  
    LPCTSTR name,
    var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `name`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 `var`  
 交換される値。 参照してください*値*で[CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext)です。  
  
## <a name="remarks"></a>コメント  
 このマクロは値プロパティを持つコントロール上で実行時にのみ成功します。 値プロパティを持つコントロールには、エディット ボックス、リスト ボックスやコンボ ボックスが含まれます。  
  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_A_VALUE を使用して関数のディスパッチ id。  

## <a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src
設定または関連するフレームの URL を取得します。  
  
```  
DDX_DHtml_Frame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `name`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLFRAMEBASE_SRC を使用して関数のディスパッチ id。  

## <a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src
設定または関連するフレームの URL を取得します。  
  
  
  
```  
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `name`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLFRAMEBASE_SRC を使用して関数のディスパッチ id。 

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src
取得またはイメージまたはドキュメント内のビデオ クリップの名前を取得します。  
  
```  
DDX_DHtml_Img_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dx`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `name`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 `var`  
 交換される値。  
  
## <a name="remarks"></a>コメント  
 使用する場合、`DDX_DHtml_Img_Src`マクロ、src 要素のプロパティをイメージ、Internet Explorer イメージ オブジェクトを取得するには、イメージ ソースの完全にエスケープされた URL が返されます。 たとえば、使用する場合、 `DDX_DHtml_Img_Src` 「いくつか興味深い画像」イメージ要素の src プロパティを文字列に設定するマクロ文字列"res://d:\myapplication\myapp.exe/some% を Internet Explorer が返されますそのプロパティを取得する場合20interesting %20picture。"  
  
 このマクロを呼び出す、 [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLIMGELEMENT_SRC を使用して関数のディスパッチ id。  

  
## <a name="see-also"></a>参照  
 [CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)
