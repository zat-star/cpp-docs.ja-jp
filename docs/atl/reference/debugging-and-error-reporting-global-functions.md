---
title: "デバッグおよびエラー レポート関数をグローバル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4a412910d13d10606080c14412d33d2b614fdcec
ms.lasthandoff: 02/24/2017

---
# <a name="debugging-and-error-reporting-global-functions"></a>デバッグとエラー報告に関するグローバル関数
これらの関数は、デバッグとトレースに役立つ機能を提供します。  
  
|||  
|-|-|  
|[AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66)|返します。、`GetLastError`を HRESULT の形式でエラー コード。|  
|[AtlHresultFromWin32](http://msdn.microsoft.com/library/63add2dd-274c-4e72-a98c-040b93413a2f)|Win32 エラー コードを HRESULT に変換します。|  
|[AtlReportError](http://msdn.microsoft.com/library/86b046a5-ea18-4ecf-9aab-40fc1eab847c)|設定**IErrorInfo**クライアントにエラーの詳細を提供します。|  
|[ため](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)|`CAtlException` をスローします。|  
|[AtlThrowLastWin32](http://msdn.microsoft.com/library/8bce8e56-c7cd-4ebb-8c62-80ebc63a3d07)|Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。|  
  
##  <a name="a-nameatlhresultfromlasterrora--atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>AtlHresultFromLastError  
 呼び出し側スレッドの直前のエラー コード値を HRESULT の形式で返します。  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>コメント  
 `AtlHresultFromLastError`呼び出し`GetLastError`を最後のエラーを取得しを使用して、HRESULT に変換した後、エラーが返されます、 **HRESULT_FROM_WIN32**マクロです。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  

##  <a name="a-nameatlhresultfromwin32a--atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>AtlHresultFromWin32  
 Win32 エラー コードを HRESULT に変換します。  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>パラメーター  
 *エラー*  
 変換するエラー値。  
  
### <a name="remarks"></a>コメント  
 Win32 エラー コードをマクロを使用して、HRESULT に変換**HRESULT_FROM_WIN32**します。  
  
> [!NOTE]
>  使用せずに**HRESULT_FROM_WIN32(GetLastError())**、関数を使用して[AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66)します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  

##  <a name="a-nameatlreporterrora--atlreporterror"></a><a name="atlreporterror"></a>AtlReportError  
 設定、`IErrorInfo`オブジェクトのクライアントにエラー情報を提供するインターフェイスです。  
  
```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [in]エラーを報告して、オブジェクトの CLSID。  
  
 `lpszDesc`  
 [in]エラーを説明する文字列。 Unicode バージョンを指定する`lpszDesc`型**LPCOLESTR**; ANSI バージョンの種類を指定する`LPCSTR`です。  
  
 `iid`  
 [in]エラーを定義するインターフェイスの IID または`GUID_NULL`場合は、エラーは、オペレーティング システムによって定義されます。  
  
 `hRes`  
 [in]`HRESULT`する呼び出し元に返されます。  
  
 `nID`  
 [in]エラーの説明文字列が格納されているリソースの識別子です。 この値が範囲の 0x0200 から 0 xffff の間にする必要があります。 デバッグ ビルドでは、 **ASSERT**になります`nID`有効な文字列のインデックスは作成されません。 リリース ビルドでエラーを説明する文字列を「不明なエラー」に設定されます。  
  
 `dwHelpID`  
 [in]エラーのヘルプ コンテキスト id。  
  
 `lpszHelpFile`  
 [in]パスと、エラーを説明するヘルプ ファイルの名前。  
  
 `hInst`  
 [in]リソースへのハンドル。 このパラメーターは、既定では、 **__AtlBaseModuleModule::GetResourceInstance**ここで、 **__AtlBaseModuleModule**のグローバル インスタンスは、 [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md)またはその派生クラスです。  
  
### <a name="return-value"></a>戻り値  
 場合、`hRes`パラメーターが&0; 以外の場合の値を返します`hRes`します。 場合`hRes`が&0; の場合、最初の&4; つのバージョンの`AtlReportError`返す`DISP_E_EXCEPTION`します。 最後の 2 つのバージョンは、マクロの結果を返す**MAKE_HRESULT (1, FACILITY_ITF、** `nID` **)**します。  
  
### <a name="remarks"></a>コメント  
 文字列*lpszDesc*がエラーのテキストの説明として使用します。 クライアントが受信すると、`hRes`から制御が戻る`AtlReportError`、クライアントがアクセスできる、 **IErrorInfo**エラーの詳細の構造です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#52;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  使用しないで`AtlReportError`C++ では、ハンドラーをキャッチします。 これらの関数の一部のオーバーライドを使用して ATL 文字列変換マクロを内部的に使用される、`_alloca`関数を内部的にします。 使用して`AtlReportError`C++ catch ハンドラーの C++ の catch ハンドラーで例外が発生します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
    
##  <a name="a-nameatlthrowa--atlthrow"></a><a name="atlthrow"></a>ため  
 `HRESULT` ステータス コードに基づいてエラーを通知します。  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>パラメーター  
 `hr`  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 この関数は、エラー状態が発生した場合の ATL および MFC コードによって使用されます。 独自のコードから呼び出すこともできます。 この関数の既定の実装は、シンボルの定義によって異なります**シンボル**および MFC または atl プロジェクトの種類。  
  
 すべてのケースでは、この関数は、デバッガーに HRESULT をトレースします。  
  
 Visual Studio 2015 の Update 3 以降では、この関数は属性付き __declspec(noreturn) SAL 警告を回避するには。  
  
 場合**シンボル**が定義されていない MFC プロジェクトで、この関数がスローされます、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)HRESULT の値に基づいています。  
  
 場合**シンボル**関数のスロー、ATL プロジェクトで定義されていない、 [CAtlException](../../atl/reference/catlexception-class.md)します。  
  
 場合**シンボル**は例外をスローする代わりに、アサーション エラーが発生関数の定義します。  
  
 ATL プロジェクトの ATL によって、障害発生時に使用するには、この関数の実装を提供することができます。 これを行うには、定義と同じシグネチャを持つ関数`AtlThrow`と #define`AtlThrow`関数の名前になります。 これは、atlexcept.h (つまり atlbase.h に atlexcept.h が含まれているため、ATL ヘッダーを含める前に行う必要があります) を含める前に行う必要があります。 関数の属性`__declspec(noreturn)`SAL 警告を回避します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&95;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldef.h  

##  <a name="a-nameatlthrowlastwin32a--atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>AtlThrowLastWin32  
 Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>コメント  
 この関数の結果をトレースする`GetLastError`デバッガーが起動します。  
  
 場合**シンボル**が定義されていない MFC プロジェクトで、この関数がスローされます、[関数](../../mfc/reference/cmemoryexception-class.md)または[関数](../../mfc/reference/coleexception-class.md)によって返される値に基づいて`GetLastError`します。  
  
 場合**シンボル**関数のスロー、ATL プロジェクトで定義されていない、 [CAtlException](../../atl/reference/catlexception-class.md)します。  
  
 場合**シンボル**は例外をスローする代わりに、アサーション エラーが発生関数の定義します。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldef.h  
   
     
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)   
 [デバッグと、エラー報告のマクロ](../../atl/reference/debugging-and-error-reporting-macros.md)










