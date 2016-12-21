---
title: "コンパイラの警告 (レベル 1) C4407 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4407"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4407"
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4407
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ポインターとメンバー間で異なる表示がキャストされました。コンパイラは正しくないコードを生成する可能性があります。  
  
 不正なキャストが見つかりました。  
  
 C4407 は、Visual C\+\+ 2005 で行ったコンパイラ準拠作業のために生成されることもあります。  メンバーへのポインターには、修飾名とアドレス演算子を必要と&しています。  
  
 C4407 は、多重継承のメンバーへのポインターから単一継承のメンバーへのポインターにキャストした場合に発生することがあります。  このようなキャストが正常に動作する場合もありますが、単一継承のメンバーへのポインター表現では十分な情報を保持できないためにエラーになることもあります。  **\/vmm** を指定してコンパイルすると解決されることがあります \(詳細については、「[\/vmm、\/vms、\/vmv \(通常の最適化\)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)」を参照してください\)。  基本クラスを再配置してみることもできます。基本クラスは派生クラスから非ゼロのオフセット位置に置かれるため、変換で失われた情報が検知されます。  
  
 次の例では警告 C4407 が生成されます。  
  
```  
// C4407.cpp  
// compile with: /W1 /c  
struct C1 {};  
struct C2 {};  
struct C3 : C1, C2 {};  
  
typedef void(C3::*PMF_C3)();  
typedef void(C2::*PMF_C2)();  
  
PMF_C2 f1(PMF_C3 pmf) {  
   return (PMF_C2)pmf;   // C4407, change type of cast,  
   // or reverse base class inheritance of C3 (i.e. : C2, C1)  
}  
```