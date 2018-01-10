---
title: "コンパイラの警告 (レベル 4) C4001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4001
dev_langs: C++
helpviewer_keywords: C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3b5c3d82bef81ee84514b39a0ce8ab07ad6e6c36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4001"></a>コンパイラの警告 (レベル 4) C4001
標準の拡張機能 '単一行コメントが使用されました  

> [!NOTE] 
> この警告は、単一行コメントは C99 に標準的なために、Visual Studio 2017 15.5 のバージョンで削除されます。
  
 単一行コメントは、C++ の標準 standard C の C99 で起動します。 厳密な ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、単一行コメントが含まれている C ファイルは、標準の拡張機能の使用状況のため C4001 を生成します。 単一行コメントが C++ の標準的なため、単一行コメントを含む C ファイル生成しない C4001 Microsoft 拡張機能 (/Ze) でコンパイルするときにします。  
  
## <a name="example"></a>例  
 警告を無効にするにコメントを解除[#pragma warning(disable:4001)](../../preprocessor/warning.md)です。  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```