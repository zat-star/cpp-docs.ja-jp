---
title: "COleDataSource クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDataSource
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [C++], MFC support
- Clipboard [C++], OLE support
- uniform data transfer
- OLE [C++], uniform data transfer
- Clipboard [C++], MFC support
- OLE Clipboard [C++], support
- IDataObject, MFC encapsulation
- data transfer [C++], OLE
- COleDataSource class
- OLE data transfer [C++]
- uniform data transfer, OLE
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
caps.latest.revision: 23
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
ms.openlocfilehash: cd8f30c3edd7d26b254e7f4a6f153ab0b2fc96da
ms.lasthandoff: 02/24/2017

---
# <a name="coledatasource-class"></a>COleDataSource クラス
OLE アプリケーションが、クリップボード操作やドラッグ アンド ドロップ操作のようなデータ転送操作中に用意するデータを置くキャッシュの役目をします。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](#coledatasource)|`COleDataSource` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[取得](#cachedata)|使用して指定された形式でデータを提供する**STGMEDIUM**構造体。|  
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|使用して指定された形式でデータを提供する`HGLOBAL`です。|  
|[COleDataSource::DelayRenderData](#delayrenderdata)|遅延レンダリングを使用して、指定された形式でデータを提供します。|  
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|指定された形式でデータを提供する`CFile`ポインター。|  
|[COleDataSource::DelaySetData](#delaysetdata)|サポートされているすべての形式に対して呼び出す`OnSetData`します。|  
|[された](#dodragdrop)|データ ソースにドラッグ アンド ドロップ操作を実行します。|  
|[COleDataSource::Empty](#empty)|空にして、`COleDataSource`データのオブジェクト。|  
|[COleDataSource::FlushClipboard](#flushclipboard)|すべてのデータをクリップボードにレンダリングします。|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|クリップボードに配置されるデータがあることを確認します。|  
|[と](#onrenderdata)|遅延レンダリングの一部としてデータを取得します。|  
|[と](#onrenderfiledata)|データを取得、`CFile`遅延レンダリングの一部として。|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|データを取得、`HGLOBAL`遅延レンダリングの一部として。|  
|[COleDataSource::OnSetData](#onsetdata)|内のデータを交換できると呼ばれる、`COleDataSource`オブジェクトです。|  
|[COleDataSource::SetClipboard](#setclipboard)|場所、`COleDataSource`オブジェクトをクリップボードにコピーします。|  
  
## <a name="remarks"></a>コメント  
 OLE のデータ ソースを直接作成することができます。 または、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)と[実際](../../mfc/reference/coleserveritem-class.md)クラスに対応 OLE データ ソースを作成、`CopyToClipboard`と`DoDragDrop`メンバー関数。 参照してください[COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard)を簡単に説明します。 オーバーライド、`OnGetClipboardData`の OLE データ ソース内のデータに追加のクリップボード形式を追加するクライアント項目またはサーバー項目クラスのメンバー関数が作成された、`CopyToClipboard`または`DoDragDrop`メンバー関数。  
  
 データの転送を準備するときにこのクラスのオブジェクトを作成、データの最適な方法を使ってデータを入力してください。 データ ソースに挿入する方法を直接受けますのデータがすぐに入力するかどうか (即時レンダリング)、またはオンデマンドで (レンダリングを遅延) です。 クリップボードの形式が使用するクリップボードの形式を渡すことによってデータを提供するすべての (省略可能[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造)、呼び出す[に](#delayrenderdata)します。  
  
 データ ソースおよびデータ転送の詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)します。 さらに、アーティクル[クリップボードのトピック](../../mfc/clipboard.md)OLE クリップボード機構について説明します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-namecachedataa--coledatasourcecachedata"></a><a name="cachedata"></a>取得  
 提供されるデータのデータ転送操作の形式を指定するには、この関数を呼び出します。  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 クリップボードの形式をデータが提供されるのです。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)に指定された形式でデータを含む構造体。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)提供されるデータの形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**、既定値は、他のフィールドの使用、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は即時レンダリングを使用して提供するために、データを指定してください。 データが必要になるまでにキャッシュされます。  
  
 使用してデータを提供する[STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)構造体。 使用することも、`CacheGlobalData`データの量を指定している場合、メンバー関数がそれほど効率的に使用して送信する、`HGLOBAL`です。  
  
 呼び出しの後に`CacheData`、 **ptd**のメンバー`lpFormatEtc`の内容と`lpStgMedium`呼び出し元ではなく、データ オブジェクトが所有します。  
  
 遅延レンダリングを呼び出す、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理される、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 詳細については、次を参照してください。、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体に、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namecacheglobaldataa--coledatasourcecacheglobaldata"></a><a name="cacheglobaldata"></a>COleDataSource::CacheGlobalData  
 提供されるデータのデータ転送操作の形式を指定するには、この関数を呼び出します。  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 クリップボードの形式をデータが提供されるのです。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 *hGlobal*  
 指定された形式のデータを含むグローバル メモリ ブロックへのハンドルします。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)提供されるデータの形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**、既定値は、他のフィールドの使用、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は、関数を呼び出すときに、データを指定する必要がありますので、即時レンダリングを使用してデータを提供します。データが必要になるまでにキャッシュされます。 使用して、`CacheData`データまたは構造化された記憶域メディアを必要とするかどうかの消費量を指定している場合、メンバー関数。  
  
 遅延レンダリングを呼び出す、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理される、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namecoledatasourcea--coledatasourcecoledatasource"></a><a name="coledatasource"></a>COleDataSource::COleDataSource  
 `COleDataSource` オブジェクトを構築します。  
  
```  
COleDataSource();
```  
  
##  <a name="a-namedelayrenderdataa--coledatasourcedelayrenderdata"></a><a name="delayrenderdata"></a>COleDataSource::DelayRenderData  
 提供されるデータのデータ転送操作の形式を指定するには、この関数を呼び出します。  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 クリップボードの形式をデータが提供されるのです。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)提供されるデータの形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**、既定値は、他のフィールドの使用、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は、データがすぐに指定されていないため、遅延レンダリングを使用してデータを提供します。 [は](#onrenderdata)または[によって](#onrenderglobaldata)データを要求するメンバー関数が呼び出されます。  
  
 データを提供しようとしていない場合は、この関数を使用して、`CFile`オブジェクトです。 使用してデータを指定する場合、`CFile`オブジェクトを呼び出し、 [DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理される、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 即時レンダリングを呼び出す、 [CacheData](#cachedata)または[使う](#cacheglobaldata)メンバー関数。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namedelayrenderfiledataa--coledatasourcedelayrenderfiledata"></a><a name="delayrenderfiledata"></a>COleDataSource::DelayRenderFileData  
 提供されるデータのデータ転送操作の形式を指定するには、この関数を呼び出します。  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 クリップボードの形式をデータが提供されるのです。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)提供されるデータの形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**、既定値は、他のフィールドの使用、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は、データがすぐに指定されていないため、遅延レンダリングを使用してデータを提供します。 [可変](#onrenderfiledata)データを要求するメンバー関数が呼び出されます。  
  
 使用する場合は、この関数を使用して、`CFile`データを提供するオブジェクト。 使用しようとしていない場合、`CFile`オブジェクトを呼び出す、[に](#delayrenderdata)メンバー関数。 詳細については遅延レンダリングの MFC で処理される、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 即時レンダリングを呼び出す、 [CacheData](#cachedata)または[使う](#cacheglobaldata)メンバー関数。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namedelaysetdataa--coledatasourcedelaysetdata"></a><a name="delaysetdata"></a>COleDataSource::DelaySetData  
 この関数では、データ ソースの内容の変更をサポートします。  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 クリップボードの形式がデータを配置します。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)は、データの置き換えられる形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**、既定値は、他のフィールドの使用、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 [データ変更](#onsetdata)が、このような場合に、フレームワークによって呼び出されます。 フレームワークには、元のデータ ソースが返されるときにだけ使用[は](../../mfc/reference/coleserveritem-class.md#getdatasource)です。 場合`DelaySetData`が呼び出されない、`OnSetData`関数は呼び出されません。 `DelaySetData`クリップボードの内容が各呼び出す必要がありますか**FORMATETC**をサポートする形式。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namedodragdropa--coledatasourcedodragdrop"></a><a name="dodragdrop"></a>された  
 呼び出す、`DoDragDrop`で通常、このデータ ソースのドラッグ アンド ドロップ操作を実行するメンバー関数、 [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)ハンドラー。  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwEffects`  
 ドラッグ アンド ドロップ操作ができるこのデータ ソースで。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_COPY`コピー操作を実行できます。  
  
- `DROPEFFECT_MOVE`移動操作を実行する可能性があります。  
  
- `DROPEFFECT_LINK`ドロップされたデータから、元のデータへのリンクを確立でした。  
  
- `DROPEFFECT_SCROLL`ドラッグのスクロール操作が行われる可能性を示します。  
  
 `lpRectStartDrag`  
 実際には、ドラッグの開始位置を定義する四角形へのポインター。 詳細については、「解説」を参照してください。  
  
 *pDropSource*  
 ドロップ ソースへのポインター。 場合**NULL**の既定の実装、 [COleDropSource](../../mfc/reference/coledropsource-class.md)が適用されます。  
  
### <a name="return-value"></a>戻り値  
 ドロップのドラッグ アンド ドロップ操作によって生成される結果それ以外の場合`DROPEFFECT_NONE`場合は、操作は、指定された四角形を終了する前に、ユーザーがマウス ボタンを解放するために決してが開始します。  
  
### <a name="remarks"></a>コメント  
 ドラッグ アンド ドロップ操作はすぐに開始されません。 マウス カーソルが指定された四角形のままになるまで待機している`lpRectStartDrag`または指定したミリ秒数が経過するまでです。 場合`lpRectStartDrag`は**NULL**、四角形のサイズは&1; ピクセルです。  
  
 遅延時間は、レジストリ キーの設定によって指定されます。 遅延時間を変更するにを呼び出して[CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[cwinapp::writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)します。 遅延時間を指定しない場合は、200 ミリ秒の既定値が使用されます。 ドラッグ遅延時間は、次のように格納されます。  
  
-   Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay に格納されます。  
  
-   Windows 3.x ドラッグ遅延時間は、WIN に格納されます。INI ファイルの [Windows} セクション。  
  
-   Windows 95/98 ドラッグ遅延時間は、WIN のキャッシュされたバージョンに格納されます。INI します。  
  
 遅延の情報は、レジストリに格納されている方法の詳細についてはドラッグのか。INI ファイルを参照してください[WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ソースの実装](../../mfc/drag-and-drop-implementing-a-drop-source.md)します。  
  
##  <a name="a-nameemptya--coledatasourceempty"></a><a name="empty"></a>COleDataSource::Empty  
 空には、この関数を呼び出して、`COleDataSource`データのオブジェクト。  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>コメント  
 両方がキャッシュされると、再利用できるように、遅延レンダリングされた形式が空にします。  
  
 詳細については、次を参照してください。 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameflushclipboarda--coledatasourceflushclipboard"></a><a name="flushclipboard"></a>COleDataSource::FlushClipboard  
 クリップボードにし、アプリケーションのシャット ダウンした後、クリップボードからデータをペーストできますし、データを表示します。  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>コメント  
 使用[SetClipboard](#setclipboard)をクリップボードにデータを格納します。  
  
##  <a name="a-namegetclipboardownera--coledatasourcegetclipboardowner"></a><a name="getclipboardowner"></a>COleDataSource::GetClipboardOwner  
 以降、クリップボードのデータが変更されているかどうかを判断[SetClipboard](#setclipboard)と、最後に呼び出された場合は、現在の所有者を識別します。  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>戻り値  
 現在、クリップボードにデータ ソースまたは**NULL**クリップボードにコピーがない場合、またはクリップボードが呼び出し元のアプリケーションによって所有されていない場合。  
  
##  <a name="a-nameonrenderdataa--coledatasourceonrenderdata"></a><a name="onrenderdata"></a>と  
 指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データが返される構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を呼び出す[関数](#onrenderfiledata)または[によって](#onrenderglobaldata)ファイルまたはメモリにはそれぞれ、指定されたストレージ メディア場合。 これらの形式のどちらを指定した場合、既定の実装は 0 を返し、何もしません。 詳細については遅延レンダリングの MFC で処理される、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 場合`lpStgMedium` ->  *tymed*は**TYMED_NULL**、 **STGMEDIUM**割り当てられで指定された入力*tymed-> lpFormatEtc*します。 ない場合は**TYMED_NULL**、 **STGMEDIUM**のデータが配置を入力する必要があります。  
  
 これは、高度なオーバーライドします。 要求された形式と媒体でデータを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンのいずれかを上書きする可能性があります。 データが小さなサイズに固定と容量の場合は、オーバーライド`OnRenderGlobalData`します。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`します。  
  
 詳細については、次を参照してください。、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体、 [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227)列挙型の場合と[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
##  <a name="a-nameonrenderfiledataa--coledatasourceonrenderfiledata"></a><a name="onrenderfiledata"></a>と  
 指定されたストレージ メディアがファイルであるときに、指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `pFile`  
 指す、 [CFile](../../mfc/reference/cfile-class.md)データが表示されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を返すだけ**FALSE**します。  
  
 これは、高度なオーバーライドします。 要求された形式と媒体でデータを提供するには、この関数をオーバーライドします。 によって、データは、代わりにこの関数の他のバージョンのいずれかをオーバーライドすることができます。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)です。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`します。 詳細については遅延レンダリングの MFC で処理される、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造と[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
##  <a name="a-nameonrenderglobaldataa--coledatasourceonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleDataSource::OnRenderGlobalData  
 指定されたストレージ メディアがグローバル メモリのときに、指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `phGlobal`  
 データが返されるグローバル メモリへのハンドルへのポインター。 いずれかがまだ割り当てられていない場合、このパラメーターを指定できます**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を返すだけ**FALSE**します。  
  
 場合`phGlobal`は**NULL**から、新規`HGLOBAL`割り当てられで返される必要があります`phGlobal`します。 それ以外の場合、`HGLOBAL`によって指定された`phGlobal`データが格納される必要があります。 内に配置するデータの量、`HGLOBAL`メモリ ブロックの現在のサイズを超えることはできません。 また、ブロックより大きなサイズに再割り当てできることはできません。  
  
 これは、高度なオーバーライドします。 要求された形式と媒体でデータを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンのいずれかを上書きする可能性があります。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)です。 データをファイル内や可変サイズのオーバーライド[可変](#onrenderfiledata)します。 詳細については遅延レンダリングの MFC で処理される、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造と[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
##  <a name="a-nameonsetdataa--coledatasourceonsetdata"></a><a name="onsetdata"></a>COleDataSource::OnSetData  
 内のデータを設定またはフレームワークによって呼び出され、`COleDataSource`オブジェクトを指定した形式でします。  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データを交換する形式を指定します。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)の現在の内容を置き換えるデータを含む構造体、`COleDataSource`オブジェクトです。  
  
 `bRelease`  
 関数呼び出しの完了後、ストレージ メディアの所有権を持つことを示します。 呼び出し元では、ストレージ メディアの代わりに割り当てられているリソースを解放する担当者を決定します。 呼び出し元がこれを設定してで`bRelease`します。 場合`bRelease`は&0; 以外、データ ソースは所有権を取得、使用が完了すると、メディアを解放します。 `bRelease` 0 は、呼び出し元が所有権を保持およびデータ ソースは、呼び出しの間でのみストレージ メディアを使用できます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 正常に取得するまで、データ ソースによるデータの所有権はなりません。 つまり、その所有権を持ちません場合`OnSetData`0 を返します。 呼び出してストレージ メディアを解放してデータ ソースに所有権がある場合は、パラメーター、 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491)関数です。  
  
 既定の実装では、何も行われません。 指定した形式でデータを置換するには、この関数をオーバーライドします。 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体と[ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491)と[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)関数、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
##  <a name="a-namesetclipboarda--coledatasourcesetclipboard"></a><a name="setclipboard"></a>COleDataSource::SetClipboard  
 含まれているデータを格納、`COleDataSource`オブジェクトを次の関数のいずれかを呼び出した後、クリップボードにコピーします。 [CacheData](#cachedata)、[使う](#cacheglobaldata)、[に](#delayrenderdata)、または[DelayRenderFileData](#delayrenderfiledata)します。  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [されます。](../../mfc/reference/coledataobject-class.md)

