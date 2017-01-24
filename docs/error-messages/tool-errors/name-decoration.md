---
title: "名前の装飾 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "装飾名, 呼び出し規約"
  - "名前の装飾 [C++]"
  - "名前 [C++], 装飾"
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 名前の装飾
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

名前の装飾は、通常は C\+\+ の名前付け規則を指しますが、C の場合でもよく適用されます。  既定では、C\+\+ では関数名、パラメーター、および戻り値の型を使用して、関数のリンカー名が作成されます。  次の関数について考えてみます。  
  
```  
void CALLTYPE test(void)  
```  
  
 次の表は、さまざまな呼び出し規約のリンカー名を示します。  
  
|呼び出し規約|extern"C"または .c ファイル|.cpp、.cxx、または \/TP|  
|------------|--------------------------|------------------------|  
|C の名前付け規則 \(`__cdecl`\)|\_test|?test@@ZAXXZ|  
|Fastcall 名前付け規則 \(`__fastcall`\)|@test@0|?test@@YIXXZ|  
|標準呼び出しの名前付け規則 \(`__stdcall`\)|\_test@0|?test@@YGXXZ|  
|Vectorcall 名前付け規則 \(`__vectorcall`\)|test@@0|?test@@YQXXZ|  
  
 C\+\+ から C の関数を呼び出すには、extern "C" を使用します。  extern "C" を指定すると、クラスに属さない C\+\+ の関数に対しては、C 名前付け規則が適用されます。  コンパイラ スイッチ **\/Tc** または **\/Tp** に注意してください。これらは、ファイル名の拡張子を無視し、ファイルをそれぞれ C または C\+\+ としてコンパイルするように指示します。  これらのオプションを使用すると、予測した名前にならないことがあります。  
  
 関数プロトタイプのパラメーターが一致していないと、このエラーが発生します。  名前の装飾では、関数のパラメーターを最終の装飾関数名に組み込みます。  関数宣言でのパラメーターと一致していない関数を呼び出すと、LNK2001 が発生することがあります。  
  
 現在では、コンパイラ販売元間またはコンパイラのバージョン間でさえも、C\+\+ の名前付けの規則が確立されていません。  そのため、別のコンパイラでコンパイルされたオブジェクト ファイルをリンクすると、名前付け方式が異なり、外部参照が未解決になります。  
  
## 参照  
 [リンカ ツール エラー LNK2001](../Topic/Linker%20Tools%20Error%20LNK2001.md)