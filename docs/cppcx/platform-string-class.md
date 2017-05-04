---
title: "Platform::String クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String"
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::String クラス
テキストを表現するために使用される Unicode 文字のシーケンシャル コレクションを表します。 使用例を含む詳細については、「[文字列](../cppcx/strings-c-cx.md)」を参照してください。  
  
## 構文  
  
```cpp  
  
public ref class String sealed : Object,  
    IDisposable,  
    IEquatable,  
    IPrintable  
```  
  
## 反復子  
 String クラスのメンバーではない 2 つの反復子関数を `std::for_each` テンプレート関数で使用して、String オブジェクトの文字列を列挙できます。  
  
|メンバー|説明|  
|----------|--------|  
|`const char16* begin(String^ s)`|指定された String オブジェクトの始まりへのポインターを返します。|  
|`const char16* end(String^ s)`|指定された String オブジェクトの末尾を越えたポインターを返します。|  
  
## メンバー  
 String クラスは、Object、および IDisposable、IEquatable、および IPrintable interfaces の各インターフェイスから継承します。  
  
 String クラスには、次の種類のメンバーの種類もあります。  
  
 **コンストラクター**  
  
|メンバー|説明|  
|----------|--------|  
|[String::String コンストラクター](../cppcx/string-string-constructor.md)|String クラスの新しいインスタンスを初期化します。|  
  
 **メソッド**  
  
 String クラスは、[Platform::Object クラス](../cppcx/platform-object-class.md) の Equals\(\)、Finalize\(\)、GetHashCode\(\)、GetType\(\)、MemberwiseClose\(\)、および ToString\(\) の各メソッドを継承します。 String には、次のメソッドもあります。  
  
|メソッド|説明|  
|----------|--------|  
|[String::Begin メソッド](../cppcx/string-begin-method.md)|現在の文字列の先頭へのポインターを返します。|  
|[String::CompareOrdinal メソッド](../cppcx/string-compareordinal-method.md)|オブジェクトによって表される 2 つの文字列値に含まれる、対応する文字列の数値を評価することにより、2 つの `String` オブジェクトを比較します。|  
|[String::Concat メソッド](../cppcx/string-concat-method.md)|指定された 2 つの String オブジェクトの値を連結します。|  
|[String::Data メソッド](../cppcx/string-data-method.md)|現在の文字列の先頭へのポインターを返します。|  
|[String::Dispose メソッド](../cppcx/string-dispose-method.md)|リソースを解放またはリソースします。|  
|[String::End メソッド](../cppcx/string-end-method.md)|現在の文字列の末尾を越えたポインターを返します。|  
|[String::Equals メソッド](../cppcx/string-equals-method.md)|指定されたオブジェクトが現在のオブジェクトと等しいかどうかを示します。|  
|[String::GetHashCode メソッド](../cppcx/string-gethashcode-method.md)|このインスタンスのハッシュ コードを返します。|  
|[String::IsEmpty メソッド](../cppcx/string-isempty-method.md)|現在の String オブジェクトが空かどうかを示します。|  
|[String::IsFastPass メソッド](../cppcx/string-isfastpass-method.md)|現在の文字列オブジェクトを*高速渡し*操作に含めるかどうかを示します。 高速渡し操作では、参照カウントは中断されます。|  
|[String::Length メソッド](../cppcx/string-length-method.md)|現在の String オブジェクトの長さを取得します。|  
|[String::ToString メソッド](../cppcx/string-tostring-method-c-cx.md)|値が現在の文字列と同じである String オブジェクトを返します。|  
  
 **プロパティ**  
  
 String クラスには、次のプロパティがあります。  
  
|メンバー|説明|  
|----------|--------|  
|[String::operator\=\= 演算子](../cppcx/string-operator-equality-operator-c-cx.md)|指定された 2 つの String オブジェクトの値が同じかどうかを示します。|  
|[operator\+ Operator](../cppcx/string-operator-decrementoperator.md)|2 つの String オブジェクトを連結して新しい String オブジェクトを作成します。|  
|[String::operator\> 演算子](../cppcx/string-operator-greater-than-operator-c-cx.md)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より大きいかどうかを示します。|  
|[String::operator\>\= 演算子](../cppcx/string-operator-greater-than-or-equals-c-cx.md)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値以上かどうかを示します。|  
|[String::operator\!\= 演算子](../cppcx/string-operator-inequality-operator-c-cx.md)|指定された 2 つの String オブジェクトの値が異なるかどうかを示します。|  
|[String::operator\< 演算子](../cppcx/string-operator-less-than-operator-c-cx.md)|1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より小さいかどうかを示します。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー** vccorlib.h \(既定でインクルードされる\)  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)