---
title: "リンカー ツールの警告 LNK4253 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4253"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4253"
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4253
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

セクション 'section1' は 'section2' にマージされていません。既に 'section3' にマージされています  
  
 競合する複数のマージ要求が検出されました。  リンカーはいずれかの要求を無視します。  
  
 **\/MERGE** オプションまたはディレクティブが検出されましたが、その `from` セクションは、前にあった **\/MERGE** オプションまたはディレクティブ \(またはリンカーからの暗黙のマージ\) によって、既に別のセクションにマージされています。  
  
 LNK4253 警告を解決するには、いずれかのマージ要求を削除します。  
  
 Visual C\+\+ で x86 コンピューターと Windows CE ターゲット プラットフォーム \(ARM、MIPS、SH4、および Thumb\) を対象としている場合、.CRT セクションは読み取り専用です。  コードが以前の動作 \(.CRT セクションが読み書き可能\) に依存している場合、予期しない動作が発生することがあります。  
  
 詳細については、次のトピックを参照してください。  
  
-   [\/MERGE \(セクションの結合\)](../../build/reference/merge-combine-sections.md)  
  
-   [コメント](../../preprocessor/comment-c-cpp.md)  
  
## 使用例  
 次の例では、リンカーに `.rdata` セクションのマージを 2 回指示してますが、マージ先のセクションが異なります。  次の例では LNK4253 エラーが生成されます。  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```