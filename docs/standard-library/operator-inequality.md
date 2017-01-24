---
title: "operator!= | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::!="
  - "!="
  - "std::operator!="
  - "std.operator!="
  - "std.!="
  - "operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= 演算子"
  - "演算子 !="
  - "operator!="
ms.assetid: ef2be7f0-1c94-4edc-b65c-731fddd519f4
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator!=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  このトピックでは、標準 C\+\+ ライブラリで使用されるコンテナーの、機能的な例として、Visual C\+\+ のドキュメントにあります。  詳細については、「[STL コンテナー](../standard-library/stl-containers.md)」を参照してください。  
  
 `operator!=` をテンプレート クラス [コンテナー](../Topic/Sample%20Container%20Class.md)の 2 種類のオブジェクトを比較するオーバーロードします。  
  
## 構文  
  
```  
  
   template<class Ty>  
bool operator!=(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## 戻り値  
 \#\#\#\! \(\_Left **\=\=** `_Right`\) を返します。  
  
## 参照  
 [\<sample container\>](../standard-library/sample-container.md)