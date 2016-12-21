---
title: "optimize | Microsoft Docs"
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
  - "vc-pragma.optimize"
  - "optimize_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "optimize プラグマ"
  - "プラグマ, optimize"
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# optimize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

実行する最適化を関数ごとに指定します。  
  
## 構文  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## 解説  
 **optimize** プラグマは関数の外側に記述する必要があります。optimize プラグマの後、最初に定義されている関数にそのプラグマが適用されます。  **on** 引数と **off** 引数は、*optimization\-list* で指定されているオプションのオンとオフを切り替えます。  
  
 *optimization\-list* には、次の表に示す 0 個以上のパラメーターを指定できます。  
  
### optimize プラグマのパラメーター  
  
|パラメーター|最適化の種類|  
|------------|------------|  
|**g**|グローバル最適化を有効にします。|  
|**s** または **t**|マシン語コードの省略シーケンスまたは高速シーケンスを指定します。|  
|**y**|プログラム スタックにフレーム ポインターを生成します。|  
  
 これらは [\/O](../build/reference/o-options-optimize-code.md) コンパイラ オプションで使用する文字と同じです。  たとえば、次のプラグマは **\/Os** コンパイラ オプションと等価です。  
  
```  
#pragma optimize( "ts", on )  
```  
  
 **optimize** プラグマの特殊な形式として、空の文字列 \(**""**\) でこのディレクティブを使用できます。  
  
 **off** パラメーターを使用すると、前述の表で示した最適化がオフになります。  
  
 **on** パラメーターを使用すると、[\/O](../build/reference/o-options-optimize-code.md) コンパイラ オプションで指定した最適化にリセットされます。  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)