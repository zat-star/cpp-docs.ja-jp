---
title: "あいまいな宣言 (C++) を解決する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70c010cf3806581c6b77bb508f3adb68e3c230f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resolving-ambiguous-declarations-c"></a>あいまいな宣言 (C++) の解決
特定の型から別の型に明示的に変換するには、キャストを使用し、目的の型名を指定する必要があります。 一部の型キャストでは、構文にあいまいさが発生します。 次の関数形式の型キャストはあいまいです。  
  
```  
char *aName( String( s ) );  
```  
  
 関数宣言と関数スタイルの初期化子としてキャストでオブジェクトの宣言であるか明確ではありません型を返す関数を宣言できません**char \*** 型の 1 つの引数を取る`String`。、またはオブジェクトを宣言でした`aName`しの値で初期化`s`型へのキャスト`String`です。  
  
 宣言を有効な関数宣言と見なすことができれば、それは関数の宣言として扱われます。 宣言が関数宣言とは考えられない (つまり、関数宣言だとすれば構文的に正しくないと考えられる) 場合にのみ、そのステートメントが関数形式の型キャストかどうかが確認されます。 したがって、コンパイラはこのステートメントを関数の宣言であると見なし、識別子 `s` を囲むかっこを無視します。 一方、次のステートメント、  
  
```  
char *aName( (String)s );  
```  
  
 と、呼び出し  
  
```  
char *aName = String( s );  
```  
  
 オブジェクト、およびユーザー定義型から変換の宣言では明らかに`String`入力**char \*** の初期化を行うために呼び出される`aName`です。  
  
## <a name="see-also"></a>参照  
 