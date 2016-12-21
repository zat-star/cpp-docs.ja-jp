---
title: "フレンド アセンブリ (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "フレンド アセンブリ、Visual C++"
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# フレンド アセンブリ (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

適切なランタイム用に、*フレンド アセンブリ* アセンブリ言語機能では、一つ以上のクライアント アセンブリまたは .netmodules にアクセスできるアセンブリ コンポーネントの名前空間スコープまたはグローバル スコープ内で型を作成します。  
  
## すべてのランタイム  
 **解説**  
  
 \(この言語機能はすべてのランタイムはサポートされません\)。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **解説**  
  
 \(この言語機能は [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]ではサポートされていません\)。  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **解説**  
  
#### 型をクライアント アセンブリまたは .netmodule からアクセスできるアセンブリ コンポーネントの名前空間スコープまたはグローバル スコープで行います。  
  
1.  コンポーネントでは、アセンブリ <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性を指定して、コンポーネントの名前空間スコープまたはグローバル スコープでアクセスの種類クライアント アセンブリまたは .netmodule の名前を渡します。追加の属性を指定することで、複数のクライアント アセンブリまたは .netmodules を指定できます。  
  
2.  クライアント アセンブリまたは"で `#using`を使用して構成アセンブリを参照する場合、`as_friend` 属性を渡します。`InternalsVisibleToAttribute`を指定しないアセンブリに `as_friend` 属性を指定すると、ランタイム例外は、コンポーネントの名前空間スコープまたはグローバル スコープで型にアクセスしようとするとスローされます。  
  
 ビルド エラーが <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性を含むアセンブリが厳密な名前クライアントがありませんが、結果 `as_friend` 属性を使用するアセンブリ。  
  
 名前空間スコープとグローバル スコープの型がクライアント アセンブリまたは .netmodule に把握することはできますが、メンバーのアクセシビリティは引き続き有効です。たとえば、private メンバーにアクセスできません。  
  
 すべてのアクセスはアセンブリを明示的に許可されている入力します。たとえば、C のすべてにアクセスできないアセンブリは、アセンブリ C がアセンブリ B を参照し、B からすべてにアクセスできるアセンブリがアセンブリ A.の型およびアセンブリ A の型。  
  
 アセンブリの外側の型のアクセシビリティを指定する方法の詳細については、「[型の可視性](../Topic/Type%20Visibility.md)」を参照してください。  
  
 詳細については、署名、Visual C\+\+ コンパイラを使用してビルドされたアセンブリに厳密な名前を付ける方法を、[厳密名アセンブリ \(アセンブリ署名\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)の参照しください。  
  
 個々の型へのアクセスを制限するには、フレンド アセンブリ機能、使用を <xref:System.Security.Permissions.StrongNameIdentityPermission> を使用できるようになります。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 次のコード例、コンポーネントでその型にアクセスできるクライアント アセンブリを指定するコンポーネントを定義します。  
  
```  
// friend_assemblies.cpp  
// compile by using: /clr /LD  
using namespace System::Runtime::CompilerServices;  
using namespace System;  
// an assembly attribute, not bound to a type  
[assembly:InternalsVisibleTo("friend_assemblies_2")];  
  
ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 次のコード例はコンポーネントのプライベート型にアクセスします。  
  
```  
// friend_assemblies_2.cpp  
// compile by using: /clr  
#using "friend_assemblies.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
 **出力**  
  
 `Class1::Test_Public`  
  
 次のコード例はコンポーネントを定義しますが、コンポーネントの型にアクセスできるクライアント アセンブリを指定しません。  
  
 コンポーネントが **\/opt:noref**でリンクされることに注意してください。  `InternalsVisibleTo` 属性が存在する必要があります。これはプライベート型がコンポーネントのメタデータに表示されることを確認します。  詳細については、「[\/OPT \(最適化\)](../build/reference/opt-optimizations.md)」を参照してください。  
  
```  
// friend_assemblies_3.cpp  
// compile by using: /clr /LD /link /opt:noref  
using namespace System;  
  
ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 次のコード例はプライベート型へのアクセスを付与しないコンポーネントのプライベート型にアクセスしたクライアントを定義します。  ランタイムの動作では、例外をキャッチするには、ヘルパー関数のプライベート型にアクセスできるようにする必要があります。  
  
```  
// friend_assemblies_4.cpp  
// compile by using: /clr  
#using "friend_assemblies_3.dll" as_friend  
using namespace System;  
  
void Test() {  
   Class1 ^ a = gcnew Class1;  
}  
  
int main() {  
   // to catch this kind of exception, use a helper function  
   try {  
      Test();     
   }  
   catch(MethodAccessException ^ e) {  
      Console::WriteLine("caught an exception");  
   }  
}  
```  
  
 **出力**  
  
 `caught an exception`  
  
 次のコード例はコンポーネントの型にアクセスできるクライアント アセンブリを指定する厳密な名前のコンポーネントを作成する方法を示します。  
  
```  
// friend_assemblies_5.cpp  
// compile by using: /clr /LD /link /keyfile:friend_assemblies.snk  
using namespace System::Runtime::CompilerServices;  
using namespace System;  
// an assembly attribute, not bound to a type  
  
[assembly:InternalsVisibleTo("friend_assemblies_6, PublicKey=00240000048000009400000006020000002400005253413100040000010001000bf45d77fd991f3bff0ef51af48a12d35699e04616f27ba561195a69ebd3449c345389dc9603d65be8cd1987bc7ea48bdda35ac7d57d3d82c666b7fc1a5b79836d139ef0ac8c4e715434211660f481612771a9f7059b9b742c3d8af00e01716ed4b872e6f1be0e94863eb5745224f0deaba5b137624d7049b6f2d87fba639fc5")];  
  
private ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 コンポーネントが公開キーを指定する必要があることに注意してください。  これは、キーのペアを作成し、公開キーを取得するには、コマンド プロンプトで次のコマンドを連続的に実行することをお勧めします。:  
  
 **sn \-d friend\_assemblies.snk**  
  
 **sn \-k friend\_assemblies.snk**  
  
 **sn \-i friend\_assemblies.snk friend\_assemblies.snk**  
  
 **sn \-pc friend\_assemblies.snk key.publickey**  
  
 **sn \-tp key.publickey**  
  
 次のコード例は厳密な名前のコンポーネントのプライベート型にアクセスします。  
  
```  
// friend_assemblies_6.cpp  
// compile by using: /clr /link /keyfile:friend_assemblies.snk  
#using "friend_assemblies_5.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
 **出力**  
  
 `Class1::Test_Public`  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)