---
title: "置き換え可能パラメーター (ATL レジストラー) を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AddReplacement
- ClearReplacements
dev_langs:
- C++
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b06333ba51b74501f3b7cd68248e5fb7e51ca94f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>置き換え可能パラメーター (レジストラー &#39; s プリプロセッサ) を使用します。
置き換え可能パラメーターを使用すると、レジストラーのクライアントを実行時のデータを指定します。 これを行うには、レジストラーが先は、スクリプトで置き換え可能パラメーターに関連付けられている値が入った置換マップを保持します。 レジストラーでは、実行時にこれらのエントリを作成します。  
  
##  <a name="_atl_using_.25.module.25"></a>% モジュールを使用します。  
 [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)を使用するスクリプトを自動的に生成`%MODULE%`です。 ATL は、サーバーの DLL または EXE の実際の場所をこの置き換え可能パラメーターを使用します。  
  
## <a name="concatenating-run-time-data-with-script-data"></a>実行時のデータとスクリプトのデータを連結します。  
 プリプロセッサの別の使用は、実行時のデータとスクリプトのデータを連結します。 たとえば、文字列を持つモジュールへの完全パスを含むエントリが必要な"`, 1`"最後に追加します。 最初に、次の展開を定義します。  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 次を呼び出す前にスクリプトの処理で表示されているメソッドのいずれかの[スクリプトの呼び出し](../atl/invoking-scripts.md)代わりにマップを追加。  
  
 [!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]  
  
 スクリプトの解析中に、レジストラーが展開され`'%MODULE%, 1'`に`c:\mycode\mydll.dll, 1`です。  
  
> [!NOTE]
>  レジストラー スクリプトでは、トークンの最大サイズは 4 K です。 (トークンは、構文内の認識可能な要素です)。これには、作成またはプリプロセッサによって展開されたトークンが含まれます。  
  
> [!NOTE]
>  実行時に置換値を置換するために、スクリプト内の呼び出しを削除、[に](../atl/reference/registry-macros.md#declare_registry_resource)または[代入](../atl/reference/registry-macros.md#declare_registry_resourceid)マクロです。 代わりに、独自に置き換える`UpdateRegistry`メソッドを呼び出す[として](../atl/reference/catlmodule-class.md#updateregistryfromresourced)または[方法については](../atl/reference/catlmodule-class.md#updateregistryfromresources)の配列を渡すと**_ATL_REGMAP_ENTRY**構造体。 配列**_ATL_REGMAP_ENTRY**には、少なくとも 1 つのエントリに設定されている必要があります {**NULL**、**NULL**}、し、このエントリが最後のエントリには常にします。 それ以外の場合、アクセス違反エラーになるときに生成**UpdateRegistryFromResource**と呼びます。  
  
> [!NOTE]
>  ATL が自動的に実行時に作成されるパス名を囲む引用符を追加、実行可能ファイルを出力するプロジェクトをビルドする際、 **% モジュール**レジストラー スクリプトのパラメーターです。 パス名に引用符を含めるしたくない場合は、新しい使用**%module_raw**パラメーター代わりにします。  
>   
>  DLL を出力するプロジェクトを作成するときに ATL には追加されません引用符がある場合、パス名場合**% モジュール**または**%module_raw**を使用します。  
  
## <a name="see-also"></a>参照  
 [レジストラー スクリプトの作成](../atl/creating-registrar-scripts.md)

