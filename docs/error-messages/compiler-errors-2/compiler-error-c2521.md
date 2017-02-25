---
title: "コンパイラ エラー C2521 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2521"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2521"
ms.assetid: 6042821b-e345-4a54-a7e9-a2c9019ea016
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2521
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' は引数を受け取りません。  
  
 デストラクターまたはファイナライザーを引数付きで使っています。  
  
 詳細については、「[デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。  
  
## 使用例  
 次の例では C2521 エラーが生成されます。  
  
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