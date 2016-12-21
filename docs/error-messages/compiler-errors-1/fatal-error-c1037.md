---
title: "致命的なエラー C1037 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1037"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1037"
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1037
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オブジェクト ファイル filename を開くことができません  
  
 [\/Fo](../../build/reference/fo-object-file-name.md) で指定されたオブジェクト ファイルを開くことができません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  ファイル名が無効です。  
  
2.  ファイルを開くためのメモリが不足しています。  
  
3.  別のプロセスでファイルを使用しています。  
  
4.  同じ名前の読み取り専用ファイルが存在します。  
  
 Visual C\+\+ .NET \(コンパイラ バージョン 1300\) には、ファイル名 \(またはファイル名へのディレクトリ パス\) に MBCS 文字が含まれている場合に、ユーザー ロケールの正しい設定を要求するというバグがあります。 システム ロケールを設定するだけでは不十分です。MBCS 文字を処理するようにユーザー ロケールを設定する必要があります。