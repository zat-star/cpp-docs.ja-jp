---
title: "イベント マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event maps
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: 15
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 4c4777496ce609d7c2fa20da726f211264095b6e
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="event-maps"></a>イベント マップ
コントロール (にキーを押す、マウス クリックやコントロールの状態への変更) (コントロールの開発者によって決定されます)、何らかのアクションが発生したそのコンテナーに通知することが希望されるたびに、イベント発生関数を呼び出します。 この関数では、関連するイベントを発生させるである重要な動作が発生した、コントロール コンテナーに通知します。  
  
 Microsoft Foundation Class ライブラリは、イベントを発生させるために最適化されたプログラミング モデルを提供します。 このモデルでは「イベント マップ」を使用する関数が特定のコントロールのイベントを発生させるかを指定します。 イベント マップには、イベントごとに&1; つのマクロが含まれています。 たとえば、イベント マップを発生させるストックの Click イベントは次のようになります。  
  
 [!code-cpp[NVC_MFCAxCtl&#16;](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]  
  
 **EVENT_STOCK_CLICK**マクロでは、コントロールがマウスが検出されるたびにイベントをクリック、株価を発生することを示します。 その他のストック イベントの詳細な一覧については、記事を参照して[ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)です。 マクロは、カスタム イベントを示すために使用します。  
  
 イベント マップ マクロは重要なは、一般に挿入しないに直接します。 これは、[プロパティ] ウィンドウがイベントに関連付けるイベント発生関数を使用する場合、ソース ファイルにイベント マップ エントリが自動的にによって作成されるためです。 編集またはイベント マップ エントリを追加するとき、[プロパティ] ウィンドウを使用することができます。  
  
 イベント マップをサポートするためには、MFC には、次のマクロが用意されています。  
  
### <a name="event-map-declaration-and-demarcation"></a>イベント マップの宣言と定義  
  
|||  
|-|-|  
|[DECLARE_EVENT_MAP](#declare_event_map)|イベント マップがクラスでイベントをイベント発生関数 (クラス宣言で使用する必要があります) にマップに使用されることを宣言します。|  
|[BEGIN_EVENT_MAP](#begin_event_map)|イベント マップ (クラスの実装で使用する必要があります) の定義を開始します。|  
|[END_EVENT_MAP](#end_event_map)|イベント マップ (クラスの実装で使用する必要があります) の定義を終了します。|  
  
### <a name="event-mapping-macros"></a>イベント マップ マクロ  
  
|||  
|-|-|  
|[については、「](#event_custom)|イベント発生関数が指定されたイベントを発生させることを示します。|  
|[EVENT_CUSTOM_ID](#event_custom_id)|イベント発生関数が、指定したディスパッチ ID を使用して、指定したイベントを発生させることを示します。|  
  
### <a name="message-mapping-macros"></a>メッセージ割り当てマクロ  
  
|||  
|-|-|  
|[ON_OLEVERB](#on_oleverb)|OLE コントロールによって処理されるカスタム動詞を示します。|  
|[ON_STDOLEVERB](#on_stdoleverb)|OLE コントロールの標準動詞マッピングを上書きします。|  
  
##  <a name="declare_event_map"></a>DECLARE_EVENT_MAP  
 各`COleControl`-プログラム内の派生クラスは、コントロールが発生するイベントを指定するためのイベント マップを提供できます。  
  
```   
DECLARE_EVENT_MAP()   
```  
  
### <a name="remarks"></a>コメント  
 使用して、`DECLARE_EVENT_MAP`クラス宣言の末尾のマクロです。 クラスのメンバー関数を定義する .cpp ファイルで使用して、`BEGIN_EVENT_MAP`マクロ、各コントロールのイベントについてマクロ エントリと`END_EVENT_MAP`イベント リストの末尾を宣言するマクロ。  
  
 イベント マップの詳細については、記事を参照してください。 [ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="begin_event_map"></a>BEGIN_EVENT_MAP  
 イベント マップの定義を開始します。  
  
```   
BEGIN_EVENT_MAP(theClass,  baseClass)  
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 イベント マップを持つコントロール クラスの名前を指定します。  
  
 `baseClass`  
 基本クラスの名前を指定`theClass`します。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する、実装 (.cpp) ファイルを持つイベント マップを開始、`BEGIN_EVENT_MAP`マクロ、イベントのそれぞれのマクロのエントリを追加し、ししを持つイベント マップ、`END_EVENT_MAP`マクロです。  
  
 イベントの詳細については、マップ、および`BEGIN_EVENT_MAP`マクロ、記事を参照して[ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="end_event_map"></a>END_EVENT_MAP  
 使用して、`END_EVENT_MAP`マクロ イベント マップの定義を終了します。  
  
```   
END_EVENT_MAP()   
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="event_custom"></a>については、「  
 カスタム イベントのイベント マップ エントリを定義します。  
  
```   
EVENT_CUSTOM(pszName, pfnFire,  vtsParams) 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszName`  
 イベントの名前です。  
  
 `pfnFire`  
 イベント発生関数の名前。  
  
 `vtsParams`  
 スペースで区切られた一連の関数のパラメーター リストを指定する&1; つ以上の定数です。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`パラメーターは、スペースで区切られた一連の値から、 **vts _**定数です。 1 つ以上のスペース (コンマではなく) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例:  
  
 [!code-cpp[NVC_MFCActiveXControl&#13;](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 RGB を表す 32 ビット整数を含むリストを指すポインターによりその後に、値の色を示す、**この**OLE フォント オブジェクトのインターフェイスです。  
  
 **Vts _**定数とその意味は次のようには。  
  
|シンボル|パラメーターの型|  
|------------|--------------------|  
|**VTS_I2**|**short**|  
|**VTS_I4**|**long**|  
|**VTS_R4**|**float**|  
|**VTS_R8**|**double**|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_CY**|**通貨**|  
|**VTS_DATE**|**日付**|  
|**VTS_BSTR**|**const char\***|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_FONT**|**IFontDispatch\***|  
|**VTS_HANDLE**|`HANDLE`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const バリアント\***|  
|**VTS_PVARIANT**|**バリアント\***|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_OPTEXCLUSIVE**|**OLE_OPTEXCLUSIVE**|  
|**VTS_PICTURE**|**IPictureDisp\***|  
|**VTS_TRISTATE**|**OLE_TRISTATE**|  
|**VTS_XPOS_PIXELS**|**OLE_XPOS_PIXELS**|  
|**VTS_YPOS_PIXELS**|**OLE_YPOS_PIXELS**|  
|**VTS_XSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_YSIZE_PIXELS**|**OLE_YSIZE_PIXELS**|  
|**VTS_XPOS_HIMETRIC**|**OLE_XPOS_HIMETRIC**|  
|**VTS_YPOS_HIMETRIC**|**OLE_YPOS_HIMETRIC**|  
|**VTS_XSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
|**VTS_YSIZE_HIMETRIC**|**OLE_YSIZE_HIMETRIC**|  
  
> [!NOTE]
>  追加のバリアント定数は、例外として、すべてのバリアント型に対して定義されている**VTS_FONT**と**VTS_PICTURE**、variant データ定数へのポインターを提供します。 使用してこれらの定数がという名前の**付け**`constantname`規則です。 たとえば、 **VTS_PCOLOR**へのポインター、 **VTS_COLOR**定数です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="event_custom_id"></a>EVENT_CUSTOM_ID  
 関数で指定したディスパッチ ID に属するカスタム イベントを発生させるイベントを定義`dispid`します。  
  
```   
EVENT_CUSTOM_ID(
  pszName,   
  dispid,   
  pfnFire,
  vtsParams)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszName`  
 イベントの名前です。  
  
 `dispid`  
 イベントを発生させるときに、コントロールによって使用されるディスパッチ ID。  
  
 `pfnFire`  
 イベント発生関数の名前。  
  
 `vtsParams`  
 パラメーターの変数の一覧は、イベントが発生したときに、コントロール コンテナーに渡されます。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _**定数です。 1 つ以上のスペースでできませんコンマで区切ったこれらの値は、関数のパラメーター リストを指定します。 例:  
  
 [!code-cpp[NVC_MFCActiveXControl&#13;](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 RGB を表す 32 ビット整数を含むリストを指すポインターによりその後に、値の色を示す、**この**OLE フォント オブジェクトのインターフェイスです。  
  
 一覧については、 **vts _**定数を参照してください[EVENT_CUSTOM](#event_custom)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="on_oleverb"></a>ON_OLEVERB  
 このマクロは、カスタム動詞をコントロールの特定のメンバー関数にマップするメッセージ マップ エントリを定義します。  
  
```   
ON_OLEVERB(idsVerbName,  memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 *idsVerbName*  
 動詞名の文字列リソース ID。  
  
 `memberFxn`  
 動詞が呼び出されたときに、フレームワークによって呼び出される関数。  
  
### <a name="remarks"></a>コメント  
 文字列テーブルに追加されるカスタム動詞名を作成するリソース エディターを使用できます。  
  
 関数のプロトタイプ`memberFxn`は。  
  
 `BOOL memberFxn(`    
 `LPMSG` `lpMsg` `,`   
 `HWND` `hWndParent` `,`   
 `LPCRECT` `lpRect`   `);`  
  
 値、 `lpMsg`、 `hWndParent`、および`lpRect`パラメーターは、の対応するパラメーターから取得、 **IOleObject::DoVerb**メンバー関数。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxole.h  
  
##  <a name="on_stdoleverb"></a>ON_STDOLEVERB  
 このマクロを使用すると、標準の動詞の既定の動作を上書きできます。  
  
```   
ON_STDOLEVERB(iVerb,   memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 オーバーライドされている動詞の標準動詞のインデックス。  
  
 `memberFxn`  
 動詞が呼び出されたときに、フレームワークによって呼び出される関数。  
  
### <a name="remarks"></a>コメント  
 形式は、標準の動詞インデックス**OLEIVERB_**、その後に操作します。 `OLEIVERB_SHOW`、 `OLEIVERB_HIDE`、および`OLEIVERB_UIACTIVATE`標準的な動詞の例を示します。  
  
 参照してください[ON_OLEVERB](#on_oleverb)として使用される関数のプロトタイプの詳細については、`memberFxn`パラメーター。  

  
### <a name="requirements"></a>要件  
  **ヘッダー** afxole.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

