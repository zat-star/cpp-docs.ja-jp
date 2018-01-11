---
title: "リンカー ツールの警告 LNK4224 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4224
dev_langs: C++
helpviewer_keywords: LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96399e0c66eb3cb719073b2318513cd680723d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4224"></a>リンカー ツールの警告 LNK4224
オプションはサポートされなくなりました。無視されます。  
  
 無効な古いリンカー オプションが指定され、無視されます。  
  
 たとえば、LNK4224 発生する可能性が/comment ディレクティブが表示される場合 obj.。使用して追加されて、/comment ディレクティブ、[コメント (C/C++)](../../preprocessor/comment-c-cpp.md)プラグマによって、非推奨 exestr オプションを使用します。 Dumpbin を使用して[/all](../../build/reference/all.md)を .obj ファイル内のリンカー ディレクティブを表示します。  
  
 可能であれば、.obj ファイルのソースを変更し、このプラグマを削除します。 この警告を無視すると場合、.executable コンパイルされている可能性が**/clr: 純粋な**期待どおりに実行されません。  
  
## <a name="example"></a>例  
 次の例では、LNK4224 が生成されます。  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```