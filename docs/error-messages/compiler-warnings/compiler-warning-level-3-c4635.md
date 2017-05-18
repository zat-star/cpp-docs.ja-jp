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
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d4c85ca32903e20ea18a731872c25ee999b67f89
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

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
  
 このサンプルでの問題は、終了タグの\<概要 > が不完全で、コンパイラが認識しないこととして、\<概要 > 終了タグ。  \<メンバー > タグは、/doc のコンパイルごとに、コンパイラによって .xdc ファイルに埋め込まれています。  そのため、ここでの問題は、終了タグ\</member >、コンパイラが処理される前の開始タグと一致しません (\<概要 > です。
