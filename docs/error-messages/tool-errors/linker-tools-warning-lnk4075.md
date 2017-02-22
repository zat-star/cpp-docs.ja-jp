---
title: "リンカー ツールの警告 LNK4075 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4075"
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# リンカー ツールの警告 LNK4075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"option1" は "option2" の指定によって無視されます。  
  
 最初のオプションは 2 番目のオプションでオーバーライドされます。  
  
 同時に指定できないリンカー オプションが指定されています。リンカー オプションを調べてください。リンカー オプションが指定されている場所は、プロジェクトをビルドしている方法によって異なります。  
  
-   開発環境でビルドしている場合は、プロジェクトのリンカー プロパティ ページを調べて、両方のリンカー オプションが指定されている場所を探します。詳細については、「[方法 : &#91;プロパティ ページ&#93; でプロジェクトのプロパティを指定する](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md)」を参照してください。  
  
-   コマンド ラインでビルドする場合は、そこで指定されているリンカー オプションを調べます。  
  
-   ビルド スクリプトでビルドする場合は、スクリプトで、これらのリンカー オプションが指定されている場所を調べます。  
  
 同時に指定できないリンカー オプションが指定されている場所が見つかったら、いずれかのリンカー オプションを削除します。  
  
 具体例 :  
  
-   **\/ZI** を指定してコンパイルされ、\/EDITANDCONTINUE という内部リンカー オプションが暗黙に指定されているモジュールと、\/OPT:REF、\/OPT:ICF、または \/INCREMENTAL:NO のいずれかを指定してコンパイルされ、暗黙に \/EDITANDCONTINUE を指定しないモジュールをリンクする場合、LNK4075 が発生します。詳細については、「[\/Z7、\/Zi、\/ZI \(デバッグ情報の形式\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)」を参照してください。