---
title: "コンパイラ エラー C2261 | Microsoft Docs"
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
  - "C2261"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2261"
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2261
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'文字列' : アセンブリ参照は無効なため、解決できません。  
  
 値が無効です。  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> は、フレンド アセンブリを指定するために使用されます。  たとえば、a.dll で b.dll をフレンド アセンブリとして指定するには、a.dll で InternalsVisibleTo\("b"\) を指定します。  この結果ランタイムによって、b.dll は a.dll のすべての型 \(ただしプライベート型を除く\) にアクセスできるようになります。  
  
 フレンド アセンブリを指定する際の正しい構文の詳細については、「[フレンド アセンブリ \(C\+\+\)](../../dotnet/friend-assemblies-cpp.md)」を参照してください。  
  
## 使用例  
 次の例では C2261 エラーが生成されます。  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```