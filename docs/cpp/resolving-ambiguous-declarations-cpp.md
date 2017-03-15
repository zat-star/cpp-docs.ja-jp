---
title: "あいまいさの解決 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# あいまいさの解決
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

特定の型から別の型に明示的に変換するには、キャストを使用し、目的の型名を指定する必要があります。  一部の型キャストでは、構文にあいまいさが発生します。  次の関数形式の型キャストはあいまいです。  
  
```  
char *aName( String( s ) );  
```  
  
 これは、関数宣言なのか、関数形式のキャストを初期化子として使用したオブジェクト宣言なのか、明確ではありません。つまり、`String` 型の 1 つの引数を受け取り、**char \*** 型を返す関数を宣言している可能性もあれば、`aName` オブジェクトを宣言し、そのオブジェクトを `String` 型にキャストされた値 `s` で初期化している可能性もあります。  
  
 宣言を有効な関数宣言と見なすことができれば、それは関数の宣言として扱われます。  宣言が関数宣言とは考えられない \(つまり、関数宣言だとすれば構文的に正しくないと考えられる\) 場合にのみ、そのステートメントが関数形式の型キャストかどうかが確認されます。  したがって、コンパイラはこのステートメントを関数の宣言であると見なし、識別子 `s` を囲むかっこを無視します。  一方、次のステートメント、  
  
```  
char *aName( (String)s );  
```  
  
 および  
  
```  
char *aName = String( s );  
```  
  
 は、明らかにオブジェクトの宣言であるため、`String` 型から **char \*** 型へのユーザー定義変換が呼び出されて、`aName` の初期化が実行されます。  
  
## 参照  
 [C\+\+ Abstract Declarators](http://msdn.microsoft.com/ja-jp/e7e18c18-0cad-4450-942b-d27e1d4dd088)