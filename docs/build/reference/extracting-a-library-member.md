---
title: "ライブラリ メンバーの抽出 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXTRACT ライブラリ マネージャー オプション"
  - "EXTRACT ライブラリ マネージャー オプション"
  - "-EXTRACT ライブラリ マネージャー オプション"
  - "抽出 (ライブラリ メンバーを)"
  - "LIB [C++], 抽出 (ライブラリ メンバーを)"
  - "ライブラリ, 抽出 (メンバーを)"
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# ライブラリ メンバーの抽出
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB では、既存のライブラリのメンバーからオブジェクト \(.obj\) ファイルを作成できます。  メンバーを抽出するには、次の構文を使用します。  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 このコマンドでは、*objectfile* という名前の .obj ファイルが作成されます。この内容は、*library* で指定したライブラリの `member` というメンバーのコピーです。  メンバー名 \(`member`\) では、大文字と小文字が区別されます。  1 つのコマンドで抽出できるメンバーは 1 つだけです。  既定の出力名はないので、\/OUT オプションを必ず指定します。  指定したフォルダー \(*objectfile* でフォルダーを指定しなかった場合は現在のフォルダー\) に *objectfile* と同じ名前のファイルがあると、出力ファイルで上書きされます。  
  
## 参照  
 [LIB リファレンス](../../build/reference/lib-reference.md)