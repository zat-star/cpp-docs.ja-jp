---
title: "リンカー ツールの警告 LNK4254 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4254"
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# リンカー ツールの警告 LNK4254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

セクション 'section1' \('オフセット'\) は 'section2' \('オフセット'\) に異なる属性を伴ってマージされています  
  
 1 つのセクションの内容が別のセクションにマージされましたが、この 2 つのセクションの属性が異なっています。  予期しない結果になる可能性があります。  たとえば、読み込み専用にするデータが書き込み可能なセクションに置かれている可能性があります。  
  
 LNK4254 を解決するには、マージ要求を変更するか、削除します。  
  
 Visual C\+\+ で x86 コンピューターと Windows CE ターゲット プラットフォーム \(ARM、MIPS、SH4、および Thumb\) を対象としている場合、.CRT セクションは読み取り専用です。  コードが以前の動作 \(.CRT セクションが読み書き可能\) に依存している場合、予期しない動作が発生することがあります。  
  
 詳細については、次のトピックを参照してください。  
  
-   [\/MERGE \(セクションの結合\)](../../build/reference/merge-combine-sections.md)  
  
-   [コメント](../../preprocessor/comment-c-cpp.md)  
  
## 使用例  
 次の例では LNK4254 エラーが生成されます。  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```