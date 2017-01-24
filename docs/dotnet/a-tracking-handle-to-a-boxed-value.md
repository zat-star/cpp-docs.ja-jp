---
title: "追跡ハンドルからボックス化変換された値へ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "ボックス化された値型, 追跡 (ハンドルを)"
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 追跡ハンドルからボックス化変換された値へ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値型を参照するために追跡ハンドルを使用する方法は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 ボックス化は CLR 統一型システムの特性です。  値型はその状態を直接格納し、一方、参照型は暗黙的なペアです。名前付きエンティティは、マネージ ヒープに割り当てられた名前のないオブジェクトのハンドルです。  たとえば、値型を `Object` に割り当てたり初期化したりするには、最初に関連メモリを割り当て、次に値型の状態をコピーし、さらにこの匿名値\/参照ハイブリッドの値を返して、値型を CLR ヒープ内に配置する必要があります。値型をボックス化するイメージは CLR ヒープで発生します。  これを C\# で記述すると次のようになります。  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 実際には、簡素化されたコードで示されるよりもかなり多くのことが行われます。  C\# のデザインは、内部で行われている操作の複雑さだけでなく、ボックス化自体の抽象化の複雑さも隠します。  これに対し、C\+\+ マネージ拡張はこれが効率性の誤った認識につながると考え、ユーザーに正しい感覚を持たせるために、明示的な命令を要求します。  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] ではボックス化の使用は暗黙的です。  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 `__box` キーワードは、C\# や [!INCLUDE[vbprvb](../Token/vbprvb_md.md)] などの言語によるデザインでは削除される、より重要なサービスのためにマネージ拡張で使用されています。つまり、マネージ ヒープ上でボックス化変換されたインスタンスを直接操作するための、ボキャブラリとトラッキング ハンドルの両方を提供します。  たとえば次の小規模プログラムを考えてみます。  
  
```  
int main() {  
   double result = 3.14159;  
   __box double * br = __box( result );  
  
   result = 2.7;   
   *br = 2.17;     
   Object * o = br;  
  
   Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
   Console::WriteLine( S"result :: {0}", __box(result) ) ;  
   Console::WriteLine( S"result :: {0}", br );  
}  
```  
  
 `WriteLine` の 3 回の呼び出しで生成されるコードは、ボックス化された値型の値にアクセスする際の各コストを示します \(これらの相違を指摘していただいた Yves Dolce に感謝します\)。ここで、強調した行は各呼び出しに関連するオーバーヘッドを示しています。  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
call       void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", __box(result) ) ;  
Ldstr    " result :: {0}"  
ldloc.0  
box    [mscorlib]System.Double // box overhead  
call    void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", br );  
ldstr    "result :: {0}"  
ldloc.0  
call     void [mscorlib]System.Console::WriteLine(string, object)  
```  
  
 ボックス化された値型を `Console::WriteLine` に直接渡すことで、ボックス化と `ToString()` の呼び出しが不要になります \(もちろん、`br` を初期化するためのボックス化がこの前にあります。`br` を初期化しなければ、それ以降の処理を行うことはできません\)。  
  
 新しい構文では、ボックス化された値型のサポートが大幅に改善され、型システムに統合されると同時に、その強力さが保持されています。  たとえば、上の小規模プログラムを変換すると次のようになります。  
  
```  
int main()  
{  
   double result = 3.14159;  
   double^ br = result;  
   result = 2.7;  
   *br = 2.17;  
   Object^ o = br;  
   Console::WriteLine( "result :: {0}", result.ToString() );  
   Console::WriteLine( "result :: {0}", result );  
   Console::WriteLine( "result :: {0}", br );  
}  
```  
  
## 参照  
 [値型とその動作 \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [方法: 明示的にボックス化を要求する](../Topic/How%20to:%20Explicitly%20Request%20Boxing.md)