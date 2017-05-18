---
title: "ATL Typedef |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 347e7bf7cd9173fb2815f44fc052ec23ab4055a6
ms.openlocfilehash: aa57212b602538e4e8d2854c6075562e72472796
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="atl-typedefs"></a>ATL の Typedef
Active Template Library には、次の typedef が含まれています。  
  
|||  
|-|-|  
|[_ATL_BASE_MODULE](#_atl_base_module)|基づく typedef と定義されている[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)します。|  
|[_ATL_COM_MODULE](#_atl_com_module)|基づく typedef と定義されている[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)します。|  
|[_ATL_MODULE](#_atl_module)|基づく typedef と定義されている[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)します。|  
|[_ATL_WIN_MODULE](#_atl_win_module)|基づく typedef と定義されている[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|  
|[ATL_URL_PORT](#atl_url_port)|使用される種類[CUrl](../../atl/reference/curl-class.md)ポート数を指定します。|  
|[CComDispatchDriver](#ccomdispatchdriver)|このクラスは、COM インターフェイス ポインターを管理します。|  
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|適切なスレッドに使用されるスレッド処理モデルに関係なく、モデルのメソッドを呼び出します。|  
|[CComObjectThreadModel](#ccomobjectthreadmodel)|適切なスレッドに使用されるスレッド処理モデルに関係なく、モデルのメソッドを呼び出します。|  
|[CContainedWindow](#ccontainedwindow)|このクラスは、特殊化した**CContainedWindowT します。**|  
|[CPath](#cpath)|特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CString`します。|  
|[CPathA](#cpatha)|特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CStringA`します。|  
|[CPathW](#cpathw)|特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CStringW`します。|  
|[CSimpleValArray](#csimplevalarray)|単純型を格納する配列を表します。|  
|[DefaultThreadTraits](#defaultthreadtraits)|既定のスレッドの特徴 (traits) クラス。|  
|[LPCURL](#lpcurl)|定数へのポインター [CUrl](../../atl/reference/curl-class.md)オブジェクトです。|  
|[LPURL](#lpurl)|ポインター、 [CUrl](../../atl/reference/curl-class.md)オブジェクトです。|  
  
##  <a name="_atl_base_module"></a>_ATL_BASE_MODULE  
 _ATL_BASE_MODULE70 に基づいて typedef と定義されます。  
  
```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```  
  
### <a name="remarks"></a>コメント  
 すべての ATL プロジェクトで使用されます。 基づく[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)します。  
  
 ATL 7.0 のモジュールのクラスの一部であるクラスは、_ATL_BASE_MODULE 構造体から派生します。  ATL モジュール クラスの詳細についてを参照してください[COM モジュール クラス](../../atl/com-modules-classes.md)します。  
  
##  <a name="_atl_com_module"></a>_ATL_COM_MODULE  
 _ATL_COM_MODULE70 に基づいて typedef と定義されます。  
  
```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```  
  
### <a name="remarks"></a>コメント  
 COM 機能を使用する ATL プロジェクトによって使用されます。 基づく[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)します。  
  
##  <a name="_atl_module"></a>_ATL_MODULE  
 _ATL_MODULE70 に基づいて typedef と定義されます。  
  
```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
  
### <a name="remarks"></a>コメント  
 基づく[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)します。  
  
##  <a name="_atl_win_module"></a>_ATL_WIN_MODULE  
 _ATL_WIN_MODULE70 に基づいて typedef と定義されます。  
  
```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
 
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウの機能を使用するすべての ATL プロジェクトによって使用されます。 基づく[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)します。  
  
##  <a name="atl_url_port"></a>ATL_URL_PORT 
  使用される種類[CUrl](curl-class.md)ポート数を指定します。
```  
typedef WORD ATL_URL_PORT;
```  

##  <a name="ccomdispatchdriver"></a>CComDispatchDriver  
 このクラスは、COM インターフェイス ポインターを管理します。  
  
```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
  
##  <a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel  
 適切なスレッドに使用されるスレッド処理モデルに関係なく、モデルのメソッドを呼び出します。  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションで使用するスレッド モデルに応じて、`typedef`名`CComGlobalsThreadModel`いずれかを参照して[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)します。 これらのクラスを追加提供`typedef`クリティカル セクション クラスを参照する名前。  
  
> [!NOTE]
> `CComGlobalsThreadModel`クラスを参照しない[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)します。  
  
 使用して`CComGlobalsThreadModel`特定のスレッド処理モデル クラスを指定することから解放します。 使用されているスレッド処理モデルに関係なく、適切なメソッドが呼び出されます。  
  
 他に、 `CComGlobalsThreadModel`、ATL には、`typedef`名[CComObjectThreadModel](#ccomobjectthreadmodel)します。 各によって参照されるクラス`typedef`次の表に示すように使用すると、スレッド処理モデルによって異なります。  
  
|typedef|シングル スレッド|アパートメント スレッド|フリー スレッド|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`;M =`CComMultiThreadModel`  
  
 使用`CComObjectThreadModel`1 つのオブジェクト クラス内で。 使用する`CComGlobalsThreadModel`オブジェクトまたは複数のスレッドでモジュールのリソースを保護する場合、プログラムにグローバルに使用可能にします。  
  
##  <a name="ccomobjectthreadmodel"></a>CComObjectThreadModel  
 適切なスレッドに使用されるスレッド処理モデルに関係なく、モデルのメソッドを呼び出します。  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComObjectThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションで使用するスレッド モデルに応じて、`typedef`名`CComObjectThreadModel`いずれかを参照して[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)します。 これらのクラスを追加提供`typedef`クリティカル セクション クラスを参照する名前。  
  
> [!NOTE]
> `CComObjectThreadModel`クラスを参照しない[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)します。  
  
 使用して`CComObjectThreadModel`特定のスレッド処理モデル クラスを指定することから解放します。 使用されているスレッド処理モデルに関係なく、適切なメソッドが呼び出されます。  
  
 他に、 `CComObjectThreadModel`、ATL には、`typedef`名[CComGlobalsThreadModel](#ccomglobalsthreadmodel)します。 各によって参照されるクラス`typedef`次の表に示すように使用すると、スレッド処理モデルによって異なります。  
  
|typedef|シングル スレッド|アパートメント スレッド|フリー スレッド|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`;M =`CComMultiThreadModel`  
  
 使用`CComObjectThreadModel`1 つのオブジェクト クラス内で。 使用`CComGlobalsThreadModel`いずれかであるオブジェクトに複数のスレッドでモジュールのリソースを保護する場合や、プログラムにグローバルに使用可能です。  
  
##  <a name="ccontainedwindow"></a>CContainedWindow  
 このクラスは、特殊化した**CContainedWindowT します。**  
  
```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  
  
### <a name="remarks"></a>コメント  
 `CContainedWindow`特殊化[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)します。 基本クラスまたは特徴 (traits) を変更する場合を使用して`CContainedWindowT`直接します。  
  
##  <a name="cpath"></a>CPath  
 特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CString`します。  
  
```   
typedef CPathT<CString> CPath;   
```  
  
##  <a name="cpatha"></a>CPathA  
 特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CStringA`します。  
  
```   
typedef CPathT<CStringA> CPathA;   
```  
  
##  <a name="cpathw"></a>CPathW  
 特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CStringW`します。  
  
```   
typedef ATL::CPathT<CStringW> CPathW;   
```  
  
##  <a name="csimplevalarray"></a>CSimpleValArray  
 単純型を格納する配列を表します。  
  
```   
#define CSimpleValArray CSimpleArray   
```  
  
### <a name="remarks"></a>コメント  
 `CSimpleValArray`作成および単純なデータ型を含む配列を管理するために提供されます。 単純な #include の define [CSimpleArray](../../atl/reference/csimplearray-class.md)します。  
  
##  <a name="lpcurl"></a>LPCURL  
 定数へのポインター [CUrl](../../atl/reference/curl-class.md)オブジェクトです。  
  
```   
typedef const CUrl* LPCURL;   
```  

##  <a name="defaultthreadtraits"></a>DefaultThreadTraits
既定のスレッドの特徴 (traits) クラス。

### <a name="syntax"></a>構文
```  
      #if defined(_MT)  
   typedef CRTThreadTraits DefaultThreadTraits;  
#else  
   typedef Win32ThreadTraits DefaultThreadTraits;  
#endif  
```

## <a name="remarks"></a>コメント
現在のプロジェクトでは、マルチ スレッド CRT を使用する場合は、DefaultThreadTraits が CRTThreadTraits として定義されます。 それ以外の場合、Win32ThreadTraits が使用されます。
  
##  <a name="lpurl"></a>LPURL  
 ポインター、 [CUrl](../../atl/reference/curl-class.md)オブジェクトです。  
  
```   
typedef CUrl* LPURL;   
```  
  
## <a name="see-also"></a>関連項目  
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   
 [関数](../../atl/reference/atl-functions.md)   
 [グローバル変数](../../atl/reference/atl-global-variables.md)   
 [構造体](../../atl/reference/atl-structures.md)   
 [マクロ](../../atl/reference/atl-macros.md)   
 [クラス](../../atl/reference/atl-classes.md)
