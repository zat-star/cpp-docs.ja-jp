---
title: "変換演算子に対する変更点 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "変換演算子"
  - "変換, explicit"
  - "explicit キーワード [C++]"
  - "演算子 [C++], 明示的な型変換"
  - "型変換, 明示的な変換"
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 変換演算子に対する変更点
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

変換演算子の構文は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 その 1 つの例が `op_Implicit` を記述することによる変換の指定です。  たとえば、その言語仕様に従って記述された `MyDouble` の定義を考えてみます。  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 これは、整数を指定すると、その整数を `MyDouble` に変換するアルゴリズムが `op_Implicit` 演算子によって提供されることを記述しています。  さらに、その変換はコンパイラによって暗黙的に実行されます。  同様に、`MyDouble` オブジェクトを指定すると、2 つの `op_Explicit` 演算子がそのオブジェクトを整数またはマネージ `String` エンティティのいずれかに変換するアルゴリズムを提供します。  ただし、ユーザーによって明示的に要求されない場合、コンパイラは変換を実行しません。  
  
 C\# では、これは次のようになります。  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 C\+\+ マネージ拡張よりも、C\# コードの方が C\+\+ に近い感じがします。  新しい構文では、この違和感が解消されています。  
  
 ISO\-C\+\+ 委員会は、予期しない結果を防ぐために、キーワード `explicit` を採用しました。たとえば、`Array` クラスは、配列の次元を表す整数型の引数を 1 つ受け取りますが、この場合、意図に反して、あらゆる整数が `Array` オブジェクトに変換されます。  これを回避する手段の 1 つに、コンストラクターにダミーの第 2 引数を指定する方法があります。  
  
 一方、C\+\+ でクラス型を設計しているときに、変換ペアを作成するのは良い考えとは言えません。  その最も良い例は標準文字列クラスです。  暗黙の変換では、単一引数コンストラクターが C スタイル配列を受け付けます。  しかし、対応する暗黙の変換演算子、つまり文字列オブジェクトを C スタイル配列に変換する演算子は提供されません。代わりに、ユーザーが名前付き関数、この場合は `c_str()` を明示的に呼び出すことが要求されます。  
  
 変換演算子への暗黙的および明示的処理の追加 \(および変換セットの単一宣言形式へのカプセル化\) は、C\+\+ の当初の変換演算子サポートに対する機能改善と考えられます。こうした動きが最終的に `explicit` キーワードの導入へとつながっています。  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] 言語の変換演算子に対するサポートは次のとおりです。変換アルゴリズムの暗黙のアプリケーションをサポートする演算子の既定の動作が原因で、C\# よりはいくぶん短めです。  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 もう 1 つの変更点は、単一引数コンストラクターが、`explicit` として宣言された場合と同じように扱われることです。  つまり、その呼び出しを発生させるには、明示的なキャストが必要です。  ただし、明示的な変換演算子が定義されている場合はそれが呼び出され、単一引数コンストラクターは呼び出されません。  
  
## 参照  
 [クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)