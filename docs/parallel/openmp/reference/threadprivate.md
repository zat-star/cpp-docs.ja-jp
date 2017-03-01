---
title: "threadprivate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
caps.latest.revision: 11
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2f5d64c172cac629a80cdf4a1057afbbf9789f5f
ms.lasthandoff: 02/24/2017

---
# <a name="threadprivate"></a>threadprivate
変数は、スレッドに対してプライベートであることを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 スレッドにプライベートに変数のコンマ区切りの一覧です。 `var`グローバルまたは名前空間スコープの変数または静的ローカル変数のいずれかにする必要があります。  
  
## <a name="remarks"></a>コメント  
 `threadprivate`ディレクティブに OpenMP 句はサポートされていません。  
  
 詳細については、次を参照してください。 [2.7.1 threadprivate ディレクティブ](../../../parallel/openmp/2-7-1-threadprivate-directive.md)します。  
  
 `threadprivate`ディレクティブがに基づいて、[スレッド](../../../cpp/thread.md)`__declspec`属性; には制限**_declspec**に適用`threadprivate`します。  
  
 使用することはできません`threadprivate`を使用して読み込まれる DLL で[LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)します。  これで読み込まれる Dll に含まれます[/DELAYLOAD (遅延読み込みのインポート)](../../../build/reference/delayload-delay-load-import.md)を使用しても**LoadLibrary**します。  
  
 使用する`threadprivate`プロセスの起動時に静的に読み込まれる DLL にします。  
  
 `threadprivate`に基づく**_declspec**、`threadprivate`変数は、並列領域によって生成されるスレッド チームの一部であるスレッドだけでなく、プロセスで開始されたすべてのスレッド内に存在します。  これは、実装の細部なので、たとえばのコンス トラクターは、留意す、`threadprivate`予想以上にユーザー定義型が呼び出されます。  
  
 A`threadprivate`消滅可能型の変数と呼ばれる、デストラクターは保証されません。  例:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 ユーザーは、並列領域を構成するスレッドを終了すると、管理しているありません。  プロセスが終了すると、スレッドはプロセスの終了に関する通知されません、に対してデストラクターは呼び出されませんされ、それらのスレッドが存在しない場合`threaded_var`で終了する&1; つを除く任意のスレッドで (ここでは、プライマリ スレッド)。  コードの適切な破棄をカウントしませんように`threadprivate`変数です。  
  
## <a name="example"></a>例  
 使用するサンプルの`threadprivate`を参照してください[プライベート](../../../parallel/openmp/reference/private-openmp.md)します。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)
