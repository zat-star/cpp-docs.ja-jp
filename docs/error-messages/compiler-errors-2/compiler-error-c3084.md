---
title: "コンパイラ エラー C3084 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3084
dev_langs:
- C++
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 7fb05bf2ebf23446de0552fd06092cb75541d49e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3084"></a>コンパイラ エラー C3084
'function': ファイナライザーまたはデストラクターを 'keyword' にすることはできません。  
  
 ファイナライザーまたはデストラクターの宣言が正しくありません。  
  
 たとえば、デストラクターをシール済みとしてマークすることはできません。  デストラクターは派生型にアクセスできません。  詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)と[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C + +/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。  
  
## <a name="example"></a>例  
 次の例では C3084 が生成されます。  
  
```  
// C3084.cpp  
// compile with: /clr /c  
ref struct R {  
protected:  
   !R() sealed;   // C3084  
   !R() abstract;   // C3084  
   !R();  
};  
```
