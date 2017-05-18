---
title: "CFontHolder クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
dev_langs:
- C++
helpviewer_keywords:
- custom fonts
- CFontHolder class
- fonts, ActiveX controls
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fdfa16756ff218159087969f2a4967ed5e76a445
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cfontholder-class"></a>CFontHolder クラス
ストック フォント プロパティを実装し、Windows のフォント オブジェクトと `IFont` インターフェイスの機能をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFontHolder  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](#cfontholder)|`CFontHolder` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFontHolder::GetDisplayString](#getdisplaystring)|コンテナーのプロパティ ブラウザーに表示される文字列を取得します。|  
|[CFontHolder::GetFontDispatch](#getfontdispatch)|フォントの返します`IDispatch`インターフェイスです。|  
|[CFontHolder::GetFontHandle](#getfonthandle)|Windows フォントへのハンドルを返します。|  
|[CFontHolder::InitializeFont](#initializefont)|初期化、`CFontHolder`オブジェクトです。|  
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|関連するフォントの情報を取得します。|  
|[CFontHolder::ReleaseFont](#releasefont)|接続が切断、`CFontHolder`オブジェクトから、`IFont`と`IFontNotification`インターフェイスです。|  
|[CFontHolder::Select](#select)|デバイス コンテキストにフォント リソースを選択します。|  
|[CFontHolder::SetFont](#setfont)|接続、`CFontHolder`するオブジェクト、`IFont`インターフェイスです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFontHolder::m_pFont](#m_pfont)|ポインター、`CFontHolder`オブジェクトの`IFont`インターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 `CFontHolder`基本クラスはありません。  
  
 このクラスを使用すると、コントロールのカスタム フォントのプロパティを実装します。 このようなプロパティを作成する方法の詳細については、記事を参照してください。 [ActiveX コントロール: フォントの使用](../../mfc/mfc-activex-controls-using-fonts.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CFontHolder`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
##  <a name="cfontholder"></a>CFontHolder::CFontHolder  
 `CFontHolder` オブジェクトを構築します。  
  
```  
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```  
  
### <a name="parameters"></a>パラメーター  
 *pNotify*  
 フォントへのポインター`IPropertyNotifySink`インターフェイスです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります`InitializeFont`を使用する前に、結果のオブジェクトを初期化します。  
  
##  <a name="getdisplaystring"></a>CFontHolder::GetDisplayString  
 コンテナーのプロパティ ブラウザーに表示できる文字列を取得します。  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `strValue`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)表示文字列を保持します。  
  
### <a name="return-value"></a>戻り値  
 文字列が取得できた場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="getfontdispatch"></a>CFontHolder::GetFontDispatch  
 フォントのディスパッチ インターフェイスへのポインターを取得するには、この関数を呼び出します。  
  
```  
LPFONTDISP GetFontDispatch();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFontHolder`オブジェクトの**この**インターフェイスです。 関数を呼び出してことに注意してください`GetFontDispatch`呼び出す必要があります`IUnknown::Release`処理終了したときに、このインターフェイス ポインターでします。  
  
### <a name="remarks"></a>コメント  
 呼び出す`InitializeFont`呼び出す前に`GetFontDispatch`します。  
  
##  <a name="getfonthandle"></a>CFontHolder::GetFontHandle  
 Windows フォントへのハンドルを取得するには、この関数を呼び出します。  
  
```  
HFONT GetFontHandle();

 
HFONT GetFontHandle(
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>パラメーター  
 `cyLogical`  
 論理ユニットは、コントロールを描画する四角形の高さ。  
  
 `cyHimetric`  
 高さの`MM_HIMETRIC`コントロールの単位です。  
  
### <a name="return-value"></a>戻り値  
 フォント オブジェクトへのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 比`cyLogical`と`cyHimetric`フォントのポイント サイズの単位の論理単位で、適切な表示サイズを計算に使用される`MM_HIMETRIC`単位数。  
  
 表示サイズ = ( `cyLogical`  /  `cyHimetric`) フォントのサイズ  
  
 パラメーターなしのバージョンでは、画面のサイズが正しく構成のフォントにハンドルを返します。  
  
##  <a name="initializefont"></a>CFontHolder::InitializeFont  
 初期化、`CFontHolder`オブジェクトです。  
  
```  
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,  
    LPDISPATCH pFontDispAmbient = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFontDesc`  
 フォントの記述の構造体へのポインター ( [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782)) フォントの特性を指定します。  
  
 `pFontDispAmbient`  
 コンテナーのアンビエント フォント プロパティへのポインター。  
  
### <a name="remarks"></a>コメント  
 場合`pFontDispAmbient`は**NULL**、`CFontHolder`の複製にオブジェクトが接続されている、`IFont`コンテナーのアンビエント フォント プロパティで使用されるインターフェイスです。  
  
 場合`pFontDispAmbient`は**NULL**のいずれかが指すフォントの記述から新しい Font オブジェクトが作成された`pFontDesc`または、`pFontDesc`は**NULL**既定の説明からです。  
  
 構築した後、この関数を呼び出して、`CFontHolder`オブジェクトです。  
  
##  <a name="m_pfont"></a>CFontHolder::m_pFont  
 ポインター、`CFontHolder`オブジェクトの`IFont`インターフェイスです。  
  
```  
LPFONT m_pFont;  
```  
  
##  <a name="querytextmetrics"></a>CFontHolder::QueryTextMetrics  
 によって表される物理フォントに関する情報を取得、`CFontHolder`オブジェクトです。  
  
```  
void QueryTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>パラメーター  
 `lptm`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)は情報を受信する構造体。  
  
##  <a name="releasefont"></a>CFontHolder::ReleaseFont  
 この関数は切断、`CFontHolder`オブジェクトからその`IFont`インターフェイスです。  
  
```  
void ReleaseFont();
```  
  
##  <a name="select"></a>CFontHolder::Select  
 この関数では、指定したデバイス コンテキストにコントロールのフォントを選択します。  
  
```  
CFont* Select(
    CDC* pDC,  
    long cyLogical,  
    long cyHimetric);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 フォントの選択先デバイス コンテキスト。  
  
 `cyLogical`  
 論理ユニットは、コントロールを描画する四角形の高さ。  
  
 `cyHimetric`  
 高さの`MM_HIMETRIC`コントロールの単位です。  
  
### <a name="return-value"></a>戻り値  
 置き換えられるフォントへのポインター。  
  
### <a name="remarks"></a>コメント  
 参照してください[GetFontHandle](#getfonthandle)については、`cyLogical`と`cyHimetric`パラメーター。  
  
##  <a name="setfont"></a>CFontHolder::SetFont  
 すべての既存のフォントを解放し、接続、`CFontHolder`オブジェクトを`IFont`インターフェイスです。  
  
```  
void SetFont(LPFONT pNewFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *pNewFont*  
 新しいポインター`IFont`インターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPropExchange クラス](../../mfc/reference/cpropexchange-class.md)

