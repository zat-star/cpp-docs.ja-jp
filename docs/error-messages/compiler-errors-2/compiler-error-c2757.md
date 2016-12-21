---
title: "コンパイラ エラー C2757 | Microsoft Docs"
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
  - "C2757"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2757"
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2757
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : この名前のシンボルは既に存在します。この名前を名前空間名として使用することはできません。  
  
 現在のコンパイルで名前空間の識別子として使用されているシンボルは、参照アセンブリで既に使用されています。  
  
 次の例では警告 C2757 が生成されます。  
  
```  
// C2757a.cpp  
// compile with: /clr /LD  
public ref class Nes {};  
```  
  
 次に、以下のコードを実行します。  
  
```  
// C2757b.cpp  
// compile with: /clr /c  
#using <C2757a.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public ref class X {};  
}  
```  
  
 次の例では警告 C2757 が生成されます。  
  
```  
// C2757c.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
public __gc class Nes {};  
```  
  
 次に、以下のコードを実行します。  
  
```  
// C2757d.cpp  
// compile with: /clr:oldSyntax /c  
#using <C2757c.dll>  
#using <mscorlib.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public __gc class X {};  
}  
```