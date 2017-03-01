---
title: "DHTML イベント マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.macros.shared
dev_langs:
- C++
helpviewer_keywords:
- event map macros
- DHTML, event map macros
- macros, DHTML event map
- DHTML events, event map
- DHTML events
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8be59b52e06241651a2f605ab949efffd0e010d3
ms.lasthandoff: 02/24/2017

---
# <a name="dhtml-event-maps"></a>DHTML イベント マップ
DHTML イベントを処理する次のマクロを使用できます。  
  
## <a name="dhtml-event-map-macros"></a>DHTML イベント マップ マクロ  
 DHTML イベントを処理する次のマクロを使用できます[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-クラスを派生します。  
  
|||  
|-|-|  
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML イベント マップの開始をマークします。|  
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML イベント マップの開始をマークします。|  
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML イベント マップを宣言します。|  
|[DHTML_EVENT](#dhtml_event)|1 つの HTML 要素のドキュメント レベルのイベントを処理するために使用します。|  
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX コントロールが発生するイベントを処理するために使用します。|  
|[DHTML_EVENT_CLASS](#dhtml_event_class)|特定の CSS クラスを持つすべての HTML 要素のドキュメント レベルのイベントを処理するために使用します。|  
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|要素レベルでイベントを処理するために使用します。|  
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|処理に使用する、 **onblur** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|処理に使用する、 `onchange` HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|処理に使用する、 **onclick** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|処理に使用する、 **ondataavailable** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|処理に使用する、 **ondblclick** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|処理に使用する、 **ondragstart** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|処理に使用する、**詳細について**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|処理に使用する、 **onfocus** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|処理に使用する、 `onhelp` HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|処理に使用する、 **onkeydown** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|処理に使用する、 **onkeypress** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|処理に使用する、 **onkeyup** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|処理に使用する、 **onmousedown** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|処理に使用する、 `onmousemove` HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|処理に使用する、 **onmouseout** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|処理に使用する、 **onmouseover** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|処理に使用する、 **onmouseup** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|処理に使用する、 **onresize** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|処理に使用する、 **onselectstart** HTML 要素からのイベントです。|  
|[DHTML_EVENT_TAG](#dhtml_event_tag)|特定の HTML タグを持つすべての要素のドキュメント レベルのイベントを処理するために使用します。|  
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML イベント マップの最後をマークします。|  
  
## <a name="url-event-map-macros"></a>URL イベント マップ マクロ  
 DHTML イベントを処理する次のマクロを使用できます[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)-クラスを派生します。  
  
|||  
|-|-|  
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|マルチページの DHTML および URL のイベント マップの開始をマークします。|  
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|埋め込みの DHTML イベント マップの開始をマークします。|  
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL のイベント エントリ マップの開始をマークします。|  
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|マルチページの DHTML および URL のイベント マップを宣言します。|  
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|マルチページの DHTML および URL のイベント マップの最後をマークします。|  
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|埋め込みの DHTML イベント マップの最後をマークします。|  
|[END_URL_ENTRIES](#end_url_entries)|URL のイベント エントリ マップの最後をマークします。|  
|[URL_EVENT_ENTRY](#url_event_entry)|マルチページ ダイアログは、内のページに、URL または HTML リソースをマップします。|  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namebegindhtmleventmapa--begindhtmleventmap"></a><a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP  
 DHTML イベント マップによって識別されるクラスのソース ファイルに配置した場合の開始をマーク`className`します。  
  
```   
BEGIN_DHTML_EVENT_MAP(className)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 DHTML イベント マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)を含めると、 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)クラス定義内のマクロです。  
  
### <a name="remarks"></a>コメント  
 DHTML イベント マップの追加情報を提供するクラスに**CDHtmlDialog** HTML 要素や、クラスのハンドラー関数に web ページでの ActiveX コントロールによって発生したイベントをルーティングに使用できます。  
  
 場所、`BEGIN_DHTML_EVENT_MAP`クラスの実装 (.cpp) ファイルにマクロが続く`DHTML_EVENT`を処理するイベントのマクロ、クラスは、(たとえば、 `DHTML_EVENT_ONMOUSEOVER` mouseover イベントの)。 使用して、 [END_DHTML_EVENT_MAP](#end_dhtml_event_map)イベント マップの最後をマークするマクロ。 これらのマクロは、次の関数を実装します。  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namebegindhtmleventmapinlinea--begindhtmleventmapinline"></a><a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE  
 DHTML イベント マップのクラス定義内の最初をマーク`className`します。  
  
```   
BEGIN_DHTML_EVENT_MAP_INLINE(className)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 DHTML イベント マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)を含めると、 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)クラス定義内のマクロです。  
  
### <a name="remarks"></a>コメント  
 DHTML イベント マップの追加情報を提供するクラスに**CDHtmlDialog** HTML 要素や、クラスのハンドラー関数に web ページでの ActiveX コントロールによって発生したイベントをルーティングに使用できます。  
  
 場所、`BEGIN_DHTML_EVENT_MAP`クラスの定義 (.h) ファイルにマクロが続く`DHTML_EVENT`を処理するイベントのマクロ、クラスは、(たとえば、 `DHTML_EVENT_ONMOUSEOVER` mouseover イベントの)。 使用して、 [END_DHTML_EVENT_MAP_INLINE](http://msdn.microsoft.com/library/0cfec092-20ee-49f3-bc38-56d6a5572db2)イベント マップの最後をマークするマクロ。 これらのマクロは、次の関数を実装します。  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  

  
##  <a name="a-namedeclaredhtmleventmapa--declaredhtmleventmap"></a><a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP  
 DHTML イベント マップ クラス定義を宣言します。  
  
```   
DECLARE_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>コメント  
 このマクロの定義で使用するのには、 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-クラスを派生します。  
  
 使用[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)または[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)マップを実装します。  
  
 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)次の関数を宣言します。  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventa--dhtmlevent"></a><a name="dhtml_event"></a>DHTML_EVENT  
 (ドキュメント レベル) で識別されるイベントを処理`dispid`の送信元で識別される HTML 要素で`elemName`します。  
  
```   
DHTML_EVENT(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 イベントを処理するように DISPID します。  
  
 `elemName`  
 `LPCWSTR` 、イベントをソーシングの HTML 要素の ID を保持または**NULL**ドキュメントのイベントを処理します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventaxcontrola--dhtmleventaxcontrol"></a><a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL  
 識別されるイベントを処理する`dispid`で識別される ActiveX コントロールによって発生した`controlName`します。  
  
```   
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)  
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 イベントを処理するためのディスパッチの ID。  
  
 `controlName`  
 `LPCWSTR`イベントを発生させるコントロールの HTML の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventclassa--dhtmleventclass"></a><a name="dhtml_event_class"></a>DHTML_EVENT_CLASS  
 (ドキュメント レベル) で識別されるイベントを処理`dispid`送信元では、HTML 要素で識別される CSS クラスを持つ`elemName`です。  
  
```   
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 イベントを処理するためのディスパッチの ID。  
  
 `elemName`  
 `LPCWSTR`イベント ソーシング HTML 要素の CSS クラスを保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventelementa--dhtmleventelement"></a><a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT  
 処理 (で識別される要素に`elemName`) によって識別されるイベント`dispid`です。  
  
```   
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn) 
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 イベントを処理するためのディスパッチの ID。  
  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
 イベントのソースがで識別される要素になる場合は、このマクロは、非バブル イベントの処理に使用される、`elemName`です。  
  
 要素がで識別される場合、このマクロを使用すると、バブル イベントを処理すると、`elemName`イベントのソースができない可能性があります (ソースの任意の要素に含まれている可能性があります`elemName`)。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonafterupdatea--dhtmleventonafterupdate"></a><a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonbeforeupdatea--dhtmleventonbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonblura--dhtmleventonblur"></a><a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR  
 処理する (レベル要素)、 **onblur**イベントです。 これは、非バブル イベントです。  
  
```   
DHTML_EVENT_ONBLUR(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonchangea--dhtmleventonchange"></a><a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE  
 処理する (レベル要素)、`onchange`イベントです。 これは、非バブル イベントです。  
  
```   
DHTML_EVENT_ONCHANGE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonclicka--dhtmleventonclick"></a><a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK  
 (ドキュメント レベルで処理、 **onclick**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventondataavailablea--dhtmleventondataavailable"></a><a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE  
 (ドキュメント レベルで処理、 **ondataavailable**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventondatasetchangeda--dhtmleventondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventondatasetcompletea--dhtmleventondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn) 
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventondblclicka--dhtmleventondblclick"></a><a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK  
 (ドキュメント レベルで処理、 **ondblclick**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventondragstarta--dhtmleventondragstart"></a><a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART  
 (ドキュメント レベルで処理、 **ondragstart**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonerrorupdatea--dhtmleventonerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE  
 (ドキュメント レベルで処理、**詳細について**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```   
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonfilterchangea--dhtmleventonfilterchange"></a><a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonfocusa--dhtmleventonfocus"></a><a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS  
 処理する (レベル要素)、 **onfocus**イベントです。 これは、非バブル イベントです。  
  
```  
 
DHTML_EVENT_ONFOCUS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonhelpa--dhtmleventonhelp"></a><a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP  
 (ドキュメント レベルで処理、`onhelp`で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONHELP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeydowna--dhtmleventonkeydown"></a><a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN  
 (ドキュメント レベルで処理、 **onkeydown**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeypressa--dhtmleventonkeypress"></a><a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS  
 (ドキュメント レベルで処理、 **onkeypress**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeyupa--dhtmleventonkeyup"></a><a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP  
 (ドキュメント レベルで処理、 **onkeyup**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONKEYUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmousedowna--dhtmleventonmousedown"></a><a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN  
 (ドキュメント レベルで処理、 **onmousedown**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmousemovea--dhtmleventonmousemove"></a><a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE  
 (ドキュメント レベルで処理、`onmousemove`で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseouta--dhtmleventonmouseout"></a><a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT  
 (ドキュメント レベルで処理、 **onmouseout**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseovera--dhtmleventonmouseover"></a><a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER  
 (ドキュメント レベルで処理、 **onmouseover**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseupa--dhtmleventonmouseup"></a><a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP  
 (ドキュメント レベルで処理、 **onmouseup**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonresizea--dhtmleventonresize"></a><a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE  
 処理する (レベル要素)、 **onresize**イベントです。 これは、非バブル イベントです。  
  
```  
 
DHTML_EVENT_ONRESIZE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonrowentera--dhtmleventonrowenter"></a><a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONROWENTER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonrowexita--dhtmleventonrowexit"></a><a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventonselectstarta--dhtmleventonselectstart"></a><a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART  
 (ドキュメント レベルで処理、 **onselectstart**で識別される HTML 要素でイベントの発生元`elemName`します。  
  
```  
 
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベント ソーシングの HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedhtmleventtaga--dhtmleventtag"></a><a name="dhtml_event_tag"></a>DHTML_EVENT_TAG  
 (ドキュメント レベル) で識別されるイベントを処理`dispid`送信元では、HTML 要素で識別される HTML タグを持つ`elemName`です。  
  
```   
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 イベントを処理するためのディスパッチの ID。  
  
 `elemName`  
 イベントのソース HTML 要素の HTML タグ。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-nameenddhtmleventmapa--enddhtmleventmap"></a><a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP  
 DHTML イベント マップの最後をマークします。  
  
```   
END_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用する必要があります[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namebegindhtmlurleventmapa--begindhtmlurleventmap"></a><a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP  
 マルチページ ダイアログは、DHTML および URL のイベント マップの定義を開始します。  
  
```  
BEGIN_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>コメント  
 Put`BEGIN_DHTML_URL_EVENT_MAP`の実装ファイルで、[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)-クラスを派生します。 それに続く[DHTML イベント マップの埋め込み](#begin_embed_dhtml_event_map)と[URL エントリ](#begin_url_entries)を閉じたと[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)します。 含める、 [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)クラス定義内でのマクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&196;](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namebeginembeddhtmleventmapa--beginembeddhtmleventmap"></a><a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP  
 マルチページ ダイアログは、埋め込みの DHTML イベント マップの定義を開始します。  
  
```  
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 イベント マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)します。 埋め込みの DHTML イベント マップが内に配置する必要があります、 [DHTML および URL のイベント マップ](#begin_dhtml_url_event_map))。  
  
 *マップ名*  
 イベント マップを持つページを指定します。 これに対応*mapName*で、 [URL_EVENT_ENTRY](#url_event_entry)マクロが実際に URL または HTML リソースを定義します。  
  
### <a name="remarks"></a>コメント  
 複数の HTML ページは、それぞれには、DHTML イベントを発生させて、DHTML マルチページ ダイアログは、構成するため、埋め込みイベント マップは、イベントをページごとのハンドラーにマップに使用されます。  
  
 DHTML と URL のイベント マップ内の埋め込みイベント マップから成る、`BEGIN_EMBED_DHTML_EVENT_MAP`マクロが続く[DHTML_EVENT](dhtml-event-maps.md#dhtml_event)マクロと[END_EMBED_DHTML_EVENT_MAP](dhtml-event-maps.md#end_embed_dhtml_event_map)マクロです。  
  
 各埋め込みイベント マップでは、対応する必要があります[URL イベント エントリ](#url_event_entry)にマップする*mapName* (で指定されている`BEGIN_EMBED_DHTML_EVENT_MAP`) の URL または html 形式のリソースにします。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namebeginurlentriesa--beginurlentries"></a><a name="begin_url_entries"></a>BEGIN_URL_ENTRIES  
 マルチページ ダイアログは、URL のイベント エントリ マップの定義を開始します。  
  
```  
BEGIN_URL_ENTRIES(className)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 URL のイベント エントリのマップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)します。 内部 URL イベント エントリのマップがある必要があります、 [DHTML および URL のイベント マップ](#begin_dhtml_url_event_map))。  
  
### <a name="remarks"></a>コメント  
 マルチページ DHTML ダイアログは、複数の HTML ページで構成され、ので URL イベント エントリを使用して、Url または html 形式にマップを対応するリソース[DHTML イベント マップの埋め込み](#begin_embed_dhtml_event_map)します。 Put`URL_EVENT_ENTRY`間でのマクロ`BEGIN_URL_ENTRIES`と[END_URL_ENTRIES](#end_url_entries)マクロです。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-namedeclaredhtmlurleventmapa--declaredhtmlurleventmap"></a><a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP  
 クラス定義に DHTML および URL のイベント マップを宣言します。  
  
```  
DECLARE_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>コメント  
 このマクロの定義で使用するのには、[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)-クラスを派生します。  
  
 DHTML と URL イベント マップに含まれる[DHTML イベント マップの埋め込み](#begin_embed_dhtml_event_map)と[URL イベント エントリ](#begin_url_entries)DHTML イベントをページごとのハンドラーにマップします。 使用[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)マップを実装します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-nameenddhtmlurleventmapa--enddhtmlurleventmap"></a><a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP  
 DHTML と URL のイベント マップの最後をマークします。  
  
```  
END_DHTML_URL_EVENT_MAP(className)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 イベント マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)します。 これと同じ`className`に対応する[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)マクロです。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-nameendembeddhtmleventmapa--endembeddhtmleventmap"></a><a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP  
 埋め込みの DHTML イベント マップの最後をマークします。  
  
```  
END_EMBED_DHTML_EVENT_MAP()  
 
```  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-nameendurlentriesa--endurlentries"></a><a name="end_url_entries"></a>END_URL_ENTRIES  
 URL のイベント エントリ マップの最後をマークします。  
  
```  
END_URL_ENTRIES()  
 
```  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="a-nameurlevententrya--urlevententry"></a><a name="url_event_entry"></a>URL_EVENT_ENTRY  
 マルチページ ダイアログは、内のページに、URL または HTML リソースをマップします。  
  
```  
URL_EVENT_ENTRY(className, url,  mapName)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 URL のイベント エントリのマップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)します。 内部 URL イベント エントリのマップがある必要があります、 [DHTML および URL のイベント マップ](#begin_dhtml_url_event_map))。  
  
 *url*  
 ページの URL または HTML リソースです。  
  
 *マップ名*  
 URL がページを指定*url*します。 これに対応*mapName*で、 [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)マップをこのページのイベントを行うマクロです。  
  
### <a name="remarks"></a>コメント  
 このページは、次のような HTML リソース場合*url*リソースの ID 番号 (つまり、「123」の 123 いないまたは ID_HTMLRES1) の文字列形式を指定する必要があります。  
  
 ページ id *mapName*は、任意のシンボルを使用してリンクに埋め込まれた URL イベント エントリのマップに DHTML イベント マップします。 DHTML と URL のイベント マップにスコープに制限されることはできます。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)します。  

  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

