---
title: "レジストリ マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
caps.latest.revision: 16
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3a3abf5ad29b50c7f6708f02fd7c5aa193b3591c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="registry-macros"></a>レジストリ マクロ
これらのマクロは、便利な型のライブラリとレジストリの機能を定義します。  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL. への依存関係を避けるために、オブジェクト内にあるオブジェクトの登録コードをすることを示しますDLL です。|  
|[DECLARE_LIBID](#declare_libid)|ATL を取得するための手段を提供、 *libid*のタイプ ライブラリ。|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|既定の ATL 登録を回避できます。|  
|[DECLARE_REGISTRY](#declare_registry)|入力したか、システム レジストリの主要なオブジェクトのエントリを削除します。|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|自動的に登録するために必要な情報を示す、 *appid*します。|  
|[に](#declare_registry_resource)|名前付きリソースを検索して、レジストリ スクリプトを実行します。|  
|[代入](#declare_registry_resourceid)|ID 番号によって識別されるリソースを検索して、レジストリ スクリプトを実行します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
    
##  <a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY  
 ATL. への依存関係を避けるために、オブジェクト内にあるオブジェクトの登録コードをするかを示すシンボルDLL です。  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>コメント  
 定義する際に**ATL_STATIC_REGISTRY**、次のコードを使用する必要があります。  
  
 [!code-cpp[NVC_ATL_EventHandlingSample&#5;](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="declare_libid"></a>DECLARE_LIBID  
 ATL を取得するための手段を提供、 *libid*のタイプ ライブラリ。  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>パラメーター  
 *libid*  
 タイプ ライブラリの GUID です。  
  
### <a name="remarks"></a>コメント  
 使用`DECLARE_LIBID`で、 `CAtlModuleT`-クラスを派生します。  
  
### <a name="example"></a>例  
 ATL ウィザードで生成されたプロジェクトの属性なしこのマクロを使用するサンプルが含まれます。  
  
##  <a name="declare_no_registry"></a>DECLARE_NO_REGISTRY  
 使用`DECLARE_NO_REGISTRY`をこのマクロが表示されるクラスの既定の ATL 登録を避けたい場合。  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="declare_registry"></a>DECLARE_REGISTRY  
 システム レジストリに標準的なクラスの登録を入力またはシステム レジストリから削除されます。  
  
```
DECLARE_REGISTRY(
    class, 
    pid, 
    vpid, 
    nid, 
    flags )
```  
  
### <a name="parameters"></a>パラメーター  
 `class`  
 [in]旧バージョンと互換性のために含まれています。  
  
 `pid`  
 [in]`LPCTSTR`はバージョン固有のプログラムの識別子。  
  
 *vpid*  
 [in]`LPCTSTR`はバージョンに依存しないプログラムの識別子。  
  
 *nid*  
 [in]A **UINT**つまりプログラムの説明として使用するレジストリ内のリソース文字列のインデックス。  
  
 `flags`  
 [in]A`DWORD`プログラムを含むのスレッド、レジストリ内のモデルです。 次の値のいずれかを指定する必要があります: **THREADFLAGS_APARTMENT**、 **THREADFLAGS_BOTH**、または**AUTPRXFLAG**します。  
  
### <a name="remarks"></a>コメント  
 標準の登録は、CLSID、プログラム ID、バージョンに依存しないプログラム ID、説明の文字列、およびスレッド モデルで構成されます。  
  
 ウィザードが自動的にレジストリのスクリプト ベースのサポートを実装して、追加オブジェクトを作成またはクラスの追加ウィザードを使用して制御するときに、[代入](#declare_registry_resourceid)ファイルにマクロです。 レジストリのスクリプトを使用したサポートしたくない場合は、使用してこのマクロを置き換える必要があります。`DECLARE_REGISTRY`します。 `DECLARE_REGISTRY`のみ、レジストリに上記で説明した&5; つの基本的なキーを挿入します。 その他のキーをレジストリに挿入するコードを手動で作成する必要があります。  
  
##  <a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID  
 自動的に登録するために必要な情報を示す、 *appid*します。  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>パラメーター  
 *resid*  
 に関する情報を含む .rgs ファイルのリソース id、 *appid*します。  
  
 *アプリケーション id*  
 GUID。  
  
### <a name="remarks"></a>コメント  
 使用`DECLARE_REGISTRY_APPID_RESOURCEID`で、 `CAtlModuleT`-クラスを派生します。  
  
### <a name="example"></a>例  
 クラスの追加コード ウィザードを使用して ATL プロジェクトに追加されたクラスをこのマクロを使用するサンプルが含まれます。  
  
##  <a name="declare_registry_resource"></a>に  
 レジストリ ファイルを含む名前付きリソースを取得し、システム レジストリにオブジェクトを入力するか、システム レジストリから削除するスクリプトを実行します。  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]文字列リソースの識別子。  
  
### <a name="remarks"></a>コメント  
 ウィザードにより自動的にレジストリのスクリプト ベースのサポートを実装され追加オブジェクトを作成または ATL プロジェクト ウィザードを使用して制御するときに、[代入](#declare_registry_resourceid)に似ているマクロ`DECLARE_REGISTRY_RESOURCE`ファイルにします。  
  
 最適化されたレジストリへのアクセスの ATL レジストリ コンポーネント (レジストラー) で静的にリンクすることができます。 レジストラー コードに静的にリンクするには、stdafx.h ファイルに次の行を追加します。  
  
 [!code-cpp[NVC_ATL_COM&#56;](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 実行時に置換値を置換する ATL をする場合は指定しないで、`DECLARE_REGISTRY_RESOURCE`または`DECLARE_REGISTRY_RESOURCEID`マクロです。 配列を作成する代わりに、**結果**実行時に、プレース ホルダーを置換対象の値と共に、構造、各エントリに変数のプレース ホルダーが含まれています。 まず[として](catlmodule-class.md#updateregistryfromresourced)または[方法については](catlmodule-class.md#updateregistryfromresources)配列を渡します。 これは、すべての置換値の追加、**結果**レジストラーの置換のマップの構造体。  

  
 置き換え可能パラメーターとスクリプトの詳細については、記事を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。  
  
##  <a name="declare_registry_resourceid"></a>代入  
 同じ[に](#declare_registry_resource)ウィザードで生成されたを使用する点を除いて**UINT**文字列名ではなく、リソースを識別するためにします。  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]リソースのウィザードで生成された識別子です。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを作成または ATL プロジェクト ウィザードを使用して制御するときにれ、ウィザードが自動的にレジストリのスクリプトを使用したサポートの実装を追加、`DECLARE_REGISTRY_RESOURCEID`ファイルにマクロです。  
  
 最適化されたレジストリへのアクセスの ATL レジストリ コンポーネント (レジストラー) で静的にリンクすることができます。 レジストラー コードに静的にリンクするには、stdafx.h ファイルに次の行を追加します。  
  
 [!code-cpp[NVC_ATL_COM&#56;](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 実行時に置換値を置換する ATL をする場合は指定しないで、`DECLARE_REGISTRY_RESOURCE`または`DECLARE_REGISTRY_RESOURCEID`マクロです。 配列を作成する代わりに、**結果**実行時に、プレース ホルダーを置換対象の値と共に、構造、各エントリに変数のプレース ホルダーが含まれています。 まず[として](catlmodule-class.md#updateregistryfromresourced)または[方法については](catlmodule-class.md#updateregistryfromresources)配列を渡します。 これは、すべての置換値の追加、**結果**レジストラーの置換のマップの構造体。  

  
 置き換え可能パラメーターとスクリプトの詳細については、記事を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

