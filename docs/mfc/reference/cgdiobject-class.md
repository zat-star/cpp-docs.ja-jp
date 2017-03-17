---
title: "CGdiObject クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- brushes, base class for
- fonts, base class for
- regions, base class for
- pens, base class for
- palettes, base class for
- CGdiObject class
- GDI objects, base class for
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
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
ms.openlocfilehash: 7fb0cd49c6a20263a5cae305b7f08f2733033ff2
ms.lasthandoff: 02/24/2017

---
# <a name="cgdiobject-class"></a>CGdiObject クラス
ビットマップ、領域、ブラシ、ペン、パレット、フォントなどの Windows のさまざまな種類のグラフィックス デバイス インターフェイス (GDI) の基底クラスを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CGdiObject : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::CGdiObject](#cgdiobject)|`CGdiObject` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::Attach](#attach)|Windows GDI オブジェクトをアタッチ、`CGdiObject`オブジェクトです。|  
|[CGdiObject::CreateStockObject](#createstockobject)|Windows の組み込みのストック ペン、ブラシ、フォントのいずれかを識別するハンドルを取得します。|  
|[CGdiObject::DeleteObject](#deleteobject)|Windows GDI オブジェクトにアタッチされて削除、`CGdiObject`オブジェクトに関連付けられているすべてのシステムの記憶域を解放することによって、メモリからのオブジェクト。|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|一時的な削除`CGdiObject`によって作成されたオブジェクト`FromHandle`します。|  
|[CGdiObject::Detach](#detach)|Windows GDI オブジェクトからのデタッチ、`CGdiObject`オブジェクトし、Windows GDI オブジェクトへのハンドルを返します。|  
|[CGdiObject::FromHandle](#fromhandle)|ポインターを返す、 `CGdiObject` Windows GDI オブジェクトへのハンドルを指定したオブジェクト。|  
|[CGdiObject::GetObject](#getobject)|接続されている Windows GDI オブジェクトを示すデータを使用して、バッファーを塗りつぶし、`CGdiObject`オブジェクトです。|  
|[CGdiObject::GetObjectType](#getobjecttype)|GDI オブジェクトの種類を取得します。|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|返します。`m_hObject`しない限り、`this`は`NULL`その場合は`NULL`が返されます。|  
|[CGdiObject::UnrealizeObject](#unrealizeobject)|ブラシの原点をリセットまたは論理パレットをリセットします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|2 つの GDI オブジェクトが等しく論理的にないかどうかを判断します。|  
|[CGdiObject::operator = =](#operator_eq_eq)|GDI の&2; つのオブジェクトが論理的に等しいかどうかを判断します。|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|取得、`HANDLE`アタッチされた Windows GDI オブジェクトにします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|A`HANDLE`を含む、 `HBITMAP`、 `HPALETTE`、 `HRGN`、 `HBRUSH`、 `HPEN`、または`HFONT`にこのオブジェクトにアタッチします。|  
  
## <a name="remarks"></a>コメント  
 作成しないで、`CGdiObject`直接します。 代わりに、オブジェクトを作成するその派生クラスのいずれかからなど`CPen`または`CBrush`です。  
  
 詳細については`CGdiObject`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="attach"></a>CGdiObject::Attach  
 Windows GDI オブジェクトをアタッチ、`CGdiObject`オブジェクトです。  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 A `HANDLE` Windows GDI オブジェクト (たとえば、`HPEN`または`HBRUSH`)。  
  
### <a name="return-value"></a>戻り値  
 添付ファイルが正常に終了した場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="cgdiobject"></a>CGdiObject::CGdiObject  
 `CGdiObject` オブジェクトを構築します。  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>コメント  
 作成しないで、`CGdiObject`直接します。 代わりに、オブジェクトを作成するその派生クラスのいずれかからなど`CPen`または**Cbrush**します。  
  
##  <a name="createstockobject"></a>CGdiObject::CreateStockObject  
 定義済みのストック Windows GDI ペン、ブラシ、フォントのいずれかを識別するハンドルを取得しに GDI オブジェクトをアタッチ、`CGdiObject`オブジェクトです。  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 目的のストック オブジェクトの種類を指定する定数。 パラメーターを参照してください*fnObject*の[GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]適切な値の詳細についてです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 クラスを派生クラスのいずれかでは、この関数の呼び出しなどの Windows GDI オブジェクトの種類に対応`CPen`ストック ペン用です。  
  
##  <a name="deleteobject"></a>CGdiObject::DeleteObject  
 Windows GDI オブジェクトに関連付けられているすべてのシステムの記憶域を解放して、メモリから、アタッチされた Windows GDI オブジェクトを削除します。  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>戻り値  
 GDI オブジェクトが正常に削除された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関連付けられている記憶域、`CGdiObject`オブジェクトがこの呼び出しによる受けません。 アプリケーションが呼び出さないで`DeleteObject`上、`CGdiObject`デバイス コンテキストに現在選択されているオブジェクト。  
  
 ブラシのパターンが削除されると、ブラシに関連付けられているビットマップは削除されません。 ビットマップは個別に削除する必要があります。  
  
##  <a name="deletetempmap"></a>CGdiObject::DeleteTempMap  
 により自動的に呼び出さ、`CWinApp`アイドル ハンドラー`DeleteTempMap`一時的な削除`CGdiObject`によって作成されたオブジェクト`FromHandle`します。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>コメント  
 `DeleteTempMap`一時的に接続されている Windows GDI オブジェクトをデタッチ`CGdiObject`オブジェクトを削除する前に、`CGdiObject`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&175;](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>CGdiObject::Detach  
 Windows GDI オブジェクトからのデタッチ、`CGdiObject`オブジェクトし、Windows GDI オブジェクトへのハンドルを返します。  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>戻り値  
 A`HANDLE`デタッチ済み以外の場合をオブジェクトに、Windows GDI **NULL** GDI オブジェクトがアタッチされていない場合。  
  
##  <a name="fromhandle"></a>CGdiObject::FromHandle  
 ポインターを返す、 `CGdiObject` Windows GDI オブジェクトへのハンドルを指定したオブジェクト。  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 A `HANDLE` Windows GDI オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CGdiObject`一時的または永続的にある場合があります。  
  
### <a name="remarks"></a>コメント  
 場合、`CGdiObject`オブジェクトが、Windows GDI のオブジェクトが一時的に既にアタッチされていない`CGdiObject`オブジェクトが作成され、接続されています。  
  
 この一時`CGdiObject`オブジェクトは、次のアプリケーションが、すべての一時的なグラフィック オブジェクトを削除する時にそのイベントのループのアイドル時間までのみ有効です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に一時オブジェクトが有効でのみことです。  
  
##  <a name="getobject"></a>CGdiObject::GetObject  
 指定したオブジェクトを定義するデータをバッファーします。  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nCount`  
 コピーするバイト数を指定、`lpObject`バッファー。  
  
 `lpObject`  
 情報を受信するユーザーが指定したバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 バイト数を取得します。それ以外の場合、エラーの場合は 0 が発生します。  
  
### <a name="remarks"></a>コメント  
 関数は、次の一覧に示すように、データ構造体の型は、グラフィック オブジェクトの種類によって異なります。 を取得します。  
  
|オブジェクト|バッファーの種類|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[ビットマップ](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|サポートされていません|  
  
 オブジェクトがある場合、`CBitmap`オブジェクト、`GetObject`幅、高さ、およびビットマップの色の書式情報のみを返します。 使用して実際のビットを取得できる[列](../../mfc/reference/cbitmap-class.md#getbitmapbits)します。  
  
 オブジェクトがある場合、`CPalette`オブジェクト、`GetObject`取得、 **WORD**パレット内のエントリの数を指定します。 この関数を取得することはありません、[保持](http://msdn.microsoft.com/library/windows/desktop/dd145040)パレットを定義する構造体。 アプリケーションを呼び出してパレット エントリに関する情報を取得することができます[CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries)します。  
  
##  <a name="getobjecttype"></a>CGdiObject::GetObjectType  
 GDI オブジェクトの種類を取得します。  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、オブジェクトの種類それ以外の場合 0 を返します。 値は、次のいずれかになります。  
  
- **OBJ_BITMAP**ビットマップ  
  
- **OBJ_BRUSH**ブラシ  
  
- **OBJ_FONT**フォント  
  
- **OBJ_PAL**パレット  
  
- **OBJ_PEN**ペン  
  
- **OBJ_EXTPEN**拡張ペン  
  
- **OBJ_REGION**地域  
  
- **OBJ_DC**デバイス コンテキスト  
  
- **OBJ_MEMDC**メモリ デバイス コンテキスト  
  
- **OBJ_METAFILE**メタファイル  
  
- **OBJ_METADC**メタファイル デバイス コンテキスト  
  
- **OBJ_ENHMETAFILE**拡張メタファイル  
  
- **OBJ_ENHMETADC**拡張メタファイル デバイス コンテキスト  
  
##  <a name="getsafehandle"></a>CGdiObject::GetSafeHandle  
 返します。`m_hObject`しない限り、**この**は**NULL**その場合は**NULL**が返されます。  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`HANDLE`アタッチされた Windows GDI のオブジェクトにそれ以外の場合**NULL**オブジェクトがアタッチされていない場合。  
  
### <a name="remarks"></a>コメント  
 一般的なハンドル インターフェイス パラダイムの一部であり、 **NULL**ハンドルが無効であるか特殊な値です。  
  
### <a name="example"></a>例  
  例を参照してください[CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled)します。  
  
##  <a name="m_hobject"></a>CGdiObject::m_hObject  
 A`HANDLE`を含む、 `HBITMAP`、 **HRGN**、 `HBRUSH`、 `HPEN`、 `HPALETTE`、または**HFONT**にこのオブジェクトにアタッチします。  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>CGdiObject::operator! =  
 2 つの GDI オブジェクトが等しく論理的にないかどうかを判断します。  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `obj`  
 既存へのポインター`CGdiObject`します。  
  
### <a name="remarks"></a>コメント  
 左側にある GDI オブジェクトが右側にある GDI オブジェクトと等しくないかどうかを判断します。  
  
##  <a name="operator_eq_eq"></a>CGdiObject::operator = =  
 GDI の&2; つのオブジェクトが論理的に等しいかどうかを判断します。  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `obj`  
 既存への参照を`CGdiObject`します。  
  
### <a name="remarks"></a>コメント  
 左側にある GDI オブジェクトが右側にある GDI オブジェクトと等しいかどうかを判断します。  
  
##  <a name="operator_hgdiobj"></a>CGdiObject::operator HGDIOBJ  
 取得、`HANDLE`アタッチされた Windows GDI のオブジェクトにそれ以外の場合**NULL**オブジェクトがアタッチされていない場合。  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>CGdiObject::UnrealizeObject  
 ブラシの原点をリセットまたは論理パレットをリセットします。  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 中に`UnrealizeObject`のメンバー関数、`CGdiObject`クラス、それを呼び出す上でのみ`CBrush`または`CPalette`オブジェクトです。  
  
 `CBrush`オブジェクト、`UnrealizeObject`は、次回のデバイス コンテキストに選択されている指定されたブラシの原点をリセットするようにします。 オブジェクトがある場合、`CPalette`オブジェクト、`UnrealizeObject`いた、以前認識していない場合と同様に、パレットを実現するシステムに指示します。 次に、アプリケーションを呼び出すとき、 [:realizepalette](../../mfc/reference/cdc-class.md#realizepalette)指定のパレットでは、システム関数は、システム パレットにある論理パレットを完全に再配置します。  
  
 `UnrealizeObject`ストック オブジェクトと関数は使用されません。 `UnrealizeObject`新しいブラシの原点が設定されているときに、関数を呼び出す必要があります (によって、 [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg)関数)。 `UnrealizeObject`現在選択されているブラシまたはディスプレイ コンテキストの現在選択されているパレットの関数を呼び出すことがない必要があります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBitmap クラス](../../mfc/reference/cbitmap-class.md)   
 [CBrush クラス](../../mfc/reference/cbrush-class.md)   
 [CFont クラス](../../mfc/reference/cfont-class.md)   
 [CPalette クラス](../../mfc/reference/cpalette-class.md)   
 [CPen クラス](../../mfc/reference/cpen-class.md)   
 [CRgn クラス](../../mfc/reference/crgn-class.md)

