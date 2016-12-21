---
title: "変換: 診断 | Microsoft Docs"
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
  - "C"
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 変換: 診断
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 2.1.1.3** 診断を識別する方法  
  
 Microsoft C は、次の形式のエラー メッセージを生成します。  
  
```  
  
filename( line-number ) : diagnostic Cnumber message  
```  
  
 ここで、*filename* はエラーが発生したソース ファイルの名前、*line\-number* はコンパイラがエラーを検出した行番号、`diagnostic` は "error" または "warning"、`number` は \(構文に示すように先頭に **C** が付いた\) 一意の 4 桁の番号、`message` は説明メッセージです。  
  
## 参照  
 [実装で定義する動作](../c-language/implementation-defined-behavior.md)