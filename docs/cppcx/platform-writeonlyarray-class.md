---
title: "Platform::WriteOnlyArray クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
s.suite: 
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::WriteOnlyArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::WriteOnlyArray クラス"
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
caps.latest.revision: 11
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 11
---
# Platform::WriteOnlyArray クラス
メソッドで設定する配列を呼び出し元から渡すときに入力パラメーターとして使用される 1 次元配列を表します。  
  
 この ref クラスは vccorlib.h でプライベートとして宣言されています。したがって、メタデータには出力されず、C\+\+ からのみ使用できます。 このクラスは、呼び出し元が割り当てた配列を受け取る入力パラメーターとして使用することのみを目的としています。 ユーザー コードから構築することはできません。 このクラスでは、C\+\+ メソッドでその配列に直接書き込むことができます。このパターンは、*FillArray* パターンと呼ばれます。 詳細については、「[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。  
  
## 構文  
  
```cpp  
private ref class WriteOnlyArray<T, 1>  
```  
  
## メンバー  
  
### パブリック メソッド  
 これらのメソッドのアクセシビリティは内部です。つまり、これらのメソッドには C\+\+ アプリまたはコンポーネント内でのみアクセスできます。  
  
|名前|説明|  
|--------|--------|  
|[WriteOnlyArray::begin メソッド](../cppcx/writeonlyarray-begin-method.md)|配列内の最初の要素を指す反復子。|  
|[WriteOnlyArray::Data プロパティ](../cppcx/writeonlyarray-data-property.md)|データ バッファーへのポインター。|  
|[WriteOnlyArray::end メソッド](../cppcx/writeonlyarray-end-method.md)|配列内の最後の要素の 1 つ後ろを指す反復子。|  
|[WriteOnlyArray::FastPass プロパティ](../cppcx/writeonlyarray-fastpass-property.md)|配列が FastPass 機構を使用できるかどうかを示します。この機構は、システムで透過的に実行される最適化です。 コード内でこのプロパティを使用しないでください。|  
|[WriteOnlyArray::Length プロパティ](../cppcx/writeonlyarray-length-property.md)|配列内の要素の数を返します。|  
|[WriteOnlyArray::set 関数](../cppcx/writeonlyarray-set-function.md)|指定した要素を指定した値に設定します。|  
  
## 継承階層  
 `WriteOnlyArray`  
  
## 必要条件  
 コンパイラ オプション: **\/ZW**  
  
 **メタデータ:** Platform.winmd  
  
 **名前空間:** Platform  
  
## 参照  
 [\(NOTINBUILD\) Platform 名前空間](http://msdn.microsoft.com/ja-jp/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)