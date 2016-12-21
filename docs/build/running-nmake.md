---
title: "NMAKE の実行 | Microsoft Docs"
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
  - "コマンド ファイル"
  - "コマンド ファイル, NMAKE"
  - "NMAKE プログラム, 実行"
  - "NMAKE プログラム, ターゲット"
  - "応答ファイル, NMAKE"
  - "ターゲット"
  - "ターゲット, ビルド"
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の実行
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## 解説  
 NMAKE は、指定された *targets* だけをビルドします。ターゲットが指定されていない場合は、メイクファイルの最初のターゲットがビルドされます。  メイクファイルの最初のターゲットは、ほかのターゲットをビルドするための[疑似ターゲット](../build/pseudotargets.md)である場合もあります。  NMAKE は、\/F で指定されたメイクファイルを使用します。\/F が指定されていない場合は、現在のディレクトリにある Makefile ファイルを使用します。  メイクファイルが \/F で指定されず、既定の Makefile もない場合は、推論規則を使用してコマンド ラインの *targets* がビルドされます。  
  
 `commandfile` テキスト ファイル \(または応答ファイル\) には、コマンド ラインの入力が記述されています。  ほかの入力は、@`commandfile` の前後に指定できます。  パスも指定できます。  `commandfile` では、改行は空白として扱われます。  マクロ定義に空白が含まれている場合は、マクロ定義を引用符で囲みます。  
  
## さらに詳しくは次のトピックをクリックしてください  
 [NMAKE のオプション](../Topic/NMAKE%20Options.md)  
  
 [Tools.ini と NMAKE](../build/tools-ini-and-nmake.md)  
  
 [NMAKE で返される終了コード](../build/exit-codes-from-nmake.md)  
  
## 参照  
 [NMAKE リファレンス](../build/nmake-reference.md)