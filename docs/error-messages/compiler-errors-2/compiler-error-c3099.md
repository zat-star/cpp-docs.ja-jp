---
title: "Compiler Error C3099 | Microsoft Docs"
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
  - "C3099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3099"
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword': マネージ属性には \[System::AttributeUsageAttribute\] を使用してください。WinRT 属性には \[Windows::Foundation::Metadata::AttributeUsageAttribute\] を使用してください。  
  
 <xref:System.AttributeUsageAttribute> を使用して、**\/clr** 属性を宣言します。  `Windows::Foundation::Metadata::AttributeUsageAttribute` を使用して、Windows ランタイム属性を宣言します。  
  
 \/CLR 属性の詳細については、「[User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。  Windows ランタイムでサポートされている属性については、「[Windows.Foundation.Metadata 名前空間](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)」を参照してください。  
  
## 使用例  
 次の例では C3099 を生成し、その修正方法を示しています。  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```