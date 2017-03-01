---
title: "される |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDataObject
- COleDataObject
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [C++], MFC support
- Clipboard [C++], OLE support
- uniform data transfer
- OLE [C++], uniform data transfer
- Clipboard [C++], MFC support
- OLE Clipboard [C++], support
- IDataObject interface, MFC encapsulation
- data transfer [C++]
- data transfer [C++], OLE
- OLE data transfer [C++]
- COleDataObject class
- uniform data transfer, OLE
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
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
ms.openlocfilehash: f30ca208252fe81f1e47d9e8f817cb9137656540
ms.lasthandoff: 02/24/2017

---
# <a name="coledataobject-class"></a>されます。
クリップボードや OLE 埋め込みアイテムからさまざまなフォーマットのデータを取得するときのデータ転送に使用します。クリップボードからデータを取得するときは、ドラッグ アンド ドロップを使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDataObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](#coledataobject)|`COleDataObject` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDataObject::Attach](#attach)|指定した OLE データ オブジェクトをアタッチ、`COleDataObject`です。|  
|[COleDataObject::AttachClipboard](#attachclipboard)|クリップボードのデータ オブジェクトをアタッチします。|  
|[COleDataObject::BeginEnumFormats](#beginenumformats)|1 つまたは複数後続準備`GetNextFormat`呼び出しです。|  
|[COleDataObject::Detach](#detach)|関連付けられたデタッチ`IDataObject`オブジェクトです。|  
|[COleDataObject::GetData](#getdata)|指定された形式で接続されている OLE データ オブジェクトからのデータをコピーします。|  
|[COleDataObject::GetFileData](#getfiledata)|接続されている OLE データ オブジェクトからデータをコピー、`CFile`指定の形式でのポインター。|  
|[COleDataObject::GetGlobalData](#getglobaldata)|接続されている OLE データ オブジェクトからデータをコピー、`HGLOBAL`指定された形式です。|  
|[COleDataObject::GetNextFormat](#getnextformat)|次のデータ形式を返します。|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|データが指定された形式で使用できるかどうかを確認します。|  
|[COleDataObject::Release](#release)|割り当てを解除し、関連付けられているリリース`IDataObject`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `COleDataObject`基本クラスはありません。  
  
 これらのデータ転送には、ソースおよび変換先が含まれます。 オブジェクトとしてデータ ソースが実装されている、 [COleDataSource](../../mfc/reference/coledatasource-class.md)クラスです。 コピー先のアプリケーションのデータがドロップがまたはのオブジェクト、クリップボードから貼り付けの操作を実行するように指示されてするたびに、`COleDataObject`クラスを作成する必要があります。  
  
 このクラスでは、指定された形式でデータが存在するかどうかを確認することができます。 また、使用可能なデータ形式を列挙または指定された書式が使用可能かどうか確認し、推奨される形式でデータを取得できます。 使用など、さまざまな方法でオブジェクトの取得を達成できる、 [CFile](../../mfc/reference/cfile-class.md)、 `HGLOBAL`、または**STGMEDIUM**構造体。  
  
 詳細については、次を参照してください。、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、アプリケーションでデータ オブジェクトを使用して、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `COleDataObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-nameattacha--coledataobjectattach"></a><a name="attach"></a>COleDataObject::Attach  
 この関数に関連付けるには、 `COleDataObject` OLE データ オブジェクトを含むオブジェクト。  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDataObject*  
 OLE データ オブジェクトへのポインター。  
  
 `bAutoRelease`  
 **TRUE** OLE データ オブジェクトである場合リリースされたときに、`COleDataObject`オブジェクトが破棄された**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameattachclipboarda--coledataobjectattachclipboard"></a><a name="attachclipboard"></a>COleDataObject::AttachClipboard  
 クリップボードに置かれているデータ オブジェクトをアタッチするには、この関数を呼び出して、`COleDataObject`オブジェクトです。  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  この関数を呼び出すことでは、このデータ オブジェクトが解放されるまでに、クリップボードをロックします。 デストラクターではデータ オブジェクトの解放、`COleDataObject`です。 詳細については、次を参照してください。 [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048)と[CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035)の Win32 ドキュメントです。  
  
##  <a name="a-namebeginenumformatsa--coledataobjectbeginenumformats"></a><a name="beginenumformats"></a>COleDataObject::BeginEnumFormats  
 以降の呼び出しを準備するには、この関数を呼び出す`GetNextFormat`項目からのデータ形式の一覧を取得するためです。  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後`BeginEnumFormats`、このデータ オブジェクトでサポートされている最初の形式の位置を格納します。 連続して呼び出す`GetNextFormat`データ オブジェクトで使用可能な形式の一覧を列挙します。  
  
 指定された形式でデータの可用性を確認するには、使用[COleDataObject::IsDataAvailable](#isdataavailable)します。  
  
 詳細については、次を参照してください。 [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namecoledataobjecta--coledataobjectcoledataobject"></a><a name="coledataobject"></a>COleDataObject::COleDataObject  
 `COleDataObject` オブジェクトを構築します。  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[COleDataObject::Attach](#attach)または[COleDataObject::AttachClipboard](#attachclipboard)他を呼び出す前に行う必要があります`COleDataObject`関数です。  
  
> [!NOTE]
>  ポインターをドラッグ アンド ドロップ ハンドラーのパラメーターの&1; つは、 `COleDataObject`、ドラッグ アンド ドロップをサポートするためにこのコンス トラクターを呼び出す必要はありません。  
  
##  <a name="a-namedetacha--coledataobjectdetach"></a><a name="detach"></a>COleDataObject::Detach  
 デタッチするには、この関数を呼び出して、`COleDataObject`データ オブジェクトを解放せず、関連する OLE データ オブジェクトからのオブジェクト。  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされた OLE データ オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetdataa--coledataobjectgetdata"></a><a name="getdata"></a>COleDataObject::GetData  
 この関数では、指定した形式で項目からデータを取得します。  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが返される形式です。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データを受け取る構造体。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**の他のフィールドの既定値が使用される、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetfiledataa--coledataobjectgetfiledata"></a><a name="getfiledata"></a>COleDataObject::GetFileData  
 作成するには、この関数を呼び出して、`CFile`または`CFile`-派生オブジェクトに指定された形式でデータを取得して、`CFile`ポインター。  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが返される形式です。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**の他のフィールドの既定値が使用される、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 新しいポインター`CFile`または`CFile`-成功した場合は、データを含む派生オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 [中] で、データが格納されている、によって、戻り値が指す実際の型があります`CFile`、 `CSharedFile`、または`COleStreamFile`です。  
  
> [!NOTE]
>  `CFile`によってこの関数の戻り値でアクセスされるオブジェクトには、呼び出し元が所有します。 呼び出し元の役割です**削除**、`CFile`をファイルを閉じる。  
  
 詳細については、次を参照してください。 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetglobaldataa--coledataobjectgetglobaldata"></a><a name="getglobaldata"></a>COleDataObject::GetGlobalData  
 グローバル メモリ ブロックを割り当てるとに指定された形式でデータの取得には、この関数を呼び出して、`HGLOBAL`です。  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが返される形式です。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**の他のフィールドの既定値が使用される、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、データを含むグローバル メモリ ブロックのハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetnextformata--coledataobjectgetnextformat"></a><a name="getnextformat"></a>COleDataObject::GetNextFormat  
 この関数では、繰り返しを項目からデータを取得するために使用できるすべての形式を取得します。  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)関数呼び出しが戻るとき、形式情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 別の形式がある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出した後[COleDataObject::BeginEnumFormats](#beginenumformats)、このデータ オブジェクトでサポートされている最初の形式の位置を格納します。 連続して呼び出す`GetNextFormat`データ オブジェクトで使用可能な形式の一覧を列挙します。 これらの関数を使用して、使用可能な形式の一覧します。  
  
 指定した形式の可用性を確認するには、呼び出す[COleDataObject::IsDataAvailable](#isdataavailable)します。  
  
 詳細については、次を参照してください。 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameisdataavailablea--coledataobjectisdataavailable"></a><a name="isdataavailable"></a>COleDataObject::IsDataAvailable  
 この関数では、特定の形式が OLE アイテムからデータを取得するために使用できるかを判断します。  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 構造体で使用するクリップボード データ形式が指す`lpFormatEtc`します。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows から返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数です。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)目的の形式を記述する構造体。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 ある場合**NULL**の他のフィールドの既定値が使用される、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 指定した形式でデータがある場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は呼び出しの前に`GetData`、 `GetFileData`、または`GetGlobalData`です。  
  
 詳細については、次を参照してください。 [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)します。  
  
##  <a name="a-namereleasea--coledataobjectrelease"></a><a name="release"></a>COleDataObject::Release  
 所有権を解放するには、この関数を呼び出して、 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)が以前関連付けられているオブジェクト、`COleDataObject`オブジェクトです。  
  
```  
void Release();
```  
  
### <a name="remarks"></a>コメント  
 `IDataObject`に関連付けられた、`COleDataObject`を呼び出して**アタッチ**または`AttachClipboard`明示的にまたは framework です。 場合、`bAutoRelease`のパラメーター**アタッチ**は**FALSE**、`IDataObject`オブジェクトは解放されません。 この場合、呼び出し元が解放を担当する、`IDataObject`を呼び出して[:release](http://msdn.microsoft.com/library/windows/desktop/ms682317)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDataSource クラス](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [実際のクラス](../../mfc/reference/coleserveritem-class.md)

