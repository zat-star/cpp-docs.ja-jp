---
title: "コンパイラ エラー C3270 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3270"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3270"
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3270
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'field': FieldOffset 属性は、必要な場合は StructLayout\(Explicit\) のコンテキストでのみ使用できます  
  
 フィールドが [FieldOffset](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic) でマークされていますが、これは [StructLayout](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic) Explicit が有効になっている場合にのみ使用できます。  
  
 次の例では C3270 が生成されます。  
  
```  
// C3270_2.cpp // compile with: /clr /c using namespace System::Runtime::InteropServices; [ StructLayout(LayoutKind::Sequential) ] // try the following line instead // [ StructLayout(LayoutKind::Explicit) ] public value struct MYUNION { [FieldOffset(0)] int a;   // C3270 // ... };  
```  
  
 次の例では C3270 が生成されます。  
  
```  
// C3270.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> using namespace System::Runtime::InteropServices; [ StructLayout(LayoutKind::Sequential) ] // try the following line instead // [ StructLayout(LayoutKind::Explicit) ] public __value struct MYUNION { [FieldOffset(0)] int a;   // C3270 // ... };  
```