---
title: "lock::operator!= | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "lock.operator!="
  - "msclr.lock.operator!="
  - "msclr::lock::operator!="
  - "lock::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock::operator!="
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
caps.latest.revision: 6
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock::operator!=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

等値演算子。  
  
## 構文  
  
```  
template<class T> bool operator!=(  
   T t  
);  
```  
  
#### パラメーター  
 `t`  
 非等値に比較するオブジェクト。  
  
## 戻り値  
 `t` がロック オブジェクトと異なる場合 `true`、別の方法で `false` を返します。  
  
## 使用例  
  
```  
// msl_lock_op_ineq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   Object^ o2 = gcnew Object;  
   lock l1(o1);  
   if (l1 != o2) {  
      Console::WriteLine("Inequal!");  
   }  
}  
```  
  
  **Inequal\!**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\lock.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [lock のメンバー](../dotnet/lock-members.md)   
 [lock::operator\=\=](../dotnet/lock-operator-equality.md)