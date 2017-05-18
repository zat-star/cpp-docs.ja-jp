---
title: "オブジェクトのマップ マクロ |Microsoft ドキュメント"
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
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f03ca61c6ab3c550c316b380d34eb5fa4f3b61de
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="object-map-macros"></a>オブジェクト マップ マクロ
これらのマクロは、オブジェクトのマップとエントリを定義します。  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|オブジェクト マップに入力は、クラス オブジェクトのテキストの説明を指定できます。|  
|[については](#object_entry_auto)|ATL オブジェクトをオブジェクトのマップに入力オブジェクトのインスタンスを作成し、レジストリを更新します。|  
|[役立つ](#object_entry_non_createable_ex_auto)|オブジェクトを登録して初期化するように指定する一方で、`CoCreateInstance` を使用してオブジェクトを外部で作成できないように指定できます。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION  
 クラス オブジェクトのテキスト説明を指定できます。  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]クラス オブジェクトの説明です。  
  
### <a name="remarks"></a>コメント  
 ATL はを通じてオブジェクト マップにこの説明を入力、 [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd)マクロです。  
  
 `DECLARE_OBJECT_DESCRIPTION`実装して、`GetObjectDescription`関数をオーバーライドして使用できる、 [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription)メソッドです。  

  
 `GetObjectDescription`関数**IComponentRegistrar::GetComponents**します。 **IComponentRegistrar**オートメーション インターフェイスを登録し、DLL 内の個々 のコンポーネントの登録を解除することができます。 ATL プロジェクト ウィザードを使用してコンポーネントの登録オブジェクトを作成するときに、ウィザードは自動的に実装、 **IComponentRegistrar**インターフェイスです。 **IComponentRegistrar**通常は Microsoft Transaction Server で使用します。  
  
 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing&#123;](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>については  
 ATL オブジェクトをオブジェクトのマップに入力オブジェクトのインスタンスを作成し、レジストリを更新します。  
  
```
OBJECT_ENTRY_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [入力] `class` という名前の C++ クラスで実装されている COM クラスの CLSID。  
  
 `class`  
 [入力] `clsid` で表される COM クラスを実装する C++ クラスの名前。  
  
### <a name="remarks"></a>コメント  
 オブジェクトのエントリ マクロは、クラスの登録、初期化、および作成をサポートするためにプロジェクトのグローバル スコープに配置されます。  
  
 `OBJECT_ENTRY_AUTO`クリエーター クラスとクラス ファクトリ クリエーター クラスの関数ポインターを入力した`CreateInstance`ATL オブジェクトの自動生成されたマップには、このオブジェクトに対して機能します。 [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)が呼び出されると、オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。  

  
 次の表では、このマクロを&2; 番目のパラメーターとして指定したクラスからのオブジェクト マップに追加される情報の取得方法について説明します。  
  
|情報|取得しました。|  
|---------------------|-------------------|  
|COM 登録|[レジストリ マクロ](../../atl/reference/registry-macros.md)|  
|クラス ファクトリの作成|[クラス ファクトリ マクロ](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|インスタンスの作成|[集約マクロ](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|コンポーネントのカテゴリの登録|[カテゴリ マクロ](../../atl/reference/category-macros.md)|  
|クラス レベルの初期化とクリーンアップ|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

  
##  <a name="object_entry_non_createable_ex_auto"></a>役立つ  
 オブジェクトを登録して初期化するように指定する一方で、`CoCreateInstance` を使用してオブジェクトを外部で作成できないように指定できます。  
  
```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [入力] `class` という名前の C++ クラスで実装されている COM クラスの CLSID。  
  
 `class`  
 [入力] `clsid` で表される COM クラスを実装する C++ クラスの名前。  
  
### <a name="remarks"></a>コメント  
 オブジェクトのエントリ マクロは、クラスの登録、初期化、および作成をサポートするためにプロジェクトのグローバル スコープに配置されます。  
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`オブジェクトを登録して初期化することを指定することができます (を参照してください[は](#object_entry_auto)の詳細) ではありませんが、`CoCreateInstance`です。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

