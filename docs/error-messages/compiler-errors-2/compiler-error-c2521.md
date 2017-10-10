---
title: "コンパイラ エラー C2521 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2521
dev_langs:
- C++
helpviewer_keywords:
- C2521
ms.assetid: 6042821b-e345-4a54-a7e9-a2c9019ea016
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: debe1e52637ea705996d2f787792b3691de34e23
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2521"></a>コンパイラ エラー C2521
'関数' は引数を受け取りません。  
  
 デストラクターまたはファイナライザーを引数付きで使っています。  
  
 詳細については、次を参照してください。[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)です。  
  
## <a name="example"></a>例  
 次の例では、C2521 を生成します。  
  
```  
// C2521.cpp  
// compile with: /clr  
ref class R {  
protected:  
   !R() {}  
  
public:  
   void CleanUp() {  
      this->!R(4);   // C2521  
      this->!R();   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R();  
   r->CleanUp();  
}  
```
