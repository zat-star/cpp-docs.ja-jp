---
title: "OLE コントロールの永続化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
caps.latest.revision: 17
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
ms.openlocfilehash: b8bbf72a1ea16b37dabf88c5d41a34b1a03ba0d1
ms.lasthandoff: 02/24/2017

---
# <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化
OLE コントロールの機能の&1; つはプロパティ永続化 (シリアル化)、OLE コントロールの読み取りまたは書き込みプロパティの値をファイルまたはストリームにできます。 コンテナー アプリケーションでは、シリアル化を使用して、アプリケーションがコントロールを破棄した後も、コントロールのプロパティの値を格納します。 OLE コントロールのプロパティ値はその後、ファイルから読み取ることができますか、ストリームの場合、コントロールの新しいインスタンスが後で作成します。  
  
### <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|バイナリ ラージ オブジェクト (BLOB) データを格納するコントロール プロパティを交換します。|  
|[PX_Bool](#px_bool)|型のコントロール プロパティを交換**BOOL**します。|  
|[PX_Color](#px_color)|コントロールの色のプロパティを交換します。|  
|[PX_Currency](#px_currency)|型のコントロール プロパティを交換**CY**します。|  
|[PX_DataPath](#px_datapath)|型のコントロール プロパティを交換`CDataPathProperty`します。|  
|[PX_Double](#px_double)|型のコントロール プロパティを交換**二重**します。|  
|[PX_Font](#px_font)|コントロールのフォント プロパティを交換します。|  
|[PX_Float](#px_float)|型のコントロール プロパティを交換**float**します。|  
|[PX_IUnknown](#px_iunknown)|未定義の型のコントロールのプロパティを交換します。|  
|[PX_Long](#px_long)|型のコントロール プロパティを交換**長い**します。|  
|[PX_Picture](#px_picture)|コントロールの画像のプロパティを交換します。|  
|[PX_Short](#px_short)|型のコントロール プロパティを交換**短い**します。|  
|[PX_ULong](#px_ulong)|型のコントロール プロパティを交換**ULONG**します。|  
|[PX_UShort](#px_ushort)|型のコントロール プロパティを交換**USHORT**します。|  
|[PXstring](#px_string)|文字の文字列のコントロールのプロパティを交換します。|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|OLE コントロールのフォント プロパティに VBX コントロールのフォント関連プロパティを交換します。|  
  
 さらに、`AfxOleTypeMatchGuid`間で一致の判定に用意されているグローバル関数、`TYPEDESC`と指定された GUID です。  
  
##  <a name="a-namepxbloba--pxblob"></a><a name="px_blob"></a>PX_Blob  
 コントロールの中でこの関数を呼び出す`DoPropExchange`をシリアル化、またはバイナリ ラージ オブジェクト (BLOB) データを格納するプロパティを初期化します。  
  
```  
 
BOOL  
PX_Blob(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    HGLOBAL& 
hBlob  ,  
    HGLOBAL 
hBlobDefault  
= NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `hBlob`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `hBlobDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値は読み取りやで参照される変数に書き込まれる`hBlob` をクリックします。 この変数を初期化する必要があります**NULL**最初を呼び出す前に`PX_Blob`を最初に (通常は、そのため、コントロールのコンス トラクターで)。 場合`hBlobDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールの初期化またはシリアル化プロセスが失敗したときに使用されます。  
  
 ハンドル`hBlob`と`hBlobDefault`次を含むメモリのブロックを参照してください。  
  
-   A`DWORD`直後の後に、バイナリ データの長さ、(バイト単位) が含まれています  
  
-   実際のバイナリ データを格納しているメモリ ブロック。  
  
 注意`PX_Blob`、Windows を使用してメモリが割り当てられる[GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) API、BLOB 型のプロパティを読み込むときにします。 このメモリの解放を担当しています。 したがって、コントロールのデストラクターを呼び出す必要があります[GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)ハンドルを解放する任意の型が BLOB のプロパティをコントロールに割り当てられたメモリがアップします。  
  
##  <a name="a-namepxboola--pxbool"></a><a name="px_bool"></a>PX_Bool  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を**BOOL**します。  
  
```  
 
BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& bValue);

BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& 
bValue  ,  
    BOOL bDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `bValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `bDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値は読み取りやで参照される変数に書き込まれる`bValue` をクリックします。 場合`bDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxcolora--pxcolor"></a><a name="px_color"></a>PX_Color  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を**OLE_COLOR**します。  
  
```  
 
BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& 
clrValue  ,  
    OLE_COLOR 
clrDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `clrValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `clrDefault`  
 コントロールの開発者によって定義されている、プロパティの既定値。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値は読み取りやで参照される変数に書き込まれる`clrValue` をクリックします。 場合`clrDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxcurrencya--pxcurrency"></a><a name="px_currency"></a>PX_Currency  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を**通貨**します。  
  
```  
 
BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& cyValue);

BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& 
cyValue  ,  
    CY cyDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `cyValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `cyDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値は読み取りやで参照される変数に書き込まれる`cyValue` をクリックします。 場合`cyDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxdatapatha--pxdatapath"></a><a name="px_datapath"></a>PX_DataPath  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のデータ パスのプロパティを初期化または逆シリアル化するメンバー関数を[関数](../../mfc/reference/cdatapathproperty-class.md)します。  
  
```  
 
BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    LPCTSTR 
pszPropName,  
    CDataPathProperty& dataPathProperty);

BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    CDataPathProperty& dataPathProperty);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `dataPathProperty`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 データ パスのプロパティは、非同期のコントロールのプロパティを実装します。 プロパティの値は読み取りやで参照される変数に書き込まれる`dataPathProperty` をクリックします。  
  
##  <a name="a-namepxdoublea--pxdouble"></a><a name="px_double"></a>PX_Double  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を**二重**します。  
  
```  
 
BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& doubleValue);

BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& 
doubleValue  ,  
    double doubleDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `doubleValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `doubleDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる`doubleValue` をクリックします。 場合`doubleDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxfonta--pxfont"></a><a name="px_font"></a>PX_Font  
 コントロールの中でこの関数を呼び出す`DoPropExchange`をシリアル化、または種類のフォントのプロパティを初期化します。  
  
```  
 
BOOL  
PX_Font(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CFontHolder& 
font  ,  
    const 
FONTDESC  
FAR* 
pFontDesc  
= 
NULL,  
    LPFONTDISP 
pFontDispAmbient  
= NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `font`  
 参照、`CFontHolder`フォント プロパティを含むオブジェクト。  
  
 `pFontDesc`  
 ポインター、 **FONTDESC**の場合は、フォントのプロパティの既定の状態の初期化中に使用する値を含む構造体、`pFontDispAmbient`は**NULL**します。  
  
 `pFontDispAmbient`  
 ポインター、**この**font プロパティの既定の状態の初期化中に使用するフォントのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値がから読み取り/書き込み`font`、`CFontHolder`適切な場合は、参照します。 場合`pFontDesc`と`pFontDispAmbient`が指定されているために必要なときに、このプロパティの既定値を初期化するためものです。 これらの値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。 通常は、渡す**NULL**の`pFontDesc`とアンビエントの値によって返される`COleControl::AmbientFont`の`pFontDispAmbient`です。 によって返されるフォント オブジェクト注`COleControl::AmbientFont`への呼び出しによって解放される必要があります、 **IFontDisp::Release**メンバー関数。  
  
##  <a name="a-namepxfloata--pxfloat"></a><a name="px_float"></a>PX_Float  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を**float**します。  
  
```  
 
BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& floatValue);

BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& 
floatValue  ,  
    float floatDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `floatValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `floatDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる`floatValue` をクリックします。 場合`floatDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxiunknowna--pxiunknown"></a><a name="px_iunknown"></a>PX_IUnknown  
 コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数を持つオブジェクトによって表されるプロパティを初期化または逆シリアル化、 **IUnknown**-派生インターフェイスです。  
  
```  
 
BOOL  
PX_IUnknown(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    LPUNKNOWN& 
pUnk  ,  
    REFIID 
iid  ,  
    LPUNKNOWN 
pUnkDefault  
= NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 *pUnk*  
 プロパティの値を表すオブジェクトのインターフェイスを含む変数への参照。  
  
 `iid`  
 プロパティ オブジェクトのインターフェイスがコントロールによって使用されることを示すインターフェイス ID です。  
  
 `pUnkDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる*pUnk* をクリックします。 場合`pUnkDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxlonga--pxlong"></a><a name="px_long"></a>PX_Long  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を**長い**します。  
  
```  
 
BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& lValue);

BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& 
lValue  ,  
    long lDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `lValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `lDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる`lValue` をクリックします。 場合`lDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxpicturea--pxpicture"></a><a name="px_picture"></a>PX_Picture  
 コントロールの中でこの関数を呼び出す`DoPropExchange`をシリアル化、またはコントロールの画像のプロパティを初期化します。  
  
```  
 
BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& pict);

BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& 
pict  ,  
    CPictureHolder& pictDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `pict`  
 参照、[使って](../../mfc/reference/cpictureholder-class.md)プロパティが格納されているオブジェクト (通常、クラスのメンバー変数)。  
  
 `pictDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる`pict` をクリックします。 場合`pictDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxshorta--pxshort"></a><a name="px_short"></a>PX_Short  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を**短い**します。  
  
```  
 
BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& sValue);

BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& 
sValue  ,  
    short sDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `sValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `sDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる`sValue` をクリックします。 場合`sDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxulonga--pxulong"></a><a name="px_ulong"></a>PX_ULong  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を**ULONG**します。  
  
```  
 
BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& ulValue);

BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& 
ulValue  ,  
    long ulDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前です。  
  
 `ulValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `ulDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる`ulValue` をクリックします。 場合`ulDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxushorta--pxushort"></a><a name="px_ushort"></a>PX_UShort  
 コントロールの中でこの関数を呼び出す`DoPropExchange`型のプロパティを初期化または逆シリアル化するメンバー関数を`unsigned`**短い**します。  
  
```  
 
BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& usValue);

BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& 
usValue  ,  
    USHORT usDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前です。  
  
 *usValue*  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 *usDefault*  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる*usValue* をクリックします。 場合*usDefault*を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxstringa--pxstring"></a><a name="px_string"></a>PXstring  
 コントロールの中でこの関数を呼び出す**DoPropExchange**をシリアル化、または文字の文字列プロパティを初期化します。  
  
```  
 
BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& strValue);

BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& 
strValue  ,  
    CString strDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `strValue`  
 プロパティが格納されている変数への参照 (通常、クラスのメンバー変数)。  
  
 `strDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値の読み取りまたはで参照される変数に書き込まれる`strValue` をクリックします。 場合`strDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="a-namepxvbxfontconverta--pxvbxfontconvert"></a><a name="px_vbxfontconvert"></a>PX_VBXFontConvert  
 コントロールの中でこの関数を呼び出す`DoPropExchange`VBX コントロールのフォント関連プロパティを変換することでフォントのプロパティを初期化します。  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡された`DoPropExchange`)。  
  
 `font`  
 変換された VBX のフォント関連のプロパティを格納する OLE コントロールのフォント プロパティ。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、VBX コントロールの直接の置き換えとして設計されていますが、OLE コントロールでのみ使用する必要があります。 Visual Basic 開発環境では、対応する置換 OLE コントロールを使用する VBX コントロールを表示するフォームが変換されるときに、呼び出すことが、コントロールの**IDataObject::SetData** VBX コントロールのプロパティのデータを含むプロパティ セットを渡す関数です。 この操作により、コントロールの`DoPropExchange`呼び出す関数。 `DoPropExchange`呼び出すことができます`PX_VBXFontConvert`VBX コントロールのフォント関連プロパティに変換する (たとえば、"FontName、""FontSize は、"に) OLE コントロールのフォントのプロパティの対応するコンポーネントにします。  
  
 `PX_VBXFontConvert`コントロールが VBX フォーム アプリケーションから実際に変換されているときにのみ呼び出されます必要があります。 例:  
  
 [!code-cpp[NVC_MFCActiveXControl&#14;](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl&#15;](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

