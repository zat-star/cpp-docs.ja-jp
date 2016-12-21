---
title: "コンパイラ エラー C3451 | Microsoft Docs"
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
  - "C3451"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3451"
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3451
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'属性': アンマネージ属性を '型' に適用できません  
  
 C\+\+ 属性を CLR 型に適用することはできません。  詳細については、「[C\+\+ Attributes Reference](../../windows/cpp-attributes-reference.md)」を参照してください。  
  
 詳細については、「[User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。  
  
 このエラーは、Visual C\+\+ 2005 で行ったコンパイラ準拠作業の結果として生成されることがあります。[uuid](../../windows/uuid-cpp-attributes.md) 属性は、CLR プログラミングを使用するユーザー定義の属性で使用できなくなりました。  代わりに、<xref:System.Runtime.InteropServices.GuidAttribute> を使用してください。  
  
## 使用例  
 次の例では C3451 エラーが生成されます。  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```