---
title: "リンカ ツール エラー LNK1179 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93b042e928331e369d64a45aa27f5f613ce9fc31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1179"></a>リンカ ツール エラー LNK1179
ファイルが無効か破損しています: COMDAT 'filename' を複製します。  
  
 オブジェクト モジュールには、同じ名前の 2 つ以上の Comdat が含まれています。  
  
 使用してこのエラーは発生する[/H](../../build/reference/h-restrict-length-of-external-names.md)、外部名の長さを制限して[/Gy](../../build/reference/gy-enable-function-level-linking.md)Comdat に関数をパッケージ化します。  
  
## <a name="example"></a>例  
 次のコードに`function1`と`function2`が最初の 8 文字と一致します。 コンパイルする**/Gy**と**/H8**リンク エラーが生成されます。  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```