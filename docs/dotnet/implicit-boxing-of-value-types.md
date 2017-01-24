---
title: "値型の暗黙のボックス化 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__box キーワード"
  - "ボックス化"
  - "ボックス化, __box キーワード"
  - "ボックス化, Visual C++"
  - "値型, ボックス化された"
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 値型の暗黙のボックス化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値型のボックス化は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 言語デザインにおいては、これまで機能に関して実地の経験ではなく哲学的な立場を優先していましたが、結果を見ると、それは誤りでした。  類推として、元の複数継承言語デザインでは、Stroustrup が仮想基本クラス サブオブジェクトは派生クラス コンストラクター内では初期化できないと決定しました。したがって、言語では、仮想基本クラスとして機能するクラスに既定コンストラクターを定義する必要がありました。  後続の仮想派生によって呼び出されるのは、その既定コンストラクターです。  
  
 仮想基本クラス階層の問題は、共有仮想サブオブジェクトの初期化に対する責任が、後続の派生と共に移行することです。  たとえば、初期化でバッファーの割り当てが必要となる基本クラスを定義すると、そのバッファーのユーザー定義のサイズが引数としてコンストラクターに渡されます。  次に、2 つの後続の仮想派生を提供し、それらを `inputb` および `outputb` と呼ぶ場合、それぞれが特定の値を基本クラス コンストラクターに提供します。  ここで、`inputb` と `outputb` の両方から `in_out` クラスを派生した場合、共有仮想基本クラス サブオブジェクトに対するこれらの値のいずれも評価できません。  
  
 そこで、元の言語デザインにおいて、Stroustrup は派生クラス コンストラクターのメンバー初期化リスト内で仮想基本クラスを明示的に初期化することを禁止しました。  これによって問題は解決しましたが、仮想基本クラスの初期化を指示できないようにすることが、実際には実行不可能と判明しました。  より柔軟な言語デザインを開発するように、Stroustrup を主に説得したのは、nihcl と呼ばれるフリーウェア バージョンの SmallTalk コレクション ライブラリを実装した National Institute of Health の Keith Gorlen でした。  
  
 オブジェクト指向の階層デザインの原則に従えば、派生クラスはその直接の基本クラスの非プライベートな実装にのみ関係します。  仮想継承の柔軟な初期化デザインをサポートするには、Stroustrup はこの原則に違反する必要がありました。  すべての仮想サブオブジェクトの初期化の責任は、それが階層のどの深さで実行されるかにかかわりなく、階層の最派生クラスが持ちます。  たとえば、`inputb` と `outputb` は両方とも、それらの直接の仮想基本クラスの明示的な初期化の責任を負います。  `in_out` が `inputb` と `outputb` の両方から派生した場合、`in_out` はかつて削除された仮想基本クラスの初期化の責任を負い、`inputb` および `outputb` 内で明示的に行われた初期化は抑止されます。  
  
 これによって、言語開発者が要求する柔軟性は得られますが、その代償としてセマンティクスが複雑になります。  仮想基本クラスに状態を含まずにインターフェイスを指定できるようにすることで、この複雑さは取り除かれます。  これは C\+\+ で推奨されるデザイン イディオムです。  CLR プログラミングでは、インターフェイス型を持つポリシーに発展しています。  
  
 単純なコード サンプルを次に示します。この場合、明示的なボックス化は不要です。  
  
```  
// Managed Extensions for C++ requires explicit __box operation  
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };  
Object* myObjArray __gc[] = {   
   __box(26), __box(27), __box(28), __box(29), __box(30)  
};  
  
Console::WriteLine( "{0}\t{1}\t{2}", __box(0),  
   __box(my1DIntArray->GetLowerBound(0)),  
   __box(my1DIntArray->GetUpperBound(0)) );  
```  
  
 ご覧のように、多数のボックス化が行われます。  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では値型のボックス化は暗黙的に行われます。  
  
```  
// new syntax makes boxing implicit  
array<int>^ my1DIntArray = {1,2,3,4,5};  
array<Object^>^ myObjArray = {26,27,28,29,30};  
  
Console::WriteLine( "{0}\t{1}\t{2}", 0,   
   my1DIntArray->GetLowerBound( 0 ),   
   my1DIntArray->GetUpperBound( 0 ) );  
```  
  
## 参照  
 [値型とその動作 \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Boxing](../windows/boxing-cpp-component-extensions.md)