---
title: "プロジェクト (ATL) のスレッド処理モデルの指定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4c115b326d2cdfe82a0466461bd378fd1b4be80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>プロジェクトのスレッド モデルの指定 (ATL)
次のマクロは ATL プロジェクトのスレッド モデルを指定可能です。  
  
|マクロ|使用に関するガイドライン|  
|-----------|--------------------------|  
|_ATL_SINGLE_THREADED|場合は 1 つのスレッド モデルを使用してすべてのオブジェクトを定義します。|  
|_ATL_APARTMENT_THREADED|アパートメント スレッドを使用して 1 つまたは複数のオブジェクトの場合を定義します。|  
|_ATL_FREE_THREADED|1 つまたは複数のオブジェクトの free またはニュートラル スレッドを使用する場合を定義します。 既存のコードが同等のマクロの参照を含めることがあります[_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded)です。|  
  
 プロジェクトのこれらのマクロのいずれかを定義しない場合は、_ATL_FREE_THREADED が有効になります。  
  
 マクロは、実行時のパフォーマンスを次のように影響します。  
  
-   プロジェクト内のオブジェクトに対応するマクロを指定すると、実行時のパフォーマンスを向上させることができます。  
  
-   上位のレベルのスレッドで、すべてのオブジェクトが 1 つ _ATL_APARTMENT_THREADED を指定する場合の例については、マクロを指定すると、実行時のパフォーマンスが若干低下します。  
  
-   _ATL_SINGLE_THREADED いずれかを指定することもとフリー スレッドのアパートメント スレッドを使用して、オブジェクトの場合は、マクロなどの下位レベルを指定すると、アプリ実行時に失敗する可能性があります。  
  
 参照してください[オプション、ATL シンプル オブジェクト ウィザード](../atl/reference/options-atl-simple-object-wizard.md)ATL オブジェクトをモデル化、スレッド処理の詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [概念](../atl/active-template-library-atl-concepts.md)

