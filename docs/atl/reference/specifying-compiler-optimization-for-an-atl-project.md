---
title: "ATL プロジェクトのコンパイラの最適化を指定する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
dev_langs:
- C++
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
caps.latest.revision: 10
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: abdad4367e75c1971ba5d11af1a60992d1bb3dd4
ms.lasthandoff: 02/24/2017

---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL プロジェクトのコンパイラの最適化を指定します。
既定では、 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)ATL_NO_VTABLE マクロを使用した新しいクラスを次のように生成されます。  
  
```  
class ATL_NO_VTABLE CProjName  
{  
 ...  
};  
```  
  
 ATL し、_ATL_NO_VTABLE を次のように定義します。  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
 #define ATL_NO_VTABLE  
#else  
 #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 ATL_NO_VTABLE マクロが展開 _ATL_DISABLE_NO_VTABLE を定義していない場合`declspec(novtable)`します。 使用して`declspec(novtable)`クラスで宣言により、vtable ポインター クラスのコンス トラクターおよびデストラクター内で初期化されるからです。 プロジェクトをビルドするときに、リンカーは、vtable と vtable がポイントするすべての関数が解消されます。  
  
 ATL_NO_VTABLE を使用する必要があるあり、その結果`declspec(novtable)`、直接作成可能な型ではない基底クラスのみを持つ。 使用しないでください`declspec(novtable)`プロジェクトで、最派生クラスを使用して、このクラス (通常[と](../../atl/reference/ccomobject-class.md)、[すると](../../atl/reference/ccomaggobject-class.md)、または[CComPolyObject](../../atl/reference/ccompolyobject-class.md))、プロジェクトの vtable ポインターを初期化します。  
  
 使用する任意のオブジェクトのコンス トラクターから仮想関数を呼び出す必要がありますいない`declspec(novtable)`します。 これらの呼び出しを移動する必要があります、 [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)メソッドです。  

  
 いないことを確認する必要があるかどうかを使用している場合、`declspec(novtable)`修飾子は、任意のクラス定義から ATL_NO_VTABLE マクロを削除するかを指定してグローバルに無効ことができます  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 stdafx.h で他のすべての ATL の前にヘッダー ファイルが含まれます。  
  
## <a name="see-also"></a>関連項目  
 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
 [Visual C プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用して、デスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)


