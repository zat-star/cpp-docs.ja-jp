---
title: "静的整数型定数リンケージの非リテラル化 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "定数, 宣言"
  - "整数の定数式"
  - "リテラル属性 [C++]"
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 静的整数型定数リンケージの非リテラル化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスの定数メンバーの宣言は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 `static const` の整数メンバーは引き続きサポートされていますが、その linkage 属性は変更されています。  現在は、literal の整数メンバーに以前の linkage 属性が格納されています。  たとえば、次のマネージ拡張クラスを考えます。  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 このコードは、このフィールドに対して次の CIL 基本属性を生成します \(literal 属性に注意してください\)。  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 このコードは新しい構文でもコンパイルされます。  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 ただし、literal 属性はもう生成されません。したがって、CLR ランタイムからは定数として見なされません。  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 以前と同じように中間言語の literal 属性を生成するには、新たにサポートされた `literal` データ メンバーの宣言を次のように変更する必要があります。  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## 参照  
 [クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [literal](../windows/literal-cpp-component-extensions.md)