---
title: "ALIAS (MASM) | Microsoft Docs"
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
  - "Alias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIAS directive"
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ALIAS (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**エイリアス**  のディレクティブは関数の別名を作成します。  これは関数の名前を使用するとリンカー \(LINK.exe\) が新しい関数に古い関数をマップできるようにするライブラリを作成します。  
  
## 構文  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### パラメーター  
 `actual-name`  
 関数またはプロシージャの実際の名前。  山かっこが必要です。  
  
 `alias`  
 代替またはエイリアス名。  山かっこが必要です。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)