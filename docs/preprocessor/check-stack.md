---
title: "check_stack | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.check_stack"
  - "check_stack_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "check_stack プラグマ"
  - "プラグマ, check_stack"
  - "プラグマ, check_stack 使用状況テーブル"
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# check_stack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**off** \(または **–**\) が指定されている場合には、スタック プローブをオフにし、**on** \(または **\+**\) が指定されている場合には、スタック プローブをオンにするようにコンパイラに指示します。  
  
## 構文  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | –}  
```  
  
## 解説  
 引数を指定しない場合、スタック プローブが既定に従って処理されます。  このプラグマは、プラグマの後で定義されている最初の関数に対して効果があります。  スタック プローブは、マクロの一部でも、インラインで生成される関数の一部でもありません。  
  
 **check\_stack** プラグマの引数を指定しない場合、スタック チェックは、コマンド ラインで指定する動作に戻ります。  詳細については、「[コンパイラ リファレンス](../build/reference/compiler-options.md)」を参照してください。  **\#pragma check\_stack** と [\/Gs](../build/reference/gs-control-stack-checking-calls.md) オプションの相互作用を次の表に示します。  
  
### check\_stack プラグマの使用  
  
|構文|コンパイルで<br /><br /> \/Gs オプションを使用?|アクション|  
|--------|-------------------------------|-----------|  
|**\#pragma check\_stack\( \)** または<br /><br /> **\#pragma check\_stack**|○|後続の関数のスタック チェックをオフにします|  
|**\#pragma check\_stack\( \)** または<br /><br /> **\#pragma check\_stack**|Ｘ|後続の関数のスタック チェックをオンにします|  
|**\#pragma check\_stack\(on\)**<br /><br /> または **\#pragma check\_stack \+**|Yes または No|後続の関数のスタック チェックをオンにします|  
|**\#pragma check\_stack\(off\)**<br /><br /> または **\#pragma check\_stack –**|Yes または No|後続の関数のスタック チェックをオフにします|  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)