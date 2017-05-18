---
title: "CPropExchange クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
dev_langs:
- C++
helpviewer_keywords:
- CPropExchange class
- OLE controls, persistence
- controls [MFC], OLE
ms.assetid: ed872180-e770-4942-892a-92139d501fab
caps.latest.revision: 22
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
ms.openlocfilehash: 655d8e2f074c3bd12b1b52ece74efb844c7a9904
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cpropexchange-class"></a>CPropExchange クラス
OLE コントロールの永続性の実装をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|バイナリ ラージ オブジェクト (BLOB) のプロパティを交換します。|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|フォントのプロパティを交換します。|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|コントロールとファイルのプロパティを交換します。|  
|[CPropExchange::ExchangeProp](#exchangeprop)|すべての組み込み型のプロパティを交換します。|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|OLE コントロールのバージョン番号を交換します。|  
|[CPropExchange::GetVersion](#getversion)|OLE コントロールのバージョン番号を取得します。|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|プロパティの交換が非同期的に実行を決定します。|  
|[CPropExchange::IsLoading](#isloading)|プロパティがされているかどうかを示す、コントロールに読み込まれるかから保存します。|  
  
## <a name="remarks"></a>コメント  
 `CPropExchange`基本クラスはありません。  
  
 コンテキストとプロパティの exchange の方向を確立します。  
  
 永続化には、通常、コントロール自体とは [中] の間でそのプロパティで表される、コントロールの状態情報の交換です。  
  
 派生したオブジェクトを構築するために、フレームワーク`CPropExchange`から読み込まれる OLE コントロールのプロパティができたことを通知には、またはストアドに永続的なストレージです。  
  
 フレームワークは、このポインターを渡します`CPropExchange`オブジェクトに、コントロールの`DoPropExchange`関数です。 目的のコントロールのコントロールのスターター ファイルを作成するウィザードを使用した場合`DoPropExchange`関数呼び出し`COleControl::DoPropExchange`します。 基底クラス版交換コントロールのストック プロパティです。コントロールに追加した exchange のプロパティに、派生クラスのバージョンを変更します。  
  
 `CPropExchange`コントロールのプロパティをシリアル化または負荷またはコントロールの作成時にコントロールのプロパティを初期化するために使用します。 `ExchangeProp`と`ExchangeFontProp`のメンバー関数`CPropExchange`にプロパティを格納し、それらを別のメディアから読み込むことができます。  
  
 使用する方法について`CPropExchange`、記事を参照して[MFC ActiveX コントロール: プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CPropExchange`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
##  <a name="exchangeblobprop"></a>CPropExchange::ExchangeBlobProp  
 バイナリ ラージ オブジェクト (BLOB) データを格納するプロパティをシリアル化します。  
  
```  
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,  
    HGLOBAL* phBlob,  
    HGLOBAL hBlobDefault = NULL) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `phBlob`  
 プロパティの格納場所を指す変数へのポインター (変数は、通常、クラスのメンバー)。  
  
 `hBlobDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値は、読み取り、書き込み先とで参照される変数の適切な`phBlob`です。 場合`hBlobDefault`を指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化が失敗したときに使用されます。  
  
 関数は、 **CArchivePropExchange::ExchangeBlobProp**、 **CResetPropExchange::ExchangeBlobProp**、および**CPropsetPropExchange::ExchangeBlobProp**純粋仮想関数をオーバーライドします。  
  
##  <a name="exchangefontprop"></a>CPropExchange::ExchangeFontProp  
 ストレージ メディアとコントロール間でのフォント プロパティを交換します。  
  
```  
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,  
    CFontHolder& font,  
    const FONTDESC* pFontDesc,  
    LPFONTDISP pFontDispAmbient) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `font`  
 参照、 [CFontHolder](../../mfc/reference/cfontholder-class.md)フォント プロパティを含むオブジェクト。  
  
 `pFontDesc`  
 ポインター、 [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) font プロパティの既定の状態を初期化するための値を含む構造体と`pFontDispAmbient`は**NULL**します。  
  
 `pFontDispAmbient`  
 ポインター、**この**font プロパティの既定の状態を初期化するために使用するフォントのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フォントのプロパティは、コントロールに、メディアから読み込まれて、フォントの特性は、メディアから取得されます、`CFontHolder`によって参照されるオブジェクト`font`で初期化されます。 Font プロパティが格納される場合は、font オブジェクトの特性がメディアに書き込まれます。  
  
 関数は、 **CArchivePropExchange::ExchangeFontProp**、 **CResetPropExchange::ExchangeFontProp**、および**CPropsetPropExchange::ExchangeFontProp**純粋仮想関数をオーバーライドします。  
  
##  <a name="exchangepersistentprop"></a>CPropExchange::ExchangePersistentProp  
 コントロールとファイルのプロパティを交換します。  
  
```  
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,  
    LPUNKNOWN* ppUnk,  
    REFIID iid,  
    LPUNKNOWN pUnkDefault) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `ppUnk`  
 プロパティへのポインターを含む変数へのポインター **IUnknown**インターフェイス (この変数は、通常、クラスのメンバー)。  
  
 `iid`  
 コントロールを使用するプロパティのインターフェイスのインターフェイス ID です。  
  
 `pUnkDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティは、コントロールに、ファイルから読み込まれるが場合、プロパティが作成され、ファイルを使用して初期化します。 プロパティが格納される場合、その値は、ファイルに書き込まれます。  
  
 関数は、 **CArchivePropExchange::ExchangePersistentProp**、 **CResetPropExchange::ExchangePersistentProp**、および**CPropsetPropExchange::ExchangePersistentProp**純粋仮想関数をオーバーライドします。  
  
##  <a name="exchangeprop"></a>CPropExchange::ExchangeProp  
 ストレージ メディアとコントロール間でのプロパティを交換します。  
  
```  
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,  
    VARTYPE vtProp,  
    void* pvProp,  
    const void* pvDefault = NULL) = 0 ;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `vtProp`  
 交換されるプロパティの型を指定する記号です。 指定できる値は次のとおりです。  
  
|シンボル|プロパティの型|  
|------------|-------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_BOOL`|**BOOL**|  
|`VT_BSTR`|`CString`|  
|`VT_CY`|**CY**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
  
 `pvProp`  
 プロパティの値へのポインター。  
  
 *pvDefault*  
 プロパティの既定値へのポインター。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値が、メディアから取得され、によって指されるオブジェクトに格納されている場合は、プロパティは、コントロールに、メディアから読み込まれて、`pvProp`です。 、、プロパティがメディアに格納される場合、オブジェクトの値が指す`pvProp`はメディアに書き込まれます。  
  
 関数は、 **CArchivePropExchange::ExchangeProp**、 **CResetPropExchange::ExchangeProp**、および**CPropsetPropExchange::ExchangeProp**純粋仮想関数をオーバーライドします。  
  
##  <a name="exchangeversion"></a>CPropExchange::ExchangeVersion  
 バージョン番号の永続化を処理するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwVersionLoaded*  
 読み込まれている永続的なデータのバージョン番号を格納する変数への参照。  
  
 `dwVersionDefault`  
 コントロールの現在のバージョン番号。  
  
 `bConvert`  
 現在のバージョンを永続的なデータを変換するか、既に読み込まれているバージョンが同じで保持するかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合は 0 です。  
  
##  <a name="getversion"></a>CPropExchange::GetVersion  
 コントロールのバージョン番号を取得するには、この関数を呼び出します。  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのバージョン番号。  
  
##  <a name="isasynchronous"></a>CPropExchange::IsAsynchronous  
 プロパティの交換が非同期的に実行を決定します。  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティは TRUE を返しますがそれ以外の場合の FALSE では非同期、交換されます。  
  
##  <a name="isloading"></a>CPropExchange::IsLoading  
 プロパティがされているかどうかを判断するには、この関数を呼び出して、コントロールに読み込みまたはそこから保存します。  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティが読み込まれる場合は 0 以外それ以外の場合 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [使って](../../mfc/reference/colecontrol-class.md#dopropexchange)




