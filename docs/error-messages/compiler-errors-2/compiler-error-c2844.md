---
title: "コンパイラ エラー C2844 | Microsoft Docs"
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
  - "C2844"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2844"
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2844
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : インターフェイス 'interface' のメンバーとして使用することはできません。  
  
 プロパティでない[interface class](../../windows/interface-class-cpp-component-extensions.md) にデータ メンバーを含めることはできません。  
  
 インターフェイスには、プロパティまたはメンバー関数以外は使用できません。  また、コンストラクター、デストラクター、および演算子も使用できません。  
  
 次の例では警告 C2844 が生成されます。  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  
  
 次の例では警告 C2844 が生成されます。  
  
```  
// C2844b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
__gc __interface IFace {  
   int i;   // C2844  
   // try the following line instead  
   // __property int Size { get; set; };  
};  
```