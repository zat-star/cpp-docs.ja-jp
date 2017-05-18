---
title: "カテゴリ マクロ |Microsoft ドキュメント"
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
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 26eea5cc8ce8e18af84a9ca89e5ddc94272be44c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="category-macros"></a>カテゴリ マクロ
これらのマクロは、カテゴリ マップを定義します。  
  
|||  
|-|-|  
|[BEGIN_CATEGORY_MAP](#begin_category_map)|カテゴリのマップの先頭をマークします。|  
|[END_CATEGORY_MAP](#end_category_map)|カテゴリ マップの最後をマークします。|  
|[IMPLEMENTED_CATEGORY](#implemented_category)|COM オブジェクトによって実装されるカテゴリを示します。|  
|[要求します。](#required_category)|COM オブジェクトによって、コンテナーの必要なカテゴリを示します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  

##  <a name="begin_category_map"></a>BEGIN_CATEGORY_MAP  
 カテゴリのマップの先頭をマークします。  
  
```
BEGIN_CATEGORY_MAP(theClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]カテゴリのマップを含むクラスの名前。  
  
### <a name="remarks"></a>コメント  
 カテゴリのマップを使用して、どのコンポーネントのカテゴリは、COM クラスを実装およびコンテナーに対して要求する対象のカテゴリを指定します。  
  
 追加、 [IMPLEMENTED_CATEGORY](#implemented_category) COM クラスで実装される各カテゴリ用にマップするエントリです。 追加、[要求する](#required_category)クラスを実装するには、そのクライアントに必要な各カテゴリ用にマップするエントリです。 使用して、地図の末尾を示す、 [END_CATEGORY_MAP](#end_category_map)マクロです。  
  
 クラスに関連付けられている場合、モジュールが登録されると、マップに表示されているコンポーネントのカテゴリを自動的に登録されます[は](../../atl/reference/object-map-macros.md#object_entry_auto)または[役立つ](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)します。  
  
> [!NOTE]
>  ATL では、標準的なコンポーネント カテゴリ マネージャーを使用して、コンポーネントのカテゴリを登録します。 モジュールが登録されているときに、マネージャーがシステムに存在しない場合は、登録は成功しますが、コンポーネントのカテゴリは、そのクラスは登録されません。  
  
 コンポーネントのカテゴリの詳細については、次を参照してください。[コンポーネントのカテゴリとは、その動作方法](http://msdn.microsoft.com/library/windows/desktop/ms694322)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing&#100;](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="end_category_map"></a>END_CATEGORY_MAP  
 カテゴリ マップの最後をマークします。  
  
```
END_CATEGORY_MAP()
```  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_CATEGORY_MAP](#begin_category_map)します。  
  
##  <a name="implemented_category"></a>IMPLEMENTED_CATEGORY  
 追加、`IMPLEMENTED_CATEGORY`マクロをコンポーネントの[カテゴリ マップ](#begin_category_map)で識別されるカテゴリを実装するとして登録する必要があるかを指定する、`catID`パラメーター。  
  
```
IMPLEMENTED_CATEGORY(catID)
```  
  
### <a name="parameters"></a>パラメーター  
 `catID`  
 [in]A **CATID**定数または実装済みのカテゴリのグローバル一意識別子 (GUID) を保持する変数。 アドレス`catID`が取得され、マップに追加します。 ストックのカテゴリの選択は、次の表を参照してください。  
  
### <a name="remarks"></a>コメント  
 クラスに関連付けられている場合、モジュールが登録されると、マップに表示されているコンポーネントのカテゴリを自動的に登録されます[は](../../atl/reference/object-map-macros.md#object_entry_auto)または[役立つ](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)マクロです。  
  
 クライアントは、インスタンスを作成するのにことがなく、機能と要件を確認するのにはクラスの登録されているカテゴリ情報を使用できます。  
  
 コンポーネントのカテゴリの詳細については、次を参照してください。[コンポーネントのカテゴリとは、その動作方法](http://msdn.microsoft.com/library/windows/desktop/ms694322)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="a-selection-of-stock-categories"></a>ストックのカテゴリの選択  
  
|説明|シンボル|レジストリの GUID|  
|-----------------|------------|-------------------|  
|安全なスクリプト|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|安全な初期化|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|単純なフレーム サイト コンテインメント|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|単純データ バインディング|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|高度なデータ バインディング|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|ウィンドウなしのコントロール|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|インターネット対応オブジェクト|参照してください[インターネット対応オブジェクト](http://msdn.microsoft.com/library/windows/desktop/ms690561)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]一覧については、サンプルです。||  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing&#100;](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="required_category"></a>要求します。  
 追加、`REQUIRED_CATEGORY`マクロをコンポーネントの[カテゴリ マップ](#begin_category_map)で識別されるカテゴリを必要とするとして登録する必要があるかを指定する、`catID`パラメーター。  
  
```
REQUIRED_CATEGORY( catID )
```  
  
### <a name="parameters"></a>パラメーター  
 `catID`  
 [in]A **CATID**定数または必要なカテゴリのグローバル一意識別子 (GUID) を保持する変数。 アドレス`catID`が取得され、マップに追加します。 ストックのカテゴリの選択は、次の表を参照してください。  
  
### <a name="remarks"></a>コメント  
 クラスに関連付けられている場合、モジュールが登録されると、マップに表示されているコンポーネントのカテゴリを自動的に登録されます[は](../../atl/reference/object-map-macros.md#object_entry_auto)または[役立つ](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)マクロです。  
  
 クライアントは、インスタンスを作成するのにことがなく、機能と要件を確認するのにはクラスの登録されているカテゴリ情報を使用できます。 たとえば、コントロールは、コンテナーがデータ バインディングをサポートする必要があります。 コンテナーは、そのコントロールに必要なカテゴリをカテゴリ マネージャーをクエリすることによって、コントロールをホストするために必要な機能があるかどうか確認できます。 コンテナーが必要な機能をサポートしていない場合は、COM オブジェクトのホストを拒否できます。  
  
 サンプルの一覧を含むコンポーネントのカテゴリの詳細については、次を参照してください。[コンポーネントのカテゴリとは、その動作方法](http://msdn.microsoft.com/library/windows/desktop/ms694322)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="a-selection-of-stock-categories"></a>ストックのカテゴリの選択  
  
|説明|シンボル|レジストリの GUID|  
|-----------------|------------|-------------------|  
|安全なスクリプト|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|安全な初期化|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|単純なフレーム サイト コンテインメント|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|単純データ バインディング|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|高度なデータ バインディング|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|ウィンドウなしのコントロール|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|インターネット対応オブジェクト|参照してください[インターネット対応オブジェクト](http://msdn.microsoft.com/library/windows/desktop/ms690561)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]一覧については、サンプルです。||  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&135;](../../atl/codesnippet/cpp/category-macros_2.h)]  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

