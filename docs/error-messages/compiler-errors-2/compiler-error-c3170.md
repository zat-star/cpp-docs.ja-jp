---
title: コンパイラ エラー C3170 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 150f543ec2f75e8d21e40f822f342adef6be06c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3170"></a>コンパイラ エラー C3170
プロジェクトで別のモジュール識別子を持つことはできません。  
  
 [モジュール](../../windows/module-cpp.md)2 つのコンパイル時にファイルに異なる名前を持つ属性が見つかりました。 1 つの一意なのみ`module`コンパイルごとに属性を指定できます。  
  
 同じ`module`属性は 1 つ以上のソース コード ファイルで指定できます。  
  
 たとえば、次のモジュールの属性が見つかった場合。  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 この場合、次のようになります。  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 c3170 (別の名前に注意してください)。