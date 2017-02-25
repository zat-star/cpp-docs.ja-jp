---
title: "コンパイラ エラー C2605 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2605"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2605"
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2605
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name': このメソッドは、マネージ クラスまたは WinRT クラスで予約されています  
  
 内部関数用に、いくつかの名前がコンパイラによって予約されています。  詳細については、「[デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。  
  
## 使用例  
 次の例では C2605 が生成されます。  
  
```  
// C2605.cpp  
// compile with: /clr /c  
ref class R {  
protected:  
   void Finalize() {}   // C2605  
};  
```