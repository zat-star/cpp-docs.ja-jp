---
title: "規則 | Microsoft Docs"
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
helpviewer_keywords: 
  - "プリプロセッサ"
  - "プリプロセッサ, 規則"
ms.assetid: 469ce448-dc6c-4d0e-ba2b-e2e7a10155e1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 規則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

構文規則では、構文のコンポーネントごとに異なるフォント属性を使用します。  シンボルとフォントは次のとおりです。  
  
|属性|説明|  
|--------|--------|  
|*非終端要素*|斜体は、非終端要素を示します。|  
|\#include|太字で示される終端要素は、示されたとおりに入力する必要があるリテラル予約語およびシンボルです。  このコンテキストの文字は、常に大文字と小文字が区別されます。|  
|opt|後ろに opt が続く非終端要素は、常に省略可能です。|  
|既定のタイプフェイス|このタイプフェイスで記述されているか、示されているセット内の文字は、ステートメント内で終端要素として使用できます。|  
  
 非終端要素に続くコロン \(:\) は、定義の説明を示します。  代替定義は別の行に示されます。  
  
## 参照  
 [文法の概要](../preprocessor/grammar-summary-c-cpp.md)