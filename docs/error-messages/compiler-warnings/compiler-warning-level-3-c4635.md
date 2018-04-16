---
title: "コンパイラの警告 (レベル 3) C4635 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16b6a19618afeed952cfa594961a0e4ccb777d26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4635"></a>コンパイラの警告 (レベル 3) C4635
XML ドキュメント コメント対象: XML の形式が正しくありません: 理由  
  
 コンパイラは XML タグに何らかの問題を検出しました。  問題を修正して再コンパイルします  
  
 次の例では C4635 が生成されます。  
  
```  
// C4635.cpp  
// compile with: /doc /clr /W3 /c  
/// <summary>     
/// The contents of the folder have changed.  
/// <summary/>   // C4635  
  
// try the following line instead  
// /// </summary>  
public ref class Test {};  
```  
  
 このサンプルの次の出力に注意してください: **'member' の終了タグが開始タグ 'summary' と一致しません。**  
  
 このサンプルでの問題は、終了タグの\<概要 > が不完全で、コンパイラが認識しないこととして、\<概要 > 終了タグ。  \<メンバー > タグは、/doc のコンパイルごとに、コンパイラによって .xdc ファイルに埋め込まれています。  そのため、ここでの問題は、終了タグ\</member >、コンパイラが処理される前の開始タグと一致しません (\<概要 >。